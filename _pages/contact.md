---
layout: single
title: Contact
date: null
type: page
published: true
status: publish
permalink: /contact/
categories: []
tags: []
---

<form action="https://formspree.io/f/mnqlvgwq" method="POST">
  <label for="name">Name:</label>
  <input type="text" id="name" name="user_name" />
  <label for="mail">E-mail:</label>
  <input type="email" id="mail" name="user_mail" />
  <label for="msg">Message:</label>
  <textarea id="msg" name="user_message"></textarea>
  <button type="submit">Send your message</button>
  <input type="hidden" name="_next" value="/thank-you" />
  <input
    type="hidden"
    name="_subject"
    value="New submission from contact form"
  />
  <input type="hidden" name="_cc" value="darunabas@gmail.com" />
</form>
