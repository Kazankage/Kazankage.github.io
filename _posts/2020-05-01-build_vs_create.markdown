---
layout: post
title:      "#build vs #create"
date:       2020-05-01 18:21:03 +0000
permalink:  build_vs_create
---


While doing my rails review I was asked what a good alternative to #create would be. 

The answer was #build

#build is an ActiveRecord method often used with associations. Similar to #create, #build returns new objects of the association. The object will be instantiated from the attributes, and a link is made throught the foreign key. It does not, like #create, however, save. #create essentially does the same thing, but when #create is run, the objects are saved ready to be used with their respective associations, and the child is given an id. 

Let me give you an example of this in a non-technical way:

You are a barista at Starbucks. Someone comes in and orders a caramel frappuccino. You know the standard recipe for one so you go ahead and make it quickly, and send it on its way (#create). A few minutes later  you remembered the person who ordered it asked for extra caramel on the drink. It would be tedious to go and ask for the drink back and add more caramel then hand it off again. Next time you could wait before handing the drink out to see if you needed to add or take away something (#build) then hand it out. 

The difference between #build and #create is that create also saves the created object as build only returns the newly created object (without it being saved yet).

New objects can be instantiated as either empty (pass no construction parameter) or pre-set with attributes but not yet saved (pass a hash with key names matching the associated table column names).

A live example:

`User.last = x`
>   => User Load (0.2ms)  SELECT "users".* FROM "users" ORDER BY "users"."id" DESC LIMIT ?  [["LIMIT", 1]]
>  => #<User id: 8, username: "Kazekage", password_digest: [FILTERED], email: "Kazekage@kage.com", created_at: "2020-04-11 20:45:15", updated_at: "2020-04-11 20:45:15"> 

Then I run

`x.mangas.build(:series => "Naruto")`

I can see that this object is already associated with a user_id, but is not given a manga_id

> => #<Manga id: nil, series: "Naruto", description: nil, link: nil, publishers: nil, genre_id: nil, user_id: 8, created_at: nil, 
> updated_at: nil>> 2.6.1 :047 > 
 
It is not saved. So if I were to call on that particular user, and ask for the Manga's that they have, "Naruto" would not be on the list.

If I were to run that code with #create: `x.mangas.create(:series => "Naruto")`

> <Manga id: 15, series: "Naruto", description: "nil", link: nil, publishers: "nil", genre_id: 3 user_id: 8, created_at: "2020-05-01 
> 17:40:28", updated_at: "2020-05-01 17:40:28"> 
> 2.6.1 :069 > 

You can see it was given a manga_id and was saved.


