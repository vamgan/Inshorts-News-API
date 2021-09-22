# Inshorts API

Inshorts is an app which provides news from different sources and presents them under 60 words. This API Scraps content from the Inshorts website and provides it in easy to use JSON Format. 

## Categories

Supports all categories as on the Inshorts Website. These include - 

1. '' // blank to get top news from all categories
2. national //Indian National News
3. business
4. sports
5. world
6. politics
7. technology
8. startup
9. entertainment
10. miscellaneous
11. hatke // Unconventional
12. science
13. automobile

## Usage

### 1. GET Request

Make a get request of the form 
```
https://inshorts-api.herokuapp.com/news?category={category_name}
```

[Click here to see sample for category sports](https://inshorts-api.herokuapp.com/news?category=sports)

### 2. POST Request

Make a post request with the category, provided as form data with name 'category' to the same route as above i.e '/news'.

## Response Format

The response JSON Object looks something like this - 

```JSON
{
    "category":"",
    "data":[
        {
            "author":"Roshan Gupta",
            "content":"Over the past 18 months, professionals worldwide achieved phenomenal salary hikes, promotions & career changes with Simplilearn, the online learning platform revealed. It offers Bootcamp programs in partnership with top universities and firms and has helped millions of learners upskill in Data & AI, Full Stack Development, Digital Marketing, MBA, other digital economy job areas, Simplilearn added.",
            "date":"22 Sep",
            "imageUrl":"https://static.inshorts.com/inshorts/images/v1/variants/jpg/m/2021/09_sep/21_tue/img_1632243978497_14.jpg?",
            "readMoreUrl":"https://inshorts.com/safe_redirect?url=https%3A%2F%2Fwww.simplilearn.com%2F%3Futm_source%3DInShorts%26utm_medium%3Db2c-leadgen%26utm_campaign%3DInShorts-SLBrandMotivator&inshorts_open_externally=true ",
            "time":"09:00 am",
            "title":"\nNow achieve your biggest career goals: Simplilearn\n",
            "url":"https://www.inshorts.com/en/news/now-achieve-your-biggest-career-goals-simplilearn-1632281403710"
        },
        {
            "author":"Anmol Sharma",
            "content":"Ex-India captain Sunil Gavaskar criticised Punjab Kings for not playing Chris Gayle against Rajasthan Royals on the occasion of the West Indian's 42nd birthday. \"He has dominated every single T20 league and you drop him for this game on his birthday makes zero sense,\" Gavaskar said. Meanwhile, Kevin Pietersen said, \"I can't understand PBKS' thinking at all.\"",
            "date":"22 Sep",
            "imageUrl":"https://static.inshorts.com/inshorts/images/v1/variants/jpg/m/2021/09_sep/22_wed/img_1632280365719_940.jpg?",
            "readMoreUrl":"https://www.hindustantimes.com/cricket/makes-0-sense-questions-will-be-asked-pietersen-gavaskar-astonished-as-punjab-kings-omit-gayle-on-42nd-birthday-101632232586594-amp.html?utm_campaign=fullarticle&utm_medium=referral&utm_source=inshorts ",
            "time":"08:54 am",
            "title":"\nPunjab Kings dropping Gayle on his birthday makes zero sense: Sunil Gavaskar\n",
            "url":"https://www.inshorts.com/en/news/punjab-kings-dropping-gayle-on-his-birthday-makes-zero-sense-sunil-gavaskar-1632281041444"
        },
        {
            "author":"Anmol Sharma",
            "content":"RR's 20-year-old pacer Kartik Tyagi took two wickets and defended four runs off the last over to help his team defeat PBKS by 2 runs in their IPL 2021 encounter. With the victory, RR moved to fifth position on the points table with eight points in eight matches. RR put up a total of 185/10 before restricting PBKS to 183/4.",
            "date":"21 Sep",
            "imageUrl":"https://static.inshorts.com/inshorts/images/v1/variants/jpg/m/2021/09_sep/21_tue/img_1632247979154_374.jpg?",
            "readMoreUrl":"https://www.iplt20.com/match/2021/32?tab=scorecard&utm_campaign=fullarticle&utm_medium=referral&utm_source=inshorts ",
            "time":"11:53 pm",
            "title":"\n20-year-old Kartik Tyagi defends 4 runs off last over as RR defeat PBKS by 2 runs\n",
            "url":"https://www.inshorts.com/en/news/20yearold-kartik-tyagi-defends-4-runs-off-last-over-as-rr-defeat-pbks-by-2-runs-1632248634570"
        },
    ],
    "success": true
}
```

Each response object has the following keys -

1. **success** - true indicates the api ran successfully. Upon error the success value is false and the object includes an errorMessage key with the error message.

    ```JSON
    {
        "category": "sciencedfg",
        "data": [],
        "errorMessage": "Invalid Category",
        "success": false
    }
    ```

2. **category** - the category you requested for.

3. **data** - An array of objects each containing a news item for the category. Each object contains 
    * title 
    * content
    * author 
    * imageUrl 
    * readMoreUrl(link to original news article)
    * date and time of publish
    * url (link to inshorts page)



