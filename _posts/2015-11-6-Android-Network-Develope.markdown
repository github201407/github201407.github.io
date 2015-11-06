---
layout: post
title:  "Android Network Develope"
date:   2015-11-6 21:16:00
categories: jekyll update
---
# Connecting to the Network
1.permissions
{% highlight ruby %}
	<uses-permission android:name="android.permission.INTERNET" />
	<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
{% endhighlight %}

2.Check the Network Connection
{% highlight ruby %}
	ConnectivityManager connMgr = (ConnectivityManager) getSystemService(Context.CONNECTIVITY_SERVICE);
    NetworkInfo networkInfo = connMgr.getActiveNetworkInfo();
    if (networkInfo != null && networkInfo.isConnected()) {
        // fetch data
    } else {
        // display error
    }
{% endhighlight %}

3.Perform Network Operations on a Separate Thread
{% highlight ruby %}
	private class DownloadWebpageTask extends AsyncTask<String, Void, String> {
        @Override
        protected String doInBackground(String... urls) {
              
            // params comes from the execute() call: params[0] is the url.
            try {
                return downloadUrl(urls[0]);
            } catch (IOException e) {
                return "Unable to retrieve web page. URL may be invalid.";
            }
        }
        // onPostExecute displays the results of the AsyncTask.
        @Override
        protected void onPostExecute(String result) {
            textView.setText(result);
       }
    }
{% endhighlight %}

4.Connect and Download Data
{% highlight ruby %}
	// Given a URL, establishes an HttpUrlConnection and retrieves
	// the web page content as a InputStream, which it returns as
	// a string.
	private String downloadUrl(String myurl) throws IOException {
		InputStream is = null;
		// Only display the first 500 characters of the retrieved
		// web page content.
		int len = 500;
			
		try {
			URL url = new URL(myurl);
			HttpURLConnection conn = (HttpURLConnection) url.openConnection();
			conn.setReadTimeout(10000 /* milliseconds */);
			conn.setConnectTimeout(15000 /* milliseconds */);
			conn.setRequestMethod("GET");
			conn.setDoInput(true);
			// Starts the query
			conn.connect();
			int response = conn.getResponseCode();
			Log.d(DEBUG_TAG, "The response is: " + response);
			is = conn.getInputStream();

			// Convert the InputStream into a string
			String contentAsString = readIt(is, len);
			return contentAsString;
			
		// Makes sure that the InputStream is closed after the app is
		// finished using it.
		} finally {
			if (is != null) {
				is.close();
			} 
		}
	}
{% endhighlight %}

5.Convert the InputStream to a String
{% highlight ruby %}
	InputStream is = null;
	Bitmap bitmap = BitmapFactory.decodeStream(is);
	ImageView imageView = (ImageView) findViewById(R.id.image_view);
	imageView.setImageBitmap(bitmap);
{% endhighlight %}

{% highlight ruby %}
	// Reads an InputStream and converts it to a String.
	public String readIt(InputStream stream, int len) throws IOException, UnsupportedEncodingException {
		Reader reader = null;
		reader = new InputStreamReader(stream, "UTF-8");        
		char[] buffer = new char[len];
		reader.read(buffer);
		return new String(buffer);
	}
{% endhighlight %}

[Managing Network Usage][Managing Network Usage]

[Multithreading For Performance][Multithreading For Performance]

[Transmitting Network Data Using Volley][Transmitting Network Data Using Volley]

Volley is not suitable for large download or streaming operations, 
since Volley holds all responses in memory during parsing. 
For large download operations, consider using an alternative like DownloadManager.

[DownloadManager][DownloadManager]: The download manager is a system service that handles long-running HTTP downloads.

[DownloadManager]:	https://developer.android.com/reference/android/app/DownloadManager.html
[Managing Network Usage]:	http://developer.android.com/training/basics/network-ops/managing.html
[Multithreading For Performance]:	http://android-developers.blogspot.com/2010/07/multithreading-for-performance.html
[Transmitting Network Data Using Volley]:	https://developer.android.com/training/volley/index.html
