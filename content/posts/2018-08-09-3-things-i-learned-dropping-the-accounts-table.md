+++
title = "3 things I learned the day I dropped the accounts table"
date = 2018-08-09T05:15:38+00:00
slug = "3-things-i-learned-dropping-the-accounts-table"
template = "page.html"

[extra]
hero_image = "/images/broken-plate.jpeg"
+++
<p>I <em>really</em> identify with the mantra &quot;move fast and break things&quot;.  Everything in moderation of course - like don't move so fast that you break all the things.  But as an engineer, I've had my greatest success by bringning things to the business/management and effectively saying:  hey, I built all this cool stuff - do you think you can sell it?</p>
<p>Early in my career I was learning the ropes as a DBA at a financial company.  I was working on a new data load that would create new <code>Accounts</code> in our database.  To simplify things and protect the innocent this is how it went down:  I was loading the data into an <code>Accounts_Temp</code> table and working in a staging connection string.  I was writing some raw MS SQL to <code>Truncate Accounts_Temp</code> and do a <code>BULK INSERT</code>.  Of course if you happened to forget that <code>_Temp</code> part and inadvertenty ran that against the wrong connection string...<em>you just truncated the primary accounts table of a major financial company</em>.</p>
<p>So yeah - a lot of things went wrong.  I shouldn't have had truncate access to prod. I should have realized I was on prod.  Lots of things should have been different.  This isn't about all the things that went wrong.  This is about all the things that went <em>right</em> that day.</p>
<p>It takes a few seconds.  Then the realization creeps in.  &quot;That wasn't production...was it?&quot;  Followed quickly by, &quot;I can fix this. I can fix this. I can fix this.&quot;  <em>You most certainly cannot fix this.</em>  At least not on your own.</p>
<p>In that moment you have choices.  I paused, pannicked, and ran right into my boss' office.  &quot;I just dropped the accounts table, what should we do?!?&quot;.  In the following 2 hours I learned more about being a DBA than in the previous 6 months.  We did a partial, live restore of a single table with minimal data loss.  <strong>It.  Was.  Awesome.</strong></p>
<p>The things I learned that day:</p>
<ol>
<li>
<p>Make tragic mistakes hard to do.  Don't let people make drastic mistakes easily.  Things like truncating data or deploying to master should have checkpoints along the way.</p>
</li>
<li>
<p>When you make a big mistake tell someone right away!  Imagine if I hadn't.  The team might have spent hours - or longer - trying to figure out what happened.  Is there a software bug?  Were we hacked?</p>
</li>
<li>
<p>Let people make mistakes.  If I was afraid of getting fired or berated for my mistake - I might have acted differently.  Because I knew my boss was supportive of me, I knew I could come to him.  I could tell him what I did wrong.  I didn't fear being mocked or belittled or fired due to this one mistake.</p>
</li>
</ol>
<p>As I've progressed in my career I've found the first one is pretty easy.  It's a computer problem - we have gotten pretty good at solving those.  The tricky part is the balance.  How can you protect your team from mistakes but still give them freedom to move quickly?</p>
<p>The second two are people problems.  Those are more complicated.</p>
<p>Make sure your team knows they won't be dragged across the coals for their mistakes.  When something does go wrong - focus on the problem - what happened, how can we solve it.  Don't focus on who did it.  Today it might be Developer A but tomorrow it could easily be Developer B.  What are the processes and procedures that allowed the mistake to happen.</p>
<p>Any conversations about negative performance should be in private.  Never call people out in front of their peers.</p>
<p>I try to emphasize to my team - I'm looking at the long view, not the short view.  You're not getting fired for having a bad day.  We all have bad days.  What's your month look like, your quarter - I bet you've contributed significantly.</p>
<p>As a mistake maker - have some confidence along with your humility.  Yes I made this mistake.  But I had the <em>right</em> intentions.  I was trying to do the right thing.  I want to fix this.  I want to get better.  How can we all learn from this?  Write up a retrospective.  Reccommend policy changes to prevent this from happening again.</p>
<p>We've all made mistakes.  Let's create an environment where the really bad mistakes are hard to do and mistakes are both forgivable and recoverable.</p>

