# Azure Intelligent Apps with CosmosDB and ChatGPT HOL

## Hands-on Lab 소개

* 인공지능의 가장 진보적이고 혁신적인 발전 중 하나인 ChatGPT와 GPT4를 통하여 인공지능이 어떻게 우리의 일상생활에 적용되고 있는지 알아보고, Azure App Service와 CosmosDB, Azure OpenAI를 이용하여 ChatGPT를 적용하는 방법을 학습합니다.

* 본 실습에서는 Azure OpenAPI 서비스를 이용하여 지능형 웹 애플리케이션을 생성합니다. 이 실습을 완성하고나면, Azure OpenAI 서비스를 이용하여 AI 챗봇 애플리케이션을 생성하는 방법을 습득할 수 있습니다. OpenAI

* OpenAI와 ChatGPT
  * OpenAI는 2015년 설립된 인공지능 연구 기업입니다. OpenAI는 인공지능의 발전을 위해 노력하고 있으며, 인공지능의 발전을 통하여 인류의 미래를 개선하고자 합니다. OpenAI는 인공지능의 발전을 위하여 다양한 연구를 진행하고 있으며, 그 중 하나가 ChatGPT입니다.
  * ChatGPT는 OpenAI에서 개발한 인공지능 챗봇입니다. ChatGPT는 인공지능이 자연어를 이해하고, 자연어로 대화를 주고받을 수 있도록 학습된 인공지능입니다.
  * 본 실습에서는 선택된 GPT 모델을 이용하여 수준 높은 답변과 복잡한 질문에 대한 답변을 생성하는 방법을 학습합니다.

* 본 실습은 GitHub Azure-Samples 리파지토리의 ["Azure CosmosDB + OpenAI ChatGPT"](https://github.com/Azure-Samples/cosmosdb-chatgpt) 샘플 애플리케이션을 기반으로 생성 되었습니다.

## 사용 리소스 및 환경
  * Azure App Service
  * Azure CosmosDB
  * Azure OpenAPI

## High Level Architecture
<img src="./images/Chatbot Architecture.png" width="520"/>

  * 본 실습에서는 사용자를 인증하고 인증된 사용자를 SaaS 솔루션인 Contoso Chatbot으로 리다이렉트 해주는, 고객용 Contoso Product Landing Page를 생성합니다.

  * Chatbot 사용자 인터페이스는 Blazor front end로 구동되어 Azure App Service에 호스팅됩니다. (Blazor는 .NET Core 기반의 웹 프레임워크로, C#을 사용하여 웹 프론트 엔드를 구현할 수 있습니다.) 기본적으로 Azure OpenAI 서비스는 서비스의 URI와 API Key를 통하여 인증됩니다. 사용자가 채팅을 시작할때, 프롬프트가 OpenAI 서비스로 전송되고, 응답이 AI 서비스에서 반환됩니다. 그런 다음 모든 메세지가 Azure Cosmos DB에 저장되고 지속됩니다.

  * 본 시나리오를 지원하기 위하여, Azure App Service에 호스팅되는 웹앱은 아래의 서비스들과 연동됩니다.

    1. Azure AD: 고객과 솔루션 어드민을 인증
    2. Azure SQL DB: 구독 데이터 저장 및 관리
    3. Azure OpenAI Service: 자연어 ChatGPT 모델로 부터 AI 응답 생성
    4. Azure CosmosDB: Intelligent App에서 사용된 ChatGPT 모델로 부터 생성된 응답 저장

## 사전 요구 사항

* 지능형 웹 애플리케이션 배포를 위해서는 다음의 사전 요구 사항이 필요합니다.

1. Azure 구독 및 Azure OpenAPI Access

  * Azure OpenAPI Access 요청은 [본 링크](https://customervoice.microsoft.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7en2Ais5pxKtso_Pz4b1_xUOFA5Qk1UWDRBMjg0WFhPMkIzTzhKQ1dWNyQlQCN0PWcu)에서 정보를 채우고 Submit 하면 됩니다.
  * Azure OpenAPI Access 요청이 승인/거절되면 이메일로 알려줍니다.

2. Azure 구독에서 App Serivce와 CosmosDB를 배포할 수 있는 권한.

3. Visual Studio, Visual Studio Code등의 코드를 보거나 수정할 수 있는 에디터

## 실습 순서

* [Step 1. Azure에서 ChatBot App 리소스 배포](https://github.com/jeongaelee/ChatbotAppHOL/blob/master/step01.md)
* [Step 2. OpenAPI Key 확인 및 Azure OpenAI 서비스 API 연결 확인](https://github.com/jeongaelee/ChatbotAppHOL/blob/master/step02.md)
* [Step 3. Chatbot 앱 보안](https://github.com/jeongaelee/ChatbotAppHOL/blob/master/step03.md)
