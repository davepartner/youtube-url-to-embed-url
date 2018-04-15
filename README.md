# youtube-url-to-embed-url
A simple PHP code to effectively  convert normal youtube url to youtube embed url.

```


<?php 
//there are two types of youtube normal url
//the code below simulatneously takes care of the two.
//many codes that attempt to do this fail because they don't realize this ancient truth

              $url = "https://www.youtube.com/watch?v=q4aL9h6-WIA";
              $shortUrlRegex = '/youtu.be\/([a-zA-Z0-9_]+)\??/i';
              $longUrlRegex = '/youtube.com\/((?:embed)|(?:watch))((?:\?v\=)|(?:\/))(\w+)/i';
          
              if (preg_match($longUrlRegex, $url, $matches)) {
                  $youtube_id = $matches[count($matches) - 1];
              }
          
              if (preg_match($shortUrlRegex, $url, $matches)) {
                  $youtube_id = $matches[count($matches) - 1];
              }
              $fullEmbedUrl = 'https://www.youtube.com/embed/' . $youtube_id ;
          ?>
          
          <!-- the embed code -->
          
<iframe id="ytplayer" type="text/html" width="560" height="400"
    src="<?php echo $fullEmbedUrl ?>?rel=0&showinfo=0&color=white&iv_load_policy=3"
    frameborder="0" allowfullscreen></iframe> 
    
```

Check me out on udemy, you could find one of my courses you may like =>
[Dave Partner on Udemy](udemy.com/user/daveozoalor)

Chat me up to say thank you => daveozoalor@gmail.com
I rant on twitter [Dave Partner on Twitter](twitter.com/daveozoalor)
