+++
Categories = ['fossasia site']
Tags = ['fossasia', 'html', 'css', 'site', 'pull request', 'issues', 'github']
date = "2015-12-20T17:17:02-05:00"
title = "Bug Fixes for GCI Student Site"

+++

Yesterday, I made two pull requests for [FOSSASIA](https://codein.withgoogle.com/organizations/fossasia/). My [first pull request](https://github.com/fossasia/gci15.fossasia.org/pull/83) fixed the issue of the icons being scattered all over the place. The icons were originally off centered from the avatar circle and off center from each other. I created a flexbox grid that automtically centered the social media icons to the center of the avatar circle. Then, I set a definte size for the a element and centered each icon vertically and horizontally inside the corresponding link elements.  

![icons](http://puu.sh/m2Ri8/804ddfb4e3.jpg)

My [second pull request](https://github.com/fossasia/gci15.fossasia.org/pull/97) aligned the Google Plus iframe so that it would stay in the center instead of being pushed to the left. It was a simple `text-align: center;` fix.  

![google plus](http://puu.sh/m2R03/efa23baa1a.jpg)


I also added my own profile picture and information in [pull request #125](https://github.com/fossasia/gci15.fossasia.org/pull/125).  