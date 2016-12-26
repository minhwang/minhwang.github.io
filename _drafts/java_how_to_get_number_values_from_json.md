---
layout: post
title:  "[JAVA] How to get the value as number from JSON"
categories: development java
---

JSONObject res = (JSONObject)jsonParser.parse(response.getBodyAsString());
			long until = res.getAsNumber("until").longValue();