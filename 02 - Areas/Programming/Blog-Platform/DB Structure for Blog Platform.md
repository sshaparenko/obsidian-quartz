---
date: 2024-04-09T15:15
tags: 
cssclasses:
  - center-titles
  - recolor-images
  - pen-purple
---

# DB Structure

![[Pasted image 20240409163719.png]]

**FOLLOW LOGIC**
In order to implement user following logic there is a table `FOLLOWS` that connect follower with followed user.

There are a couple scenarios that should be considered:
- Restricting user from following on itself
- When a user is deleted => all rows from `FOLLOWS` should be deleted
- User can follow another user only once
- Since the search in follows will be performed on `follower_id` and `followed_id` we should implement indexes from this columns

	**PROCEDURES TO IMPLEMENT**
	
	`p_followers_number(number user_id)` - return a numbers of followers accounts 
	
	`p_followed_number(number user_id)` - return number of followed accounts

	

**FEED LOGIC**
- User should see posts of the users he is following
- Posts are shown based on date and time of their creation
- Posts are loading based on 10 post pagination
- If there are more that 5 posts posted => user should be able to update the feed