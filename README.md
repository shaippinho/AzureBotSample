# Azure Bot Service com CI/CD

## Tecnologias

```
.Net 6
Azure Bot Service
CI/CD
NGrok
Bot Emulator
```
## Fontes: 
Como provisionar Realizar o deploy de um Bot Service no Azure em 2023-> [Deploy Microsoft Azure Bot to Azure App Service](https://www.youtube.com/watch?v=RTq72C10x88)

Como testar o bot via Postman/Insomnia-> [DirectLineAPI - Testing with custom client](https://thewebspark.com/2018/04/15/directlineapi-testing-with-custom-client-and-postman-microsoft-bot-framework/)

Como criar um bot com C# -> [Microsoft Learning Path - Quickstart create bot service](https://learn.microsoft.com/pt-br/azure/bot-service/bot-service-quickstart-create-bot?view=azure-bot-service-4.0&tabs=csharp%2Cvs)

Bot Emulator -> [GitHub - Bot Emulator](https://github.com/microsoft/BotFramework-Emulator)
<details>

<summary>Exemplo payload para teste via DirectLine</summary>

  
1 - POST https://directline.botframework.com/v3/directline/conversations
```json
{
	"Message": ""
}
```
  
Resposta
```json
{
	"conversationId": "2dGb9y2jKNSLrCzfvLwj6B-br",
	"token": "eyJhbGciOiJSUzI1NiIsImtpZCI6IkJZM1pKV3ViOGJIeVdpcTJIaDJVNllFR2oySSIsIng1dCI6IkJZM1pKV3ViOGJIeVdpcTJIaDJVNllFR2oySSIsInR5cCI6IkpXVCJ9.eyJib3QiOiJCb3RBenVsVGVzdGUiLCJzaXRlIjoiQkc5UGI5djVlSVUiLCJjb252IjoiMmRHYjl5MmpLTlNMckN6ZnZMd2o2Qi1iciIsIm5iZiI6MTY4NzMwNjI4NiwiZXhwIjoxNjg3MzA5ODg2LCJpc3MiOiJodHRwczovL2RpcmVjdGxpbmUuYm90ZnJhbWV3b3JrLmNvbS8iLCJhdWQiOiJodHRwczovL2RpcmVjdGxpbmUuYm90ZnJhbWV3b3JrLmNvbS8ifQ.YzEtp073ARDE9qnmqADVXwA5na0dSTjNljg8Juwksnrf3ACCsok-49JamkKLC1ASi5h7zZ1osSf-ijSWshq5Dc1VEWC20AisvU4cM7IJbi8ttuGmr1MU0Gs4h_S7q4uhPYqGwPYVYB8BgMP-ogjE6yBLWzrhS7Tc40DQAjnH-t1ECRqkInXex1ZhXD0OALvyKzH-7aMFR_Yh2PEDefWP65TE9eoz61Bi5yPNA0Ex5q4cKXK62Ec_mmXfhRvF6y68xFUvengh-6DkKzsDu_Uos5h5zJbiZm6vTXXxDY4TkMaFGHhAcahzZ8bHh74w_ief634cJwInyEGYKtDZ4Ub6gw",
	"expires_in": 3600,
	"streamUrl": "wss://directline.botframework.com/v3/directline/conversations/2dGb9y2jKNSLrCzfvLwj6B-br/stream?watermark=-&t=eyJhbGciOiJSUzI1NiIsImtpZCI6IkJZM1pKV3ViOGJIeVdpcTJIaDJVNllFR2oySSIsIng1dCI6IkJZM1pKV3ViOGJIeVdpcTJIaDJVNllFR2oySSIsInR5cCI6IkpXVCJ9.eyJib3QiOiJCb3RBenVsVGVzdGUiLCJzaXRlIjoiQkc5UGI5djVlSVUiLCJjb252IjoiMmRHYjl5MmpLTlNMckN6ZnZMd2o2Qi1iciIsIm5iZiI6MTY4NzMwNjI4NiwiZXhwIjoxNjg3MzA2MzQ2LCJpc3MiOiJodHRwczovL2RpcmVjdGxpbmUuYm90ZnJhbWV3b3JrLmNvbS8iLCJhdWQiOiJodHRwczovL2RpcmVjdGxpbmUuYm90ZnJhbWV3b3JrLmNvbS8ifQ.qKaCEpl0_XtnSUp0czoJCRiyt2_mSbQpBjY-mq8qoTWfBYnaPz_bSAQJjzorms2rl0PFdG_Onbq149-GtNb12MrUMoeMAHKIhETvX8Y-wWIEwXGaKeft0_dwMLodF_uXOz7lcv5K1ou_p1vEWFoy6J0T5LuH3GvsH2h5gbDM1WfMee4m86feqWbSPPd7ugpV7k58a3TPuKzUrmTQbrzi1QS4Sc5d6NHBVY31aHP6B2qVBwh5v_mzT5H7LshEyk_Og5RaI9K4u0wg65tyCizGDAUDC2pRiWk3PenWxAv4JYBNcztLu4g3MMKxa_3yrjqGKJjlC9IGsUSZ0qe8VraTJg",
	"referenceGrammarId": "11a3d88f-bcfb-195e-ba4c-a2a0bb2b8924"
}
```  

2 - POST https://directline.botframework.com/v3/directline/conversations/IVCpaSiSE8JLNEuZ5Mb1Xk-us/activities
```json
{
	"type":"Teste",
	"from": {
			"id":"The Web Spark"
	},
	"text":"create a note"
}
```
  
Resposta
```json
{
	"id": "IVCpaSiSE8JLNEuZ5Mb1Xk-us|0000004"
}
```

 3 - GET https://directline.botframework.com/v3/directline/conversations/IVCpaSiSE8JLNEuZ5Mb1Xk-us/activities
  
Resposta
```json
{
	"activities": [
		{
			"type": "message",
			"id": "IVCpaSiSE8JLNEuZ5Mb1Xk-us|0000000",
			"timestamp": "2023-06-21T00:23:31.9078112Z",
			"channelId": "directline",
			"from": {
				"id": "BotAzulTeste",
				"name": "BotAzulTeste"
			},
			"conversation": {
				"id": "IVCpaSiSE8JLNEuZ5Mb1Xk-us"
			},
			"attachmentLayout": "list",
			"speak": "Welcome to Bot Framework!",
			"inputHint": "acceptingInput",
			"attachments": [
				{
					"contentType": "application/vnd.microsoft.card.adaptive",
					"content": {
						"$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
						"type": "AdaptiveCard",
						"version": "1.0",
						"body": [
							{
								"type": "Image",
								"url": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQtB3AwMUeNoq4gUBGe6Ocj8kyh3bXa9ZbV7u1fVKQoyKFHdkqU",
								"size": "stretch"
							},
							{
								"type": "TextBlock",
								"spacing": "medium",
								"size": "default",
								"weight": "bolder",
								"text": "Welcome to Bot Framework!",
								"wrap": true,
								"maxLines": 0
							},
							{
								"type": "TextBlock",
								"size": "default",
								"isSubtle": true,
								"text": "Now that you have successfully run your bot, follow the links in this Adaptive Card to expand your knowledge of Bot Framework.",
								"wrap": true,
								"maxLines": 0
							}
						],
						"actions": [
							{
								"type": "Action.OpenUrl",
								"title": "Get an overview",
								"url": "https://docs.microsoft.com/en-us/azure/bot-service/?view=azure-bot-service-4.0"
							},
							{
								"type": "Action.OpenUrl",
								"title": "Ask a question",
								"url": "https://stackoverflow.com/questions/tagged/botframework"
							},
							{
								"type": "Action.OpenUrl",
								"title": "Learn how to deploy",
								"url": "https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-howto-deploy-azure?view=azure-bot-service-4.0"
							}
						]
					}
				}
			],
			"entities": []
		},
		{
			"type": "message",
			"id": "IVCpaSiSE8JLNEuZ5Mb1Xk-us|0000001",
			"timestamp": "2023-06-21T00:23:31.9859399Z",
			"channelId": "directline",
			"from": {
				"id": "BotAzulTeste",
				"name": "BotAzulTeste"
			},
			"conversation": {
				"id": "IVCpaSiSE8JLNEuZ5Mb1Xk-us"
			},
			"text": "NOTE: LUIS is not configured. To enable all capabilities, add 'LuisAppId', 'LuisAPIKey' and 'LuisAPIHostName' to the appsettings.json file.",
			"inputHint": "ignoringInput",
			"attachments": [],
			"entities": []
		},
		{
			"type": "message",
			"id": "IVCpaSiSE8JLNEuZ5Mb1Xk-us|0000002",
			"timestamp": "2023-06-21T00:23:32.0274226Z",
			"channelId": "directline",
			"from": {
				"id": "BotAzulTeste",
				"name": "BotAzulTeste"
			},
			"conversation": {
				"id": "IVCpaSiSE8JLNEuZ5Mb1Xk-us"
			},
			"text": "Where would you like to travel to?",
			"speak": "Where would you like to travel to?",
			"inputHint": "expectingInput",
			"attachments": [],
			"entities": []
		},
		{
			"type": "Teste",
			"id": "IVCpaSiSE8JLNEuZ5Mb1Xk-us|0000003",
			"timestamp": "2023-06-21T00:23:31.6774783Z",
			"serviceUrl": "https://directline.botframework.com/",
			"channelId": "directline",
			"from": {
				"id": "The Web Spark"
			},
			"conversation": {
				"id": "IVCpaSiSE8JLNEuZ5Mb1Xk-us"
			}
		},
		{
			"type": "Teste",
			"id": "IVCpaSiSE8JLNEuZ5Mb1Xk-us|0000004",
			"timestamp": "2023-06-21T00:23:56.6471351Z",
			"serviceUrl": "https://directline.botframework.com/",
			"channelId": "directline",
			"from": {
				"id": "The Web Spark"
			},
			"conversation": {
				"id": "IVCpaSiSE8JLNEuZ5Mb1Xk-us"
			},
			"text": "create a note"
		}
	],
	"watermark": "4"
}
```   
</details>
