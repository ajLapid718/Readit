# README

A clone of Reddit. First app deployed to Heroku. This helped me to develop slightly more familiarity with differences in development and production. I also became more familiar with Heroku commands in the terminal as well as using SO to determine what was deprecated and what was not between different versions of Rails. I learned a little bit about the Bootstrap framework as well as HTML, CSS, JS, and jQuery. This also helped me work with constantly tracking files and committing (descriptively) and pushing. This is also one of the first READMes I am purposefully filling out. Became familiar with the concept of dyno hours as well. Became comfortable with editing the gemfile. Need to brush up on branches and merging branches. Learned about scaffolding as well.

* Small victories:
  - Became familiar with GitHub Markdown
  - ctrl + shift + f
  - developed intuition on which folders I needed to navigate to
  - learned more terminology here and there
  - btn group

  ```ruby
  the_front_page_of_the_internet = "reddit!"
  print the_front_page_of_the_internet
  ```

  ```
  left
  ```
  ```
  up
  ```
  ```
  right
  ```
  ```
  down
  ```

  `left`, `up`, `right`, `down`

##### Features
* Sign In
* Sign Up
* Edit Account
* Submit Link/Thread
* Comment
* Upvote/Downvote (Static)
* Sign Out
* Auth Pattern

* No functionality or view for canceling an account/deleting an account.


Side Note/Reminder: For the favicon, this is what I did.
1) Resize picture into 16x16 or 32x32 heightxwidth.
2) Make sure the extension is .ico
3) Put the file in the public pipeline (didn't work with assets pipeline).
4) Put: `<link href="/ubecon.ico" rel="shortcut icon" type="image/x-icon" />` in the head of the html in the application.html.erb folder. (the backslash prior to ubecon.ico is unnecessary in this case)
5) Syntax: in HTML5, the backslash to close the link tag is unnecessary but it won't break if it is there like above. The whitespace is also benign. It could have been written like so: `<link href="ubecon.ico" rel="shortcut icon" type="image/x-icon">`
6) Similar to button_to or link_to, there is a Rails helper that is functionally equivalent to the written-out link tag for a favicon. The embedded ruby code looks like: `<%= favicon_link_tag 'ubecon.ico' %>`
7) If the filename remains unchanged as favicon.ico, then the code would look like: `<%= favicon_link_tag %>`
  - Be mindful of:
    - Cache in terms of the Rails app
    - Cache in terms of the browser
    - One user on SO explains: "It is better/standard to have the favicon on yourdomain.com/favicon.ico as some browsers request for them directly (even when you do not use the meta tag for it)"
    - Discern the extent to which the location of the file is significant
    - 16x16 and 32x32 (for retina displays)
    - Other web browsers and their requirements (chrome vs internet explorer)
8) No need to scale app aka no need to run: `heroku ps:scale web=0` in order to make changes as far as I can tell.
9) Figure out how to use the assets/images pipeline (does the favicon_link_tag method assist in this endeavor?) because that is more organized than using the public folder (although it is weird that the stock/default favicon.ico file is located in the pubic pipeline) and learn the differences.
10) According to a SO user: "Place the favicon.ico image in /app/assets/images/ if you are using the asset pipeline, and in /public/images/ if you are not" when using the rails helper metod.
11) According to a SO user: " `<%= favicon_link_tag 'favicon.ico' %>` points to app/assets/images/favicon.ico, as opposed to public/assets/images/favicon.ico" but this is odd because I am using the helper and the icon is in the public pipeline...
