Here you find all characters of the Tenfait world.
Each character is represented in the following format:
```
{
  "name":"The name of the character",
  "title":"Dragon Slayer",
  "fullName":"Name the Dragon Slayer",
  "aliases":["aka","nickname"],
  "nameHistory":["previous Name","childhood name"],
  "locationOfBirth":"Dragon City",
  "job":"worker",
  "passions":["farming","riding dragons"],
  "dialoge":[
    {
      "id":"start",
      "says":"Hello Who are you?",
      "options":[
        {
          "text":"Hello I am {name}",
          "triggers":"dialogId1"
        },
        {
          "text":"I don't want to tell you",
          "triggers":"dialogId2"
        },
        {
          "text":"I am a hero",
          "triggers":"dialogId3"
        }
      ]
    },
    {
      "id":"dialogId1",
      "says":"Hello {name}, Have a nice day",
      "options":[
        {
          "text":"Thanks, bye",
          "triggers":"end"
        }
      ]
    },
    {
      "id":"dialogId2",
      "says":"Okay, bye",
      "options":[
        {
          "text":"bye",
          "triggers":"end"
        }
      ]
    },
    {
      "id":"dialogId3",
      "says":"Wow, I have a quest for you",
      "options":[
        {
          "text":"No thanks",
          "triggers":"dialog2"
        },
        {
          "text":"Accept the quest",
          "triggers":"end"
        }
      ]
    },
    {
      "id":"start",
      "requires":{"quest":"questid","stateMin":1,"stateMax":2},
      "text":"Thanks for your help",
      "options":[
        "text":"No probelm",
        "triggers":"reward"
      ]
    }
  ]
}

```

A quest looks like
```
{
  "id":"questId",
  "name":"A lost child",
  "description":"A child got lost in the woods, find it",
  "states":[
    {
      "requirement":
      [
        {
          "type":"find",
          "entity":"entityId"
        }
      ]
    }
  ]
}
```

A NPC will allways attempt to find dialog that requires a quest the user is currently in.
If there are multiple open quests He will ask you `What are you here for?` `QuestName A` or `Quest B` based on the name of the quest.
