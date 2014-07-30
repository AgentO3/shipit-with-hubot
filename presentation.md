![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/hubot.jpg)

# Ship All the Things: Intro to ChatOps and Hubot

!

![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/vc-team.jpg)

# Hi! My name is Owen

!

![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/vc-team.jpg)

- Work for VividCortex
- Developer
- Deployment automation
- Spearheading ChatOps
- I brew beer, play guitar & snowboard!


!

![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/ship1.jpg)

# The ShipIt! Culture

!

![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/matrix_code_term.jpg)


# Getting code to production

!

![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/ship2.jpg)


# early and often

!



![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/deployment.jpg)


# deployments <br>easy <br>fun <br>accessible & safe

!

![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/chat.jpg)

# ChatOps FTW

!

# Put tools in the middle of the chatroom conversation

![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/tools.jpg)

!

![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/robot-dance.gif)

# Meet Thing the VividCortex Hubot

!

![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/robot-dance.gif)

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


![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/team.jpg)


# Enables everyone to ShipIt!

!

![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/human-keyboard)

# No Human Keyboards Allowed!

!


![bg](https://dl.dropboxusercontent.com/u/69816878/shipit-with-hubot/pairing.jpg)

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

![bg](http://i1.ytimg.com/vi/wSReSGe200A/maxresdefault.jpg)

- thing natalie me
- thing cats bomb me 10
- thing doge bomb me


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
#   AgentO3
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

# Hubot Commands

!

### In House Scripts

The VividCortex Hubot Script

<small>https://github.com/VividCortex/hubot-vividcortex</small>

DBA Me Hubot Script

<small>https://github.com/AgentO3/dba-me</small>

!

Cats Me Hubot Script

<small>https://github.com/AgentO3/cats-me</small>

Elastic Log Hubot Script

<small>https://github.com/AgentO3/elastic-log</small>

!

### Linkage

ChatOps at GitHub by Jesse Newland 

<small>https://www.youtube.com/watch?v=NST3u-GjjFw</small>

ChatOps: Augmented Reality for Ops by Mark Imbriaco

<small>https://www.youtube.com/watch?v=pCVvYCjvoZI</small>

!

A Guide to Hubot Scripting

<small>https://github.com/github/hubot/blob/master/docs/scripting.md</small>


!

#Q&A

#### Rate my talk 

http://spkr8.com/t/34651
 
#### Follow Me 

@AgentO3





