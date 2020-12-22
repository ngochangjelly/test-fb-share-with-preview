## How to share webpage link to facebook with specific thumbail

- Insert facebook share button in webpage to share post
- In order for the share button to work, you need to add Facebook SDK before the share button as mentioned in Facebook fdocumentatio: https://developers.facebook.com/docs/plugins/share-button/

    ```
    <!-- Load Facebook SDK for JavaScript -->
    <div id="fb-root"></div>
    <script>(function(d, s, id) {
    var js, fjs = d.getElementsByTagName(s)[0];
    if (d.getElementById(id)) return;
    js = d.createElement(s); js.id = id;
    js.src = "https://connect.facebook.net/en_US/sdk.js#xfbml=1&version=v3.0";
    fjs.parentNode.insertBefore(js, fjs);
    }(document, 'script', 'facebook-jssdk'));</script>

    ```
- The mechanisim to show shared post preview thumbnail is: when user share a url to Facebook, Facebook will call API to that webpage to get data to display. So, we have to specify in webpage head these following information:

    ```
        <head>
            <title>Your Website Title</title>
            <meta property="og:url" content="{{web domain}}/index.html" />
            <meta property="og:type" content="website" />
            <meta property="og:title" content="your preview title" />
            <meta property="og:description" content="your preview description" />
            <meta property="og:image" content="{{web domain}}/thumbnail.jpg" />
        </head>
    ```

- Demo:
    - I have implemented a simple web page and deploy it in netlify to test the facebook share with preview feature. You can have a look here: https://keen-yalow-af3cc7.netlify.app/
    - Find out code here: 



### Preference
- https://developers.facebook.com/docs/plugins/share-button/