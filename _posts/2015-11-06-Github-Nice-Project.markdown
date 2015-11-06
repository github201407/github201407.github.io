---
layout: post
title:  "Github Nice Project"
date:   2015-11-6 23:49:00
categories: jekyll update
---

1.[android-async-http][android-async-http]
	e.g. [Nice Example][Nice Example]
	
{% highlight ruby %}
	AsyncHttpClient client = new AsyncHttpClient();
	client.get("http://www.google.com", new AsyncHttpResponseHandler() {
		@Override
		public void onSuccess(String response) {
			System.out.println(response);
		}
	});
{% endhighlight %}

{% highlight ruby %}
	public class BooheeClient {
	
	  private static final String BASE_URL = "http://www.boohee.com/api/";
	  private static AsyncHttpClient client = new AsyncHttpClient();
	  
	  public static void get(String url, RequestParams params, AsyncHttpResponseHandler responseHandler) {
		  client.get(getAbsoluteUrl(url), params, responseHandler);
	  }

	  public static void post(String url, RequestParams params, AsyncHttpResponseHandler responseHandler) {
		  client.post(getAbsoluteUrl(url), params, responseHandler);
	  }

	  private static String getAbsoluteUrl(String relativeUrl) {
		  return BASE_URL + relativeUrl;
	  }
	}
{% endhighlight %}

{% highlight ruby %}
	class BooheeClientUsage {
		public void getPublicTimeline() throws JSONException {
			BooheeClient.get("moya_video", null, new JsonHttpResponseHandler() {
				@Override
				public void onSuccess(JSONObject video) {
					// Pull out the first event on the public timeline
					String normal_url = video.getString("normal_url");

					// Do something with the response
					System.out.println(normal_url);
				}
			});
		}
	}
{% endhighlight %}


[Nice Example]:		http://stormzhang.com/android/2013/01/27/android-async-http/
[android-async-http]:	https://github.com/loopj/android-async-http