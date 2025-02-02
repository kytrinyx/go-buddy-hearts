---
layout: page
title: What's New
include_in_header: true
---

# Changelog
The app is currently in alpha testing on iOS and Android.

This changelog is for the benefit of the testers.
Once v1.0 of the app is released, the changelog will be reset, showing only post-v1.0 changes.

<br>

### `Latest`
# **Version 0.0.1+31**

#### What's new

_Note that the notifications are still not working on Android. I'm working on figuring out why, but have no estimate as to when this will be fixed._

- We decided to change the decay notification so that it happens 3 minutes before decay, instead of 2 minutes. The game boots up pretty slowly, so if you get a 2 minute warning and then have to boot the game up from scratch, it can get a bit stressful.


<br>
### **Version 0.0.1+30**

#### Bug Fixes
- Okay. That flip-flopping was not fixed. I have still not been able to prove what is causing it, but I have another hypothesis. If I'm right, it will not continue to happen. (I'm not confident. Can you tell?)

<br>
### **Version 0.0.1+29**

#### Bug Fixes
- Sometimes the decay timer was observed to be flip-flopping between an old countdown and a new countdown. This should no longer happen.

<br>
### **Version 0.0.1+28**

#### Bug Fixes
- Actually trigger that notification that should have gone out in the previous build.

<br>

### **Version 0.0.1+27**

#### What's New

- Two minutes before decay happens, you'll get a notification about decay being imminent.

<br>
### **Version 0.0.1+26**

#### What's New
- We ditched the 'refresh' button next to the decay timer. Now that you can refresh with specific actions via the 'undo' and 'again' overlay, that button was redundant.
- To prevent old timelines from hanging around, when you open the app it resets the timeline if it hasn't had any activity on it today, provided that it has fully decayed to zero points. This should be inline with the behavior in Pokémon GO, but we may want to verify that.

#### Bug Fixes
- If you put the app in the background long enough for a bunch of decay to happen, it... just didn't. The decay timer finished, and you would get one point of decay, and it wouldn't start a new timer. It would do the right thing if you killed the app and restarted it, just not if you backgrounded it and then brought it back to the foreground. This is now fixed.

<br>

### **Version 0.0.1+25**

#### Bug Fixes
- Still fiddling with cooldown timer behavior. This time, if you clicked 'again' on the overlay while at double hearts, the decay timer didn't get reset, and the refresh failed to get added to the timeline shown on the details page.

<br>

### **Version 0.0.1+24**

#### Bug Fixes
- So, remember back in v0.0.1+18 where I said that I put the cooldown timers back after accidentally having changed them? It turns out I put them back to the wrong value (mixing up the default decay timer value and the default cooldown timer value). So, yeah. That is fixed f'real this time.

<br>
### **Version 0.0.1+23**

#### Bug Fixes
- We accidentally disabled refreshes entirely while at double-hearts. This is fixed: you get the usual 'undo' and 'again', where 'again' says it will reset the decay timer, but that you don't get points for it.

<br>
### **Version 0.0.1+22**

#### What's New

- The behavior of the activity buttons while the timer is at max was still not great: it felt like nothing was happening when you clicked the button. The button did have a small animation that showed that it was being pushed, but it just didn't feel like that was clear enough feedback. With this change we take a different approach: if you click an available activity, we disable the button. Then further interactions will be via the undo-or-again overlay, which should make it feel better.

<br>

### **Version 0.0.1+21**

No user-facing changes. I tried submitting build 20 for review so we can start external testing, and there was a configuration error that I needed to fix.

<br>

### **Version 0.0.1+20**

#### What's New

- We decided not to kill the cooldown timers when attaining double hearts after all. It makes it a bit more confusing, and you can no longer undo an action. What if you accidentally clicked the button that made it go to 32 points? You wouldn't be able to undo that. So yeah. We're reverting to the previous behavior.

<br>
### **Version 0.0.1+19**


#### What's New
- When attaining double-hearts (max points), it kills all the running cooldown timers, and doesn't start new ones. The timers are all going to run out before the first bit of decay happens, and until then no more points can be added.

#### Bug Fixes
- It turns out, hitting 'again' on an activity while it is in cooldown was resetting the cooldown timer. That is now fixed.

<br>
### **Version 0.0.1+18**

#### Bug Fixes
- This puts the cooldown timer durations back to where they should be, after temporarily changing them for an experiment and then forgetting to but them back.

### **Version 0.0.1+17**

#### Bug Fixes
- Normally you can only register two bonuses. But if you killed the app and restarted it, it would let you register one more. And if you killed it again, yeah... you get the idea. So that's fixed, now.

<br>

### **Version 0.0.1+16**
The basic app functionality is all in place. Now we need to get it into the hands of more testers. Thank you so much to taiwegian, our lone, pre-alpha tester!

#### What's New
- Now with a 'How it Works' screen, in case you haven't obsessively studied the Pokemon Go Buddy emotional points algorithm. Yes, I realize that this is almost everyone.

<br>

### **Version 0.0.1+15**

#### What's New
- The longpress explanations on the activity buttons are now split into multiple sections, accessible by swiping.

<br>

### **Version 0.0.1+14**

#### What's New
- Long-pressing the different activity buttons now provides some information about that activity—what it consists of, where and how to do it, and requirements to actually get the points for it.

<br>

### **Version 0.0.1+13**

#### Bug Fixes
- Fix bug with re-re-re-reverted events. It turns out if you do and undo the same event over and over again, the decay timer wasn't behaving correctly. This is now _actually_ fixed.

<br>

### **Version 0.0.1+12**

#### What's New
- The cooldown period used for bonus, walk, and routes is now 1 minute instead of 10 seconds. This makes it more likely that you'll have time to undo it, in the event that you accidentally registered the wrong event. You can always register a new one by using the 'again' button in the overlay.

#### Bug Fixes
- You can now revert more than one event, back to back. Previously, if you reverted one event, the decay timer would reset correctly, but if you then went and reverted some other event, the decay timer would start fresh.

<br>

### **Version 0.0.1+11**

#### What's New
- If you click on an activity button while the cooldown timer is running, you now get an overlay that gives you choices, rather than just reverting the event straight off the bat. People who aren't familiar with the algorithm and the app might click the 'feed' button because they fed their buddy, even when they wouldn't have gotten points for it. This makes sense. I feed my buddy all the time, even when it's not hungry, and I won't get points for it. The point being, we can't know ahead of time if you accidentally clicked the button in the first place, and would like to undo it, or if you clicked it because you did the same action again. The new overlay lets you clarify what you intended.
- The 'choose' activity has now been renamed to 'kickoff'. The various explanations about the buddy emotional points algorithm on Reddit explain that when you switch to a new buddy for the first time in a given day, you get two extra points, and that if you switch away, you lose those, and can't get them again. But it's a bit more nuanced than that. First of all, if you have the same buddy as yesterday and don't actually choose it, then you still get those points. Or, if you have the same buddy as yesterday, and then switch away, and then switch back and _then_ start feeding it, you also get the points. And you even get the points if you play with your buddy and take a snapshot (thus getting two affection hearts) and _then_ switch away, and switch back and start feeding it. We eventually determined that the two extra points are gained the first time you feed your buddy a berry in a given day. So rather than do something stupidly complicated with the 'feed' action, we decided to rename the action to 'kickoff'. When you start interacting with a new buddy on a given day, click 'kickoff', then when you feed it, click 'feed' as normal. As long as you don't switch away and switch back, you're good.

#### Bug Fixes
- This fixes a whole slew of bugs related to the fact that an event is not always worth the canonical number of points. If you're nearing the maximum, then an event will only get however many points are left to get to 32, not the full score for that event. The bugs happened when undoing events, and also when deciding whether or not you were allowed to register another bonus.

<br>

### **Version 0.0.1+10**

#### Bug Fixes
- Make it so the decay timer restarts if you revert an event.

<br>

### **Version 0.0.1+9**

#### What's New
- If you click an activity button while it's in the cooldown period, it will undo the event. E.g. if you clicked 'gym', and then realized that it wasn't a gym battle, it was a raid. What you want is to undo the 'gym' activity, and pick 'raid' instead.
- If a timer goes negative it now won't show anything at all, instead of showing a negative timer. While timers don't normally go negative, sometimes there's a bit of lag in the system, and they'll show negative values for a second or two before the timer catches up and refreshes. In this case it's better to just not show anything at all.

<br>

### **Version 0.0.1+8**

#### What's New
- The events in the detail page now show in reverse order, with the newest events at the top.

#### Bug Fixes
- The details page can now scroll. /facepalm (Yes, it turns out, sometimes it takes a whole lot of events to get your buddy excited. Who knew.)

<br>

### **Version 0.0.1+7**

#### What's New
- There's now a new screen that shows the timeline of all the events that you registered with this buddy. When you click 'reset', the timeline starts over.

<br>

### **Version 0.0.1+6**

#### What's New
- De-emphasizes the 'reset' button even more. We really don't want to make it tempting to press this.

#### Bug Fixes
- Fixes the logic of the decay timers so that they don't go negative.
- Deletes the balloon activity. I previously thought that fighting a grunt or a leader in a balloon counted separately from battling at a pokestop. We finally determined that I was wrong. Grunts are grunts. Leaders are leaders. Balloons have no bearing on the issue whatsoever.

<br>

### **Version 0.0.1+5**

#### What's New
- Show n/32 points in the points tile, instead of just showing the number of points. This is not good design, but it is at least an indicator for those who aren't intimately familiar with the emotional points algorithm of how far they have to go to get their double hearts.

#### Bug Fixes
- Fixes a bug in the decay timer. If you restarted the app, the decay timer would start at the top, instead of accounting for the time that has passed since your last activity.

### **Version 0.0.1+4**

#### Bug Fixes
- Makes it so cooldown timers don't go negative.

<br>

### **Version 0.0.1+3**

#### Bug Fixes
- Fixes the cooldown timers so that they start at the right time when you kill and restart the app.

<br>

### **Version 0.0.1+2**

#### What's New
- This changes the color of the 'reset' button and moves it from the bottom of the screen to the top. Where previously the 'reset' button was the most obvious button around, this makes it a bit less tempting to press, avoiding accidental resets.

#### Bug Fixes
- When you background the app and then bring it back to the foreground, the timers now take elapsed time into account, instead of just pretending that the backgrounding never happened and continuing where they left off. It sure is nice to test on a real device!

<br>

### **Version 0.0.1+1**
This is the very first release of a barely functional app, to a single test user.
