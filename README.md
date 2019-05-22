# Tomcat
stop tomcat server port 

https://stackoverflow.com/questions/42084188/kill-tomcat-service-running-on-any-port-windows

https://github.com/leeponlp/spring-boot-oauth2/tree/master/src/main/java/com/qy/conf

https://stackoverflow.com/questions/16851199/sending-an-e-mail-through-java-application-with-excel-file-attached-not-workin/16851851

https://medium.com/oril/spring-boot-websockets-angular-5-f2f4b1c14cee

https://medium.com/@JavaArchitect/configure-ssl-certificate-with-spring-boot-b707a6055f3

# SSL

https://stackoverflow.com/questions/2893819/accept-servers-self-signed-ssl-certificate-in-java-client

https://zoltanaltfatter.com/2016/04/30/soap-over-https-with-client-certificate-authentication/

https://medium.com/@pakin/git-%E0%B8%84%E0%B8%B7%E0%B8%AD%E0%B8%AD%E0%B8%B0%E0%B9%84%E0%B8%A3-git-is-your-friend-c609c5f8efea


https://ace.c9.io/#nav=embedding

    TrustManager[] trustAllCerts = new TrustManager[] {
			new X509TrustManager() {
				@Override
				public X509Certificate[] getAcceptedIssuers() {
					return null;
				}
				
				@Override
				public void checkClientTrusted(X509Certificate[] certs, String authType) {
					// Trust always
				}
				
				@Override
				public void checkServerTrusted(X509Certificate[] certs, String authType) {
					// Trust always
				}
			}
		};

		// Install the all-trusting trust manager
		SSLContext sc = SSLContext.getInstance("SSL");
		// Create empty HostnameVerifier
		HostnameVerifier hv = new HostnameVerifier() {
			@Override
			public boolean verify(String arg0, SSLSession arg1) {
				return true;
			}
		};

		sc.init(null, trustAllCerts, new java.security.SecureRandom());
		HttpsURLConnection.setDefaultSSLSocketFactory(sc.getSocketFactory());
		HttpsURLConnection.setDefaultHostnameVerifier(hv);
