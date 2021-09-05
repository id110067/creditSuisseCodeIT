# creditSuisseCodeIT



Problem Statement!!


Entry Challenge
It is the year 2038 and robots have the right to get paid for the work they do. As an
employer of robots, you need to calculate how much a robot gets paid for cleaning your
apartment.
How much a robot gets paid depends on when you ask the robot to work. After all, during
the day the robot can be a little louder and work a bit faster whilst everyone is out of the
house, but at night, you will need to turn on the super quiet mode, which takes more effort!
Robots also cost a bit more over weekends, due to higher demand.

2

Your robot rates calculator needs to consider the following:
• A standard minutely rate for weekdays, and an ‘extra’ rate for weekends.
• When rates switches between day and night rates, for a total of four different rates
(weekday/weekend + day/night).
• For every eight hours, the robot needs to take an hour of unpaid break (or part thereof)
for planned system maintenance.
Implement an application that can take in an input like the example below, and provide an
output as shown:
{
"shift": {
"start": "2038-01-01T20:15:00",  // we can use time library
"end": "2038-01-02T04:15:00"
},
"roboRate": {
"standardDay": {
"start": "07:00:00",
"end": "23:00:00",
"value": 20
},
"standardNight": {
"start": "23:00:00",
"end": "07:00:00",
"value": 25
},
"extraDay": {
"start": "07:00:00",
"end": "23:00:00",
"value": 30
},
"extraNight": {
"start": "23:00:00",
"end": "07:00:00",
"value": 35
}
}
}
Sample output:
{ "value": 13725 }


//20 for 2 and 45 minutes and 25 for 5 hours and 15 minutes

// Calculation as 1 januaray is friday which is standard day hence the day hours are 2hours and 45 minutes = 165 minutes at a rate of 20 per minute
// standard night rate was 25 which robot on friday worked for 1 hour --> 60 * 25
// For extra day as 2nd januray is saturday, then robot works extra 4 hours 15 minutes = 255 minutes at a rate of 35 minutes

Additional test cases for the sample rates above:
Start End Expected value
2038-01-01T20:15:00 2038-01-02T08:15:00 19650
2038-01-11T07:00:00 2038-01-17T19:00:00 202200
2038-01-01T20:15:00 2038-01-02T04:16:00 13725
2038-01-01T20:15:00 2038-01-02T05:16:00 13760
The problem statement has not been completely described - you should provide comments on
any other assumptions you have made on top of these two:
1. Shift timestamps will be given in ISO format “yyyy-MM-dd’T’hh:mm:ss”, rates in “hh:mm:ss”.
2. Duration boundaries are [inclusive, exclusive), e.g. a shift from 7 am to 11 pm will fit into a
single day rate, without incurring a minute of the night rate.
Assessors will be considering code-readability, implementation and assumptions including
checks/validations that your application performs. You are allowed to use third-party libraries.
