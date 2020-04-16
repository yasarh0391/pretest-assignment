# pretest-assignment
Q. Programming Pre-Screen
Conference room scheduling.
Find the nearest open conference room for a team in which a team can hold
its meeting. Given n team members with the floor on which they work and
the time they want to meet, and a list of conference rooms identified by
their floor and room number as a decimal number, maximum number of
people it fits and pairs of times they are open - find the best place for
the team to have their meeting. If there is more than one room available
that fits the team at the
chosen time then the best place is on the floor the closest to where the team
works.
E.g.
rooms.txt
7.11,8,9:00,9:15,14:30,15:00
8.23,6,10:00,11:00,14:00,15:00
8.43,7,11:30,12:30,17:00,17:30
9.511,9,9:30,10:30,12:00,12:15,15:15,16:15
9.527,4,9:00,11:00,14:00,16:00
9.547,8,10;30,11:30,13:30,15:30,16:30,17:30
Input: 5,8,10:30,11:30 # 5 team members, located on the 8th floor,
meeting time 10:30 - 11:30
Output:
9.547
Please explain: how you solved the problem and how it would behave based
on the different parameters (number of team members, longer meeting
times, many rooms with random booking times). How would you test the
program to ensure it always produced the correct results?
For extra credit, can you improve the solution to split the meeting across
more than one room if say only one room is available for a fraction of the
meeting and another room is free later to hold the remainder of the meeting
during the set time. If you want to make this more powerful - assume that
the number of room splits can happen in proportion to the length of the
meeting so that say if a meeting is 8 hrs long then the algorithm could
schedule it across say up to 4 rooms if a single room was not available for
the whole time.

Ans: def roomSearch(n,f,s,e):
row = data.loc[(data['Start Time']==s) & (data['End Time']==e)]
if (n < row['Max People'].array):
return row['Floor'],row['Room']
else:
print('No room available')

-Floor,Room,Max People,Start Time,End Time
 7,11,8,0900,0915
 7,11,8,1430,1500
 8,23,6,1000,1100
 8,23,6,1400,1500
 8,43,7,1130,1230
 8,43,7,1700,1730
 9,511,9,0930,1030
 10,501,9,1030,1130
 9,511,9,1200,1215
 9,511,9,1515,1615
 9,527,4,0900,1100
 9,527,4,1400,1600
 9,547,8,1030,1130
 9,547,8,1330,1530
 9,547,8,1630,1730

Function takes number of people n, floor f, start time s and end time e as
inputs.
First locates based on the start time and end time.
Then checks if it has the capacity for people and returns the floor and room.
Super basic.
For next part to pick nearest room, explain we can do a binary search to find
nearest floor in case there is more than 1 room on different floor.

There will always be room to improve. I believe in refining and tuning the
product to best meet the goals. For scheduling a conference, we can refine
the code further.

1. Use Greedy algorithm to further address splitting the meeting in different
rooms for the entire day. Nearest floor will again take priority as it is good
time management
2. Instead of printing no rooms available, we can suggest conference rooms
that have similar time slot availability.
3. If there are two conference rooms available on same floor, allocate the
room that fills up first. Like two rooms available with max people of 6 & 7
and you have only have 5 people allocate the room with max people of 6.

FYI – please see the code below & will attached the code file.
