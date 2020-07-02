---
ms.openlocfilehash: 519de92ca4201d199941afe6382ddf9fc480fbbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614521"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a><span data-ttu-id="dc999-101">ServiceBase non propaga le eccezioni OnStart</span><span class="sxs-lookup"><span data-stu-id="dc999-101">ServiceBase doesn't propagate OnStart exceptions</span></span>

#### <a name="details"></a><span data-ttu-id="dc999-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="dc999-102">Details</span></span>

<span data-ttu-id="dc999-103">In .NET Framework 4.7 e versioni precedenti, le eccezioni generate all'avvio di servizi non vengono propagate al chiamante di <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dc999-103">In the .NET Framework 4.7 and earlier versions, exceptions thrown on service startup are not propagated to the caller of <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.</span></span><br/><span data-ttu-id="dc999-104">A partire dalle applicazioni destinate a .NET Framework 4.7.1, il runtime propaga le eccezioni a <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> per i servizi il cui avvio non riesce.</span><span class="sxs-lookup"><span data-stu-id="dc999-104">Starting with applications that target the .NET Framework 4.7.1, the runtime propagates exceptions to <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> for services that fail to start.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dc999-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="dc999-105">Suggestion</span></span>

<span data-ttu-id="dc999-106">All'avvio del servizio, se si verifica un'eccezione, tale eccezione verrà propagata.</span><span class="sxs-lookup"><span data-stu-id="dc999-106">On service start, if there is an exception, that exception will be propagated.</span></span> <span data-ttu-id="dc999-107">Questo dovrebbe aiutare a diagnosticare casi in cui l'avvio di un servizio non riesce.</span><span class="sxs-lookup"><span data-stu-id="dc999-107">This should help diagnose cases where services fail to start.</span></span> <br/><span data-ttu-id="dc999-108">Se questo comportamento non è accettabile, è possibile rifiutarlo esplicitamente aggiungendo l'elemento &lt;AppContextSwitchOverrides&gt; seguente alla sezione &lt;runtime&gt; del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="dc999-108">If this behavior is undesirable, you can opt out of it by adding the following &lt;AppContextSwitchOverrides&gt; element to the &lt;runtime&gt; section of your application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true" />
```

<span data-ttu-id="dc999-109">Se l'applicazione è destinata a una versione precedente la 4.7.1 ma si vuole avere questo comportamento, aggiungere l'elemento &lt;AppContextSwitchOverrides&gt; seguente alla sezione &lt;runtime&gt; del file di configurazione dell'applicazione:</span><span class="sxs-lookup"><span data-stu-id="dc999-109">If your application targets an earlier version than 4.7.1 but you want to have this behavior, add the following &lt;AppContextSwitchOverrides&gt; element to the &lt;runtime&gt; section of your application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false" />
```

| <span data-ttu-id="dc999-110">Nome</span><span class="sxs-lookup"><span data-stu-id="dc999-110">Name</span></span>    | <span data-ttu-id="dc999-111">Valore</span><span class="sxs-lookup"><span data-stu-id="dc999-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dc999-112">Scope</span><span class="sxs-lookup"><span data-stu-id="dc999-112">Scope</span></span>   | <span data-ttu-id="dc999-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="dc999-113">Minor</span></span>       |
| <span data-ttu-id="dc999-114">Version</span><span class="sxs-lookup"><span data-stu-id="dc999-114">Version</span></span> | <span data-ttu-id="dc999-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="dc999-115">4.7.1</span></span>       |
| <span data-ttu-id="dc999-116">Type</span><span class="sxs-lookup"><span data-stu-id="dc999-116">Type</span></span>    | <span data-ttu-id="dc999-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="dc999-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="dc999-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="dc999-118">Affected APIs</span></span>

- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType>
- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType>
