import json
import requests
import pprint


json = requests.get("https://raider.io/api/v1/mythic-plus/runs?season=season-7.3.0&region=world&dungeon=all").text
#keep the above line so you can paste into json viewer

# whatisthis = requests.get("https://raider.io/api/v1/raiding/raid-rankings?raid=Tomb%20of%20Sargeras&difficulty=Mythic&region=us")
response = requests.get("https://raider.io/api/v1/mythic-plus/runs?season=season-7.3.0&region=world&dungeon=all").json()

print(json)

# pp = pprint.PrettyPrinter(indent=2)
# pp.pprint(response)
# print(response['raidRankings'][0]['guild']['region']['name'])
# print(response['raidRankings'][0])

rankCount = len(response['rankings']) #The amount of dictionaries in rankings

death_knight_tanks = []
i = 0
def dktank():
    global i # <--- declare `i` as a global variable
    for ranking_group in response["rankings"]:
        # Go through all the roster members in the group
        for roster_member in ranking_group["run"]["roster"]:
            # If it's a tank and a Death Knight, add it to our list
            if roster_member["role"] == "tank" and roster_member["character"]["class"]["name"] == "Death Knight":
                death_knight_tanks.append(roster_member)
                
                #optional arguments to use to see more stuff
                # print(i)
                # print(roster_member["character"]["class"]["name"])
                

# next()
dktank()
print("Number of classes found: ", len(death_knight_tanks))


# i = 0
#
#      for roster_member in response["rankings"][i]["run"]["roster"]:
#          if roster_member["role"] == "tank":
#             i+=1
#             print(i)
#             print(roster_member["character"]["name"])

