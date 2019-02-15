# easy-prospect-watch

![app](./app.png)

Easy way to create [MLB.com Prospect Watch](http://m.mlb.com/prospects) like prospect ranking.

## Getting Started

``` bash
# clone repository
$ git clone https://github.com/prs-watch/easy-prospect-watch.git easy-prospect-watch
# move into project
$ cd easy-prospect-watch
# install dependencies
$ npm install
# run
$ npm run dev
# generate static resources
$ npm run generate
```

## Edit prospect ranking as you like

Resource of Prospect Ranking is [assets/data.json](https://github.com/prs-watch/easy-prospect-watch/blob/master/assets/data.json). 

```json
{
    "data": [
        {
            "name": "VLADIMIR GUERRERO JR.",
            "team": "TOR",
            "pos": "3B",
            "rank": "1",
            "image": "https://assets3.sportsnet.ca/wp-content/uploads/2018/03/guerrero_vladjr1280-1040x572.jpg",
            "description": "Amazing!"
        },
        {
            "name": "FERNANDO TATIS JR.",
            "team": "SD",
            "pos": "SS",
            "rank": "2",
            "image": "https://cdn-images-1.medium.com/max/1600/1*9-RvXHUlsMa9KkEvwNS-EQ.jpeg",
            "description": "Amazing!"
        },
        {
            "name": "ELOY JIMENEZ",
            "team": "CWS",
            "pos": "OF",
            "rank": "3",
            "image": "http://images.performgroup.com/di/library/sporting_news/e/a0/eloyjimenez-062218-ftr-gettyjpg_uj2x9df2847x1p20hixucbjop.jpg?t=667829276&w=960&quality=70",
            "description": "Amazing!"
        },
        {
            "name": "VICTOR ROBLES",
            "team": "WSH",
            "pos": "OF",
            "rank": "4",
            "image": "https://imagesvc.timeincapp.com/v3/fan/image?url=https%3A%2F%2Fdistrictondeck.com%2Fwp-content%2Fuploads%2Fgetty-images%2F2017%2F07%2F1038899232.jpeg&c=sc&w=850&h=560",
            "description": "Amazing!"
        },
        {
            "name": "KYLE TUCKER",
            "team": "HOU",
            "pos": "OF",
            "rank": "5",
            "image": "https://imagesvc.timeincapp.com/v3/fan/image?url=https://houseofhouston.com/wp-content/uploads/getty-images/2018/03/928216584-houston-astros-v-new-york-mets.jpg.jpg&",
            "description": "Amazing!"
        }
    ]
}

```

Attributes you have to input are following.

|Name|About|
|:--|:--|
|name|Player name.|
|team|Team name.|
|pos|Position name.|
|rank|Ranking the player are on.|
|description|Player's scouting report.|

## Future work

+ Change resource format to csv.
+ Be a web application and support to upload ranking resources online.