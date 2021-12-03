---
layout: essay
type: essay
title: Best Pratices
# All dates must be YYYY-MM-DD format!
date: 2021-12-02
labels:
  - Design patterns
  - automation
---
## What is a Design Pattern?

“What is a design pattern” is already a question on loose footing. First you would think what kind of person asks this question. Then where did design patterns come from and are they still being talked about and used. One way to track this is to look at the literature being published on the subject. It seems that books on design patterns leveled off in the early 2000’s. Quickly scanning those top [eight](https://realtoughcandy.com/best-design-patterns-books/), [sevens](https://medium.com/javarevisited/7-best-books-to-learn-design-patterns-for-java-programmers-5627b93eefdb), [fives](https://www.journaldev.com/7229/best-design-patterns-book) lists for “Best Design pattern books” one of the newest books I saw on any of the lists was published about a decade ago in 2012, Most were from around 2004. So either all design patterns were figured out so there was no need to publish anything else, people just stopped using them (unlikely since I was just asked about it) or the terminology changed. I am inclined to think that the terminology has changed. Looking at the book published in 2012 I got an idea of what word replaced “Design Patterns”. The book was titled [“Real World Java EE Patterns-Rethinking Best Practices”](http://realworldpatterns.com/). Now best practices and design patterns aren’t a one to one match but they do hit a lot of the same beats. They both act as guidelines on how to quickly setup systems without having to reinvent the wheel. You know how something should be done and how to set it up. They are both helpful in planning out a system or project. I think that a design pattern has a more concrete definition than best practice but they’ve gotten clumped together in recent years. An easy way to see it is that all design patterns are best practices but not all best practices are design patterns.

## Design Pattern Implementations

<img class="ui medium right floated rounded image" src="../images/MVC.PNG">
An example of a widely used design pattern is a model view controller. This design pattern is often implemented in user interfaces and breaks it down into three components: model, view and a controller. 
The model contains the information to be displayed, the viewer displays the model and changes based on user interaction and the controller determines what results from user interaction. An example from my own work would be the temperature notification system that I just set up. The viewer shows if a switch is on or off. <img <img class="ui huge rounded image" src="../images/viewer DesignP.PNG">

It gets this information from an object that stores the state “ON” or “OFF”. <img class="ui huge right floated rounded image" src="../images/Model DesignP.PNG">
It is then checked by the controller to see if the state has changed or the temperature threshold had been reached. In this case input is collected from an external temperature sensor.

```py
while 0==0:

  # the sample method will take a single reading and return a
  # compensated_reading object
  bmeData = bme280.sample(bus, address, calibration_params)
  tempF = (round(bmeData.temperature+1)*(9.0/5.0)+32)
  print(tempF)
  print(bmeData.temperature+1)
  print(round(tempF))

  try:
    headers = {
      'Accept': 'application/json',
    }

    requests.get('http://192.168.1.110:8080/rest/items/Alexa_TTS', headers=headers)
    getStateTemp = requests.get('http://192.168.1.110:8080/rest/items/TempState', headers=headers)
    if tempF < 70.0 and getStateTemp.json()["state"] == 'OFF':
      try:
        headers = {
          'Content-Type': 'text/plain',
          'Accept': 'application/json',
        }
        print(tempF)
        temp = str(round(tempF))
        #data = ('The temperature is: %s degrees' % temp)
        data = ('Alert: The temperature has dropped below 70 degrees. Alert')
        turnOn = 'ON'

        requests.post('http://192.168.1.110:8080/rest/items/Alexa_TTS', headers=headers, data=data)
        setState = requests.post('http://192.168.1.110:8080/rest/items/TempState', headers=headers, data=turnOn)
      except:
        print('not connected yet')
    if tempF >= 70.0 and getStateTemp.json()["state"] == 'ON':
      try:
        headers = {
          'Content-Type': 'text/plain',
          'Accept': 'application/json',
        }
        print(tempF)
        temp = str(round(tempF))
        data = ('Alert: The temperature has risen above 70 degrees. Alert')
        turnOff = 'OFF'

        requests.post('http://192.168.1.110:8080/rest/items/Alexa_TTS', headers=headers, data=data)
        setState = requests.post('http://192.168.1.110:8080/rest/items/TempState', headers=headers, data=turnOff)
      except:
        print('not connected yet')
  except:
    print("openhab not running")
  time.sleep(5)
```
