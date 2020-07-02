---
ms.openlocfilehash: 519de92ca4201d199941afe6382ddf9fc480fbbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614521"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase non propaga le eccezioni OnStart

#### <a name="details"></a>Dettagli

In .NET Framework 4.7 e versioni precedenti, le eccezioni generate all'avvio di servizi non vengono propagate al chiamante di <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.<br/>A partire dalle applicazioni destinate a .NET Framework 4.7.1, il runtime propaga le eccezioni a <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> per i servizi il cui avvio non riesce.

#### <a name="suggestion"></a>Suggerimento

All'avvio del servizio, se si verifica un'eccezione, tale eccezione verrà propagata. Questo dovrebbe aiutare a diagnosticare casi in cui l'avvio di un servizio non riesce. <br/>Se questo comportamento non è accettabile, è possibile rifiutarlo esplicitamente aggiungendo l'elemento &lt;AppContextSwitchOverrides&gt; seguente alla sezione &lt;runtime&gt; del file di configurazione dell'applicazione:

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true" />
```

Se l'applicazione è destinata a una versione precedente la 4.7.1 ma si vuole avere questo comportamento, aggiungere l'elemento &lt;AppContextSwitchOverrides&gt; seguente alla sezione &lt;runtime&gt; del file di configurazione dell'applicazione:

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false" />
```

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Minorenne       |
| Version | 4.7.1       |
| Type    | Ridestinazione |

#### <a name="affected-apis"></a>API interessate

- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType>
- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType>
