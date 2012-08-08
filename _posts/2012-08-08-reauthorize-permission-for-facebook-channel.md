---
layout: post
title: Re-authorize permission for Facebook channel
---

When I was developing the Facebook channel, the Facebook Graph API supports the offline_access permission. With this permission, users authorize once and an application can access the user data forever(except users deauthorize or change their passwords later). However, before we launched Linktuned, Facebook was planning to [remove the offline_access permission](https://developers.facebook.com/roadmap/offline-access-removal/). As a result, all the tokens we get from the authorizations, will have a 2-month expiration time.

Once the authorization/token is expired, our crawler will not be able to get links from your Facebook account anymore. This will affect users who signed in with Twitter or with the form, and later add Facebook as a link channel. For those who always signin with Facebook, you are **not** affected because every time you sign in, we get a valid token from Facebook. So even if your token is expired, we can get a new one through your signin.

We did some updates to fix this issue, and if you are among the affected ones, you will probably see the following tooltip after signin:

![Facebook token expired](/images/token_expired.png)

Please click the Facebook button to re-authorize. If it is successful, the tooltip should disappear.

This will happen every 2 months. Sorry for the inconvenience. 

