![bg](http://octodex.github.com/images/hubot.jpg)

# ShipIt with Hubot

!

![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/vc-team.jpg)

# Hi! My name is Owen

!

![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/vc-team.jpg)

- Work for VividCortex
- Frontend developer
- Deployment automation
- Spearheading ChatOps
- I brew beer, play guitar & snowboard!


!

![bg](http://farm6.staticflickr.com/5018/5405915409_5065c4b297_b.jpg)

# The ShipIt! Culture

!

![bg](http://www.etherice.com/rmx/images/matrix/matrix_code_term.jpg)


# Getting code to production

!

![bg](http://farm7.staticflickr.com/6151/6159637428_6bffb5bce1_b.jpg)


# early and often

!



![bg](http://farm9.staticflickr.com/8542/8683120433_625f99b942_b.jpg)


# deployments <br>easy <br>fun <br>accessible & safe

!

![bg](http://farm3.staticflickr.com/2850/10501143674_f8fdc7775a_o.jpg)

# ChatOps FTW

!

# Put tools in the middle of the chatroom conversation

![bg](http://farm4.staticflickr.com/3206/3108399560_e3cdfbccf9_o.jpg)

!

![bg](http://24.media.tumblr.com/c2bb0f32b5a767e3ad80fc6c14f1e0c3/tumblr_miuial56jj1qedf7ko2_r5_1280.gif)

# Meet Thing the VividCortex Hubot

!

![bg](http://24.media.tumblr.com/c2bb0f32b5a767e3ad80fc6c14f1e0c3/tumblr_miuial56jj1qedf7ko2_r5_1280.gif)

# Let's put </br>Thing to work

!

### Push feature branch to Github

![img](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/demo1.png)

!

### Deploy it to stage

![img](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/demo2.png)

!

### Thing let's us know it's deployed

![img](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/demo3.png)

##### we're rewarding with a picture of Natalie

!

### Create the Pull Request

![img](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/demo4.png)

#### and ask John to review it

!

### ShipIt!

![img](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/demo6.png)

!

### Merge the Pull Request

![img](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/demo5.png)

!

### Then release it

![img](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/demo7.png)

!

# w00t!

![img](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/demo8.png)


!


![bg](http://farm4.staticflickr.com/3330/4596126247_f5b64904c2_b.jpg)


# Enables everyone to ShipIt!

!

![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/human-keyboard)

# No Human Keyboards Allowed!

!


![bg](http://farm5.staticflickr.com/4068/4638056301_f34564ce78_b.jpg)

# Learn by seeing others

!

![bg](http://farm4.staticflickr.com/3504/3944265754_cab00132c2_o.jpg)

# Works wherever chat is

!


![bg](http://farm5.staticflickr.com/4072/4420110649_685dd31703_o.jpg)

# Maintains code ownership

!

![bg](http://i1.ytimg.com/vi/wSReSGe200A/maxresdefault.jpg)

# It's fun!!!

!


![bg](http://farm5.staticflickr.com/4003/4310364093_a53195bd03_b.jpg)

# Access control

!


![bg](http://farm5.staticflickr.com/4003/4310364093_a53195bd03_b.jpg)

- Word of the day
- Roles
- None of the above

!

![bg](http://farm8.staticflickr.com/7173/6539741537_29f3f585f2_b.jpg)

# Keep sharp <br/>tools out

!

![bg](http://stream1.gifsoup.com/view2/1374951/trust-fall-fail-o.gif)

# Trust your people

!

![bg](https://github-camo.global.ssl.fastly.net/219e92aa54ddb56821d5c7257bd1cd5ed041d87d/687474703a2f2f6875626f742e6769746875622e636f6d2f696d616765732f6c61796f75742f736368656d617469632e737667)

# The Nuts and Bolts of Hubot

!

![bg](http://farm9.staticflickr.com/8348/8264844028_94f0e37319_b.jpg)

# Adapters

!

![bg](http://farm9.staticflickr.com/8348/8264844028_94f0e37319_b.jpg)

- IRC
- HipChat
- CampFire
- Flowdock
- Twitter
- Many Many More

!

# Scripts

![img](https://dl.dropboxusercontent.com/u/69816878/scripts-dir.png)

!

### Documentation

<div class="code">
# Description:
#   Natalie!
#
# Dependencies:
#   None
#
# Configuration:
#   None
#
# Commands:
#   hubot natalie me - A randomly selected natalie
#   hubot natalie bomb me &lt;number&gt; - natalie explosion!
#
# Author:
#   o3design
</div>

!

### Listen for command by name

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.<span class="highlight">respond</span> /natalie bomb(?: me)?( \d+)?$/i, (msg) ->
    natalies = msg.match[1] || 4
    msg.http(url)
     .get() (err, res, body) ->
       pics = JSON.parse(body)
       (msg.send msg.random pics) for i in [0..natalies]
</div>

!

### If CoffeeScript ain't your thang
<div class="code">

var url = 'https://natalie.com/natalie-me.json';

module.exports = function(robot) {
  robot.<span class="highlight">respond</span>(/nataliejs bomb(?: me)?( \d+)?$/i, 
  function(msg) {
    var  natalies = msg.match[1] || 4; 
    msg.http(url).get()(function(err, res, body) {
      var pics = JSON.parse(body),
          count = 0;
      while (count < natalies) {
        msg.send(msg.random(pics));
        count ++;
      }
    });
  });
};
</div>

!

#### thing natalie bomb me

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.respond <span class="highlight">/natalie bomb(?: me)?( \d+)?$/i</span>, (msg) ->
    natalies = msg.match[1] || 4
    msg.http(url)
     .get() (err, res, body) ->
       pics = JSON.parse(body)
       (msg.send msg.random pics) for i in [0..natalies]
</div>

!

#### thing natalie bomb me 10

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.respond /natalie bomb(?: me)?( \d+)?$/i, (msg) ->
    natalies = <span class="highlight">msg.match[1]</span> || 4
    msg.http(url)
     .get() (err, res, body) ->
       pics = JSON.parse(body)
       (msg.send msg.random pics) for i in [0..natalies]
</div>

!



### Listen for any match

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.<span class="highlight">hear</span> /natalie bomb(?: me)?( \d+)?$/i, (msg) ->
    natalies = msg.match[1] || 4
    msg.http(url)
     .get() (err, res, body) ->
       pics = JSON.parse(body)
       (msg.send msg.random pics) for i in [0..natalies]
</div>

!

### On entering the room

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.<span class="highlight">enter</span> (msg) ->
    msg.http(url)
     .get() (err, res, body) ->
       pics = JSON.parse(body)
       msg.send msg.random pics
</div>

!

### On leaving the room

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.<span class="highlight">leave</span> (msg) ->
    msg.http(url)
     .get() (err, res, body) ->
       pics = JSON.parse(body)
       msg.send msg.random pics
</div>

!

### On http request

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.<span class="highlight">router.post</span> '/natalie/me/:qty', (req, pics) ->
    qty = req.params.qty || 4
    msg.http(url)
     .get() (err, pics, body) ->
       pics = JSON.parse(body)
       (msg.send msg.random pics) for i in [0..qty]
</div>

!

#### Talking REST

<div class="code">
<span class="highlight">url = 'https://natalie.com/natalie-me.json'</span>

module.exports = (robot) ->
  robot.respond /natalie bomb(?: me)?( \d+)?$/i, (msg) ->
    natalies = msg.match[1] || 4
    <span class="highlight">msg.http(url)</span>
     .get() (err, res, body) ->
       pics = JSON.parse(body)
       (msg.send msg.random pics) for i in [0..natalies]
</div>

!

#### Talking REST

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.respond /natalie bomb(?: me)?( \d+)?$/i, (msg) ->
    natalies = msg.match[1] || 4
    msg.http(url)
     <span class="highlight">.get() (err, res, body) -> </span>
       pics = JSON.parse(body)
       (msg.send msg.random pics) for i in [0..natalies]
</div>

!

#### Replying to the room

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.respond /natalie bomb(?: me)?( \d+)?$/i, (msg) ->
    natalies = msg.match[1] || 4
    msg.http(url)
     .get() (err, res, body) ->
       pics = JSON.parse(body)
       (<span class="highlight">msg.send</span> msg.random pics) for i in [0..natalies]
</div>

!

#### Replying directly to sender

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.respond /natalie bomb(?: me)?( \d+)?$/i, (msg) ->
    natalies = msg.match[1] || 4
    msg.http(url)
     .get() (err, res, body) ->
       pics = JSON.parse(body)
       (<span class="highlight">msg.reply</span> msg.random pics) for i in [0..natalies]
</div>

!

#### Memory

<div class="code">
module.exports = (robot) ->

  robot.respond /who is @?([\w .\-]+)\?*$/i, (msg) ->
    name = msg.match[1].trim()

    users = robot.<span class="highlight">brain.usersForFuzzyName(name)</span>
    if users.length is 1
      user = users[0]

      msg.send "#{name} is user - #{user}"
</div>

!

![bg](http://fc02.deviantart.net/fs70/i/2011/231/5/d/pokemon_master_red_by_2d75-d473gi1.jpg)

# Hubot Training 101

!

### thing deploy webapp 123-shipit

<div class="code">
- /Users/owen/code/vividcortex/thing/scripts/deploy.coffee
- http://10.10.10.175:8080/job/webapp-stage/configure
- http://10.10.10.175:8080/job/deploy-webapp-stage/configure
- http://10.10.10.175:8080/job/send-message-to-thing/configure
</div>

!

### thing merge webapp 123-shipit into master

<div class="code">
- /Users/owen/code/vividcortex/thing/scripts/git-merge.coffee
- http://10.10.10.175:8080/job/merge-branches/configure
- http://10.10.10.175:8080/job/send-message-to-thing/configure
</div>

!

### thing release webapp 123-shipit patch

<div class="code">
- /Users/owen/code/vividcortex/thing/scripts/deploy.coffee
- http://10.10.10.175:8080/job/webapp-master/configure
- http://10.10.10.175:8080/job/release-webapp/configure
- http://10.10.10.175:8080/job/send-message-to-thing/configure
</div>


!

![bg](http://farm3.staticflickr.com/2422/4098453037_55513099ef_o.jpg)

# The Future

!

![bg](http://farm7.staticflickr.com/6211/6858583426_1f003ea519_b.jpg)

# Automate! Automate! Automate!

!

![bg](http://farm5.staticflickr.com/4061/4425900247_0e9437a37f_b.jpg)

# Pull data into the conversation

!

![bg](http://farm5.staticflickr.com/4061/4425900247_0e9437a37f_b.jpg)

### thing log me webapp 50

### thing graph me cpu

### thing issues assigned to me

!

![bg](http://static3.wikia.nocookie.net/__cb20090314140222/terminator/images/6/6c/T4-art-concepting-041.jpg)

# System administration

!

![bg](http://static3.wikia.nocookie.net/__cb20090314140222/terminator/images/6/6c/T4-art-concepting-041.jpg)

### thing create db-shard3

### thing backup webapp1

### thing purge logs api-server2

!

#Q&A

#### Rate my talk 

http://spkr8.com/t/28731
 
#### Follow Me 

@O3Design
