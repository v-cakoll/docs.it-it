---
ms.openlocfilehash: b521f4163bf5bf4a369d0eec12dae503703a976e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614433"
---
### <a name="throttle-concurrent-requests-per-session"></a>Limitazione delle richieste simultanee per sessione

#### <a name="details"></a>Dettagli

In .NET Framework 4.6.2 e versioni precedenti, ASP.NET esegue le richieste in sequenza con lo stesso Sessionid e in ASP.NET Sessionid viene sempre generato usando un cookie per impostazione predefinita. Se una pagina richiede molto tempo per rispondere, le prestazioni del server risulteranno significativamente peggiorate semplicemente premendo <kbd>F5</kbd> sul browser. Nella correzione è stato aggiunto un contatore per tenere traccia delle richieste in coda e terminare le richieste quando superano il limite specificato. Il valore predefinito è 50. Se si raggiunge il limite, verrà registrato un avviso nel registro eventi e potrebbe essere registrata una risposta HTTP 500 nel log di IIS.

#### <a name="suggestion"></a>Suggerimento

Per ripristinare il comportamento precedente, è possibile aggiungere l'impostazione seguente al file web. config per rifiutare esplicitamente il nuovo comportamento.

```xml
<appSettings>
    <add key="aspnet:RequestQueueLimitPerSession" value="2147483647"/>
</appSettings>
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7         |
| Type    | Ridestinazione |
