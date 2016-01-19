##What is fakeCloudapp??
To develop cloud app easily before registering your url in [Seller Office Site](http://seller.samsungapps.com/tv/portal/main)


##Cloud app
[How to register your URL](http://www.samsungdforum.com/TizenGuide/tizen1731/index.html#TV-Application-View)

 You can also host your TV app on your own cloud based server. Using the Smart View SDK, you can launch your cloud based TV app by it's URL. In this scenario, there will be nothing for the user to download to the TV, but also means your app will not have an icon within SmartHub on the TV.
> Cloud TV Apps must be "whitelisted" in order to be launched on a Samsung SmartTV and TizenTV.

> a. To publish your Cloud TV App, visit Seller Office Site and sign up.

> b. Select "Cast Suppoted App Registration" - "Cloud TV App"

> c. Fill in basic information with Cloud URL.

###1. URL
TV can't launch your url before registering sellersite.

ex) http://dev-multiscreen-examples.s3-website-us-west-1.amazonaws.com/examples/helloworld/tv/


###2. fakCloudApp
add your URL into window.location

	<script type="text/javascript"> 
		var init = function () { 
			window.location = "http://dev-multiscreen-examples.s3-website-us-west-1.amazonaws.com/examples/helloworld/tv/"; 
		} 
		 
		window.onload = function(){ 
			init(); 
		}; 
	</script>

###2. Mobile launch fakeCloudApp
Test and verfiy your cloud app

        // Launch Installed  App
        String appId = "dEZRQkxXVQ.FakeCloudApp";
        String channelId = app.getConfig().getHelloWorldChannel();
        msApplication = service.createApplication(appId, channelId);

###3. Mobile launch cloud app(URL)
After register your URL in Seller Site

        //Launch Cloud App
        Uri uri = "http://dev-multiscreen-examples.s3-website-us-west-1.amazonaws.com/examples/helloworld/tv/"
        String channelId = app.getConfig().getHelloWorldChannel();
        msApplication = service.createApplication(uri, channelId);
