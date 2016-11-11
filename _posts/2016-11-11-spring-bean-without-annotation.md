	@Bean
	public Client getClient() throws UnknownHostException {
		if (null == client) {
			Settings settings = buildSettings();
			TransportAddress address = getTransportAddress();

			client = TransportClient.builder().settings(settings).build().addTransportAddress(address);
		}

		return client;
	}
