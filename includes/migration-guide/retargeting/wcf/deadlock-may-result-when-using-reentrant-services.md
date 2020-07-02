---
ms.openlocfilehash: dd7d3e445772e4b5ec148576ccd1374d56e251bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614528"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a><span data-ttu-id="d25fc-101">Possibile deadlock quando si usano servizi rientranti</span><span class="sxs-lookup"><span data-stu-id="d25fc-101">Deadlock may result when using Reentrant services</span></span>

#### <a name="details"></a><span data-ttu-id="d25fc-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d25fc-102">Details</span></span>

<span data-ttu-id="d25fc-103">Può verificarsi un deadlock in un servizio rientrante, che limita le istanze del servizio a un solo thread di esecuzione alla volta.</span><span class="sxs-lookup"><span data-stu-id="d25fc-103">A deadlock may result in a Reentrant service, which restricts instances of the service to one thread of execution at a time.</span></span> <span data-ttu-id="d25fc-104">Sono soggetti a questo problema i servizi che includono l'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute> seguente nel codice:</span><span class="sxs-lookup"><span data-stu-id="d25fc-104">Services prone to encounter this problem will have the following <xref:System.ServiceModel.ServiceBehaviorAttribute> in their code:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a><span data-ttu-id="d25fc-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="d25fc-105">Suggestion</span></span>

<span data-ttu-id="d25fc-106">Per risolvere questo problema, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d25fc-106">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="d25fc-107">Impostare la modalità di concorrenza del servizio su <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> oppure &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;.</span><span class="sxs-lookup"><span data-stu-id="d25fc-107">Set the service's concurrency mode to <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> or &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;.</span></span> <span data-ttu-id="d25fc-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d25fc-108">For example:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- <span data-ttu-id="d25fc-109">Installare l'aggiornamento più recente di .NET Framework 4.6.2 oppure eseguire l'aggiornamento a una versione successiva di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d25fc-109">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="d25fc-110">Viene così disabilitato il flusso di <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d25fc-110">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d25fc-111">Questo comportamento è configurabile ed è equivalente all'aggiunta dell'impostazione dell'app seguente nel file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="d25fc-111">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

<span data-ttu-id="d25fc-112">Il valore di `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` non deve mai essere impostato su `false` per i servizi Reentrant.</span><span class="sxs-lookup"><span data-stu-id="d25fc-112">The value of `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` should never be set to `false` for Reentrant services.</span></span>

| <span data-ttu-id="d25fc-113">Nome</span><span class="sxs-lookup"><span data-stu-id="d25fc-113">Name</span></span>    | <span data-ttu-id="d25fc-114">Valore</span><span class="sxs-lookup"><span data-stu-id="d25fc-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d25fc-115">Scope</span><span class="sxs-lookup"><span data-stu-id="d25fc-115">Scope</span></span>   | <span data-ttu-id="d25fc-116">Minorenne</span><span class="sxs-lookup"><span data-stu-id="d25fc-116">Minor</span></span>       |
| <span data-ttu-id="d25fc-117">Version</span><span class="sxs-lookup"><span data-stu-id="d25fc-117">Version</span></span> | <span data-ttu-id="d25fc-118">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d25fc-118">4.6.2</span></span>       |
| <span data-ttu-id="d25fc-119">Type</span><span class="sxs-lookup"><span data-stu-id="d25fc-119">Type</span></span>    | <span data-ttu-id="d25fc-120">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="d25fc-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d25fc-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="d25fc-121">Affected APIs</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
