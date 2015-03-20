---
layout: page
title: Architecture
permalink: /architecture/
---

## Architecture draft

[Click to see the draft](https://docs.google.com/document/d/1yRV5DNJAhBH73bJo-s5L8wwoeJG4Ke6H45dg8_rRT84/edit?usp=sharing)

## Architecture plan

[Click to see the plan](https://drive.google.com/file/d/0B4mHLrLla3S8VHd3QXZrZ25yb1U/view?usp=sharing)

## Formats of incoming messages (only suggestion! decide yourself)

### FraudDetectionService

PUT /api/loanApplication/{loanApplicationId}

```json
{
    "firstName" : "text",
    "lastName" : "text",
    "job" : "text",
    "amount" : number,
    "age" : number
}
```

### LoanApplicationDecisionMaker

PUT /api/loanApplication/{loanApplicationId}

```json
{
    "firstName" : "text",
    "lastName" : "text",
    "job" : "text",
    "amount" : number,
    "fraudStatus" : "text"
}
```

GET /api/loanApplication/{loanApplicationId}
```json
{
    "applicationId" : "text",
    "result" : boolean
}
```

### ClientService

POST /api/client

```json
{
    "firstName" : "text",
    "lastName" : "text",
    "age": number,
    "loanId" : "text" (This is actually the loan application identifier.)
}
```
### LoanApplicationService

POST /api/loanApplication

```json
{
    "amount": number,
    "loanId" : "text" (This is actually the loan application identifier.)
}
```

### ReportingService

POST /api/client

```json
{
    "firstName" : "text",
    "lastName" : "text",
    "age": number,
    "loanId" : "text" (This is actually the loan application identifier.)
}
```

POST /api/reporting

```json
{
    "loanId" : "text",
    "job" : "text",
    "amount" : number,
    "fraudStatus" : "text",
    "decision" : "text"
}
```

### MarketingOfferGenerator

PUT /api/marketing/{loanApplicationId}

```json
{
    "person" : {
        "firstName" : "text",
        "lastName" : "text"
    },
    "decision" : "text"
}
```

GET /api/marketing/{firstName}_{lastName}

```json
{
    "marketingOffer" : "text"
}
```
