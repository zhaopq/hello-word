public SchedulerFactoryBean schedulerFactoryBean(DataSource dataSource) {
	SchedulerFactoryBean factory = new SchedulerFactoryBean();
	factory.setDataSource(dataSource);

	// quartz参数
	Properties prop = new Properties();
	prop.put("org.quartz.scheduler.instanceName", "ZPQScheduler");
	prop.put("org.quartz.scheduler.instanceId", "AUTO");
	// 线程池配置
	prop.put("org.quartz.threadPool.class", "org.quartz.simpl.SimpleThreadPool");
	prop.put("org.quartz.threadPool.threadCount", "20");
	prop.put("org.quartz.threadPool.threadPriority", "5");
	// JobStore配置
	prop.put("org.quartz.jobStore.class", "org.quartz.impl.jdbcjobstore.JobStoreTX");
	// 集群配置
	prop.put("org.quartz.jobStore.isClustered", "true");
	prop.put("org.quartz.jobStore.clusterCheckinInterval", "15000");
	prop.put("org.quartz.jobStore.maxMisfiresToHandleAtATime", "1");

	prop.put("org.quartz.jobStore.misfireThreshold", "12000");
	prop.put("org.quartz.jobStore.tablePrefix", "QRTZ_");
	factory.setQuartzProperties(prop);
  }
