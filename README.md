# Utilizando AI Search para indexação e consulta de dados através do Azure AI Services 📑

Este projeto foi desenvolvido durante o Bootcamp Microsoft Azure AI Fundamentals da DIO. O objetivo é experimentar os recursos do [Azure AI Services](https://azure.microsoft.com/en-us/products/ai-services/).

## ✨ Passo-a-passo
- Criar uma conta no Azure;
- Criar um recurso do tipo Azure AI Search;
- Criar um recurso do tipo AI services;
- Criar uma conta de armazenamento em Storage Accounts;
- Permitir acesso anonimo ao Storage Account criado;
- Ainda no Storage Account criado, adicionar um novo container com acesso anônimo de leitura;
- No container, fazer upload das reviews anexadas na documentação usada como referência;
- Retornar para o primeiro recurso criado do tipo Azure AI Search e importar dados do container;
- Ir para o Search Explorer para testar uma consulta feita em JSON:

#### Exemplo de entrada da consulta:

```
{
 "search": "locations:'Chicago'",
 "count": true
}
```

#### Exemplo de saída da consulta:

```
{
  "@odata.context": "https://ai-cognitive-search-test-dio.search.windows.net/indexes('coffee-index')/$metadata#docs(*)",
  "@odata.count": 3,
  "value": [
    {
      "@search.score": 2.3650222,
      "content": "\nReview: I often make Fourth Coffee my meeting spot for my client meetings weekday mornings. I own a small business and the folks who work at Fourth Coffee are always very friendly. It leaves a good impression on my clients. There are also plenty of drink selections, good wi-fi, and seating. Some of my favorite coffees are the lavender honey latte and, in the winter, the apple-chai latte. There are delicious baked goods offered as well. \nDate: October 21, 2018\nLocation: Chicago, Illinois \n\nimage1.png\n\n\n\n",
      "metadata_storage_path": "aHR0cHM6Ly9haWNvZ25pdGl2ZXNlYXJjaGFjY291bnQuYmxvYi5jb3JlLndpbmRvd3MubmV0L2NvZmZlcmV2aWV3cy9yZXZpZXctNS5kb2N40",
      "locations": [
        "meeting spot",
        "Chicago",
        "Illinois"
      ],
      "keyphrases": [
        "delicious baked goods",
        "lavender honey latte",
        "apple-chai latte",
        "Fourth Coffee",
        "meeting spot",
        "client meetings",
        "small business",
        "good impression",
        "drink selections",
        "good wi",
        "favorite coffees",
        "Review",
        "mornings",
        "folks",
        "clients",
        "plenty",
        "fi",
        "seating",
        "winter",
        "Date",
        "October",
        "Location",
        "Chicago",
        "Illinois"
      ],
      "sentiment": "[\"positive\"]",
      "merged_content": "\nReview: I often make Fourth Coffee my meeting spot for my client meetings weekday mornings. I own a small business and the folks who work at Fourth Coffee are always very friendly. It leaves a good impression on my clients. There are also plenty of drink selections, good wi-fi, and seating. Some of my favorite coffees are the lavender honey latte and, in the winter, the apple-chai latte. There are delicious baked goods offered as well. \nDate: October 21, 2018\nLocation: Chicago, Illinois \n\nimage1.png\n  \n\n\n",
      "text": [
        ""
      ],
      "layoutText": [
        "{\"language\":\"en\",\"text\":\"\",\"lines\":[],\"words\":[]}"
      ],
      "imageTags": [
        "clothing",
        "person",
        "furniture",
        "human face",
        "chair",
        "table",
        "woman",
        "indoor",
        "window",
        "desk",
        "sitting",
        "people",
        "restaurant"
      ],
      "imageCaption": [
        "{\"tags\":[\"person\",\"woman\",\"laptop\",\"dish\"],\"captions\":[{\"text\":\"a woman showing a woman something on a tablet\",\"confidence\":0.513512134552002}]}"
      ]
    },
    {
      "@search.score": 1.0858147,
      "content": "\n\nReview: The coffee tastings every Wednesday afternoon are so fun. Each month there is a new drink theme. You do need to book a spot in advance to attend. It is very worth it! I also love their local music. Fourth Coffee brings in rising artists every weekend. I like to head over there mid-afternoon on weekdays when it’s not too busy and get a slice of pie or their seasonal baked goods.  \nDate: August 13, 2018\nLocation: Chicago, Illinois  \n\nimage1.png\n\n\n\nimage2.png\n\n\n\n",
      "metadata_storage_path": "aHR0cHM6Ly9haWNvZ25pdGl2ZXNlYXJjaGFjY291bnQuYmxvYi5jb3JlLndpbmRvd3MubmV0L2NvZmZlcmV2aWV3cy9yZXZpZXctNC5kb2N40",
      "locations": [
        "Fourth Coffee",
        "Chicago",
        "Illinois"
      ],
      "keyphrases": [
        "new drink theme",
        "seasonal baked goods",
        "coffee tastings",
        "local music",
        "Fourth Coffee",
        "rising artists",
        "ierican Coffee",
        "Review",
        "afternoon",
        "spot",
        "advance",
        "weekdays",
        "slice",
        "pie",
        "Date",
        "August",
        "Location",
        "Chicago",
        "Illinois"
      ],
      "sentiment": "[\"positive\"]",
      "merged_content": "\n\nReview: The coffee tastings every Wednesday afternoon are so fun. Each month there is a new drink theme. You do need to book a spot in advance to attend. It is very worth it! I also love their local music. Fourth Coffee brings in rising artists every weekend. I like to head over there mid-afternoon on weekdays when it’s not too busy and get a slice of pie or their seasonal baked goods.  \nDate: August 13, 2018\nLocation: Chicago, Illinois  \n\nimage1.png\n ierican Coffee 114 10148/0034 \n\n\nimage2.png\n  \n\n\n",
      "text": [
        "ierican Coffee 114 10148/0034",
        ""
      ],
      "layoutText": [
        "{\"language\":\"en\",\"text\":\"ierican Coffee 114 10148/0034\",\"lines\":[{\"boundingBox\":[{\"x\":701,\"y\":284},{\"x\":649,\"y\":303},{\"x\":647,\"y\":297},{\"x\":699,\"y\":279}],\"text\":\"ierican Coffee\"},{\"boundingBox\":[{\"x\":682,\"y\":241},{\"x\":614,\"y\":263},{\"x\":611,\"y\":251},{\"x\":678,\"y\":228}],\"text\":\"114 10148/0034\"}],\"words\":[{\"boundingBox\":[{\"x\":701,\"y\":285},{\"x\":679,\"y\":293},{\"x\":676,\"y\":287},{\"x\":699,\"y\":279}],\"text\":\"ierican\"},{\"boundingBox\":[{\"x\":676,\"y\":294},{\"x\":652,\"y\":303},{\"x\":650,\"y\":297},{\"x\":674,\"y\":288}],\"text\":\"Coffee\"},{\"boundingBox\":[{\"x\":682,\"y\":242},{\"x\":672,\"y\":245},{\"x\":668,\"y\":232},{\"x\":678,\"y\":229}],\"text\":\"114\"},{\"boundingBox\":[{\"x\":669,\"y\":245},{\"x\":618,\"y\":262},{\"x\":615,\"y\":251},{\"x\":666,\"y\":233}],\"text\":\"10148/0034\"}]}",
        "{\"language\":\"en\",\"text\":\"\",\"lines\":[],\"words\":[]}"
      ],
      "imageTags": [
        "food",
        "chocolate",
        "table",
        "cup",
        "serveware",
        "indoor",
        "cocoa solids",
        "caffeine",
        "tableware",
        "sitting",
        "coffee",
        "dessert",
        "musical instrument",
        "music",
        "concert",
        "clothing",
        "person",
        "string instrument",
        "human face",
        "microphone",
        "plucked string instruments",
        "acoustic guitar",
        "guitar",
        "indoor",
        "woman"
      ],
      "imageCaption": [
        "{\"tags\":[\"cup\",\"coffee\",\"table\",\"indoor\",\"pastry\",\"beverage\",\"breakfast\",\"close\"],\"captions\":[{\"text\":\"a group of small cups with brown liquid in them\",\"confidence\":0.39556038379669189}]}",
        "{\"tags\":[\"person\",\"music\",\"guitar\",\"bowed instrument\",\"bass\"],\"captions\":[{\"text\":\"a person playing a guitar\",\"confidence\":0.54444891214370728}]}"
      ]
    },
    {
      "@search.score": 0.96866095,
      "content": "Review: Today I was truly disappointed with how long I had to wait for the pastries I ordered ahead of time. When I got my box, some of the pastries seemed stale. Terrible experience!  \nDate: October 23, 2018\nLocation: Chicago, Illinois \n\n",
      "metadata_storage_path": "aHR0cHM6Ly9haWNvZ25pdGl2ZXNlYXJjaGFjY291bnQuYmxvYi5jb3JlLndpbmRvd3MubmV0L2NvZmZlcmV2aWV3cy9yZXZpZXctOC5kb2N40",
      "locations": [
        "Chicago",
        "Illinois"
      ],
      "keyphrases": [
        "Terrible experience",
        "Review",
        "pastries",
        "time",
        "box",
        "Date",
        "October",
        "Location",
        "Chicago",
        "Illinois"
      ],
      "sentiment": "[\"negative\"]",
      "merged_content": "Review: Today I was truly disappointed with how long I had to wait for the pastries I ordered ahead of time. When I got my box, some of the pastries seemed stale. Terrible experience!  \nDate: October 23, 2018\nLocation: Chicago, Illinois \n\n",
      "text": [],
      "layoutText": [],
      "imageTags": [],
      "imageCaption": []
    }
  ]
}
```

## 📷
![json_view_query](https://github.com/jkss13/Azure-AI-Search-Service-Introduction-Test/assets/89669182/28612ea5-3600-44a3-aff3-8ba985dd583d)


### Referência
[Azure AI Search Index](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html)
