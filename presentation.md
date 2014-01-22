![bg](http://octodex.github.com/images/hubot.jpg)

<!-- 

-->


# ShipIt With Hubot

!

![bg](/images/vc-team.jpg)

# About Me 

- Frontend developer
- Deployment automation
- Spearheading ChatOps
- I brew beer, play guitar & snowboard!


!

![bg](http://farm6.staticflickr.com/5018/5405915409_5065c4b297_b.jpg)

# The ShipIt! Culture

!

![bg](http://farm7.staticflickr.com/6075/6049646962_d5327553ba_b.jpg)


# ShipIt! is about getting code to production

!


![bg](http://farm7.staticflickr.com/6075/6049646962_d5327553ba_b.jpg)


# by making deployments easy fun & accessible

!

![bg](http://farm3.staticflickr.com/2850/10501143674_f8fdc7775a_o.jpg)

# ChatOps FTW

!

![bg](https://lh6.googleusercontent.com/-76_wSBeN4b0/Um9Dt5NLuAI/AAAAAAAATlo/2JxlxF4yKwg/s640/spainjs_01.png)

# What is ChatOps?

!

# It's about putting tools in the middle of the chatroom conversation

![bg](http://farm4.staticflickr.com/3206/3108399560_e3cdfbccf9_o.jpg)

!

# How does that work?

![bg](http://i.imgur.com/HFsWj.jpg)

!


### Push my branch to Github

```
git push origin 123-shipit
```

!

### Deploy it to our staging server (Pooroku) with Hubot

```
thing deploy webapp 123-shipit
```

!

### We check to make sure it works as expected

!

### Create the Pull Request in GitHub

!

### Someone reviews my Pull Request and says ShipIt!

!

### I merge the Pull Request to master and run.

```
thing release webapp patch
```

!

![bg](http://content.screencast.com/users/ozanzal/folders/Jing/media/d8b17b40-2d9e-4e2e-8640-98ba7dc229d7/00000051.png)

# Successful!

!

### Looks good in production!!!

```
thing beer me
```

!

![bg](http://farm4.staticflickr.com/3330/4596126247_f5b64904c2_b.jpg)


# Enables everyone to ShipIt!

!

![bg](http://farm3.staticflickr.com/2649/3764949110_0db9fe1865_b.jpg)

# No Human Keyboards Allowed!

!


![bg](http://farm5.staticflickr.com/4068/4638056301_f34564ce78_b.jpg)

# Learn by seeing others

!

![bg](http://farm4.staticflickr.com/3504/3944265754_cab00132c2_o.jpg)

# Works wherever chat is

!


![bg](http://farm5.staticflickr.com/4072/4420110649_685dd31703_o.jpg)

# You write it, you test it, you <br/> deploy it

!

![bg](http://farm7.staticflickr.com/6211/6858583426_1f003ea519_b.jpg)

# Automate! Automate! Automate!

!

![bg](http://farm5.staticflickr.com/4003/4310364093_a53195bd03_b.jpg)

# Access control

- Word of the day
- Roles
- Nothing

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

![bg](http://farm5.staticflickr.com/4070/4456489056_061592c991_b.jpg)

# Ears

!

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.<span class="highlight">respond</span> /natalie bomb(?: me)?( \d+)?$/i, (msg) ->
    natalies = msg.match[1] || 4
    msg.http(url)
     .get() (err, res, body) ->
       res = JSON.parse(body)
       (msg.send res[i]) for i in [0..natalies]
</div>

!

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.respond <span class="highlight">/natalie bomb(?: me)?( \d+)?$/i</span>, (msg) ->
    natalies = msg.match[1] || 4
    msg.http(url)
     .get() (err, res, body) ->
       res = JSON.parse(body)
       (msg.send res[i]) for i in [0..natalies]
</div>

!

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.respond /natalie bomb(?: me)?( \d+)?$/i, (msg) ->
    natalies = <span class="highlight">msg.match[1]</span> || 4
    msg.http(url)
     .get() (err, res, body) ->
       res = JSON.parse(body)
       (msg.send res[i]) for i in [0..natalies]
</div>

!

![bg](http://farm5.staticflickr.com/4087/5103883432_030b060720_b.jpg)


# Arms

!

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.respond /natalie bomb(?: me)?( \d+)?$/i, (msg) ->
    natalies = msg.match[1] || 4
    <span class="highlight">msg.http(url)</span>
     .get() (err, res, body) ->
       res = JSON.parse(body)
       (msg.send res[i]) for i in [0..natalies]
</div>

!

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.respond /natalie bomb(?: me)?( \d+)?$/i, (msg) ->
    natalies = msg.match[1] || 4
    msg.http(url)
     <span class="highlight">.get() (err, res, body) -> </span>
       res = JSON.parse(body)
       (msg.send res[i]) for i in [0..natalies]
</div>

!

![bg](http://farm4.staticflickr.com/3113/2294987464_b0a5940b69_b.jpg)

# Mouth

!

<div class="code">
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.respond /natalie bomb(?: me)?( \d+)?$/i, (msg) ->
    natalies = msg.match[1] || 4
    msg.http(url)
     .get() (err, res, body) ->
       res = JSON.parse(body)
       (<span class="highlight">msg.send</span> res[i]) for i in [0..natalies]
</div>

!

![bg](http://farm1.staticflickr.com/86/260323825_1533332578_o.jpg)

# The Brain

!

```
url = 'https://natalie.com/natalie-me.json'

module.exports = (robot) ->
  robot.respond /natalie?(?: me)?$/i, (msg) ->
    msg.http(url)
      .get() (err, res, body) ->
        msg.send msg.random JSON.parse(body)
```

!

![bg](http://fc02.deviantart.net/fs70/i/2011/231/5/d/pokemon_master_red_by_2d75-d473gi1.jpg)

# Hubot Training 101

!

#Q&A

#### Rate my talk 

http://spkr8.com/t/28731
 
#### Follow Me 

@O3Design
