---
ms.openlocfilehash: 7a7ecf052276fe8e62463498b83230d466630c79
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616263"
---
### <a name="workflow-xoml-definition-and-sqltrackingservice-cache-keys-changed-from-md5-to-sha256"></a><span data-ttu-id="732fb-101">La definizione XOML del flusso di lavoro e le chiavi della cache di SqlTrackingService sono state modificate da MD5 a SHA256</span><span class="sxs-lookup"><span data-stu-id="732fb-101">Workflow XOML definition and SqlTrackingService cache keys changed from MD5 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="732fb-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="732fb-102">Details</span></span>

<span data-ttu-id="732fb-103">Nel runtime di Workflow viene archiviata una cache di definizioni del flusso di lavoro definite in XOML.</span><span class="sxs-lookup"><span data-stu-id="732fb-103">The Workflow Runtime in keeps a cache of workflow definitions defined in XOML.</span></span> <span data-ttu-id="732fb-104">Anche in SqlTrackingService viene archiviata una cache con chiavi specificate da stringhe.</span><span class="sxs-lookup"><span data-stu-id="732fb-104">The SqlTrackingService also keeps a cache that is keyed by strings.</span></span> <span data-ttu-id="732fb-105">Queste cache vengono codificate con chiavi in base ai valori che includono un valore hash di checksum.</span><span class="sxs-lookup"><span data-stu-id="732fb-105">These caches are keyed by values that include checksum hash value.</span></span> <span data-ttu-id="732fb-106">In .NET Framework 4.7.2 e versioni precedenti l'hash del checksum usava l'algoritmo MD5 che causava problemi nei sistemi abilitati per FIPS.</span><span class="sxs-lookup"><span data-stu-id="732fb-106">In the .NET Framework 4.7.2 and earlier versions, this checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="732fb-107">A partire da .NET Framework 4,8, l'algoritmo usato è SHA256. Non dovrebbe sussistere un problema di compatibilità con questa modifica perché i valori vengono ricalcolati ogni volta che il runtime del flusso di lavoro e SqlTrackingService viene avviato.</span><span class="sxs-lookup"><span data-stu-id="732fb-107">Starting with the .NET Framework 4.8, the algorithm used is SHA256.There shouldn't be a compatibility issue with this change because the values are recalculated each time the Workflow Runtime and SqlTrackingService is started.</span></span> <span data-ttu-id="732fb-108">Tuttavia, sono state specificate modalità non standard per consentire ai clienti di ripristinare l'uso dell'algoritmo hash legacy, in caso di necessità.</span><span class="sxs-lookup"><span data-stu-id="732fb-108">However, we have provided quirks to allow customers to revert back to usage of the legacy hashing algorithm, if necessary.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="732fb-109">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="732fb-109">Suggestion</span></span>

<span data-ttu-id="732fb-110">Se questa modifica crea problemi durante l'esecuzione dei flussi di lavoro, provare a impostare una o entrambe le opzioni `AppContext`:</span><span class="sxs-lookup"><span data-stu-id="732fb-110">If this change presents a problem when executing workflows, try setting one or both of the `AppContext` switches:</span></span>

- <span data-ttu-id="732fb-111">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; su true.</span><span class="sxs-lookup"><span data-stu-id="732fb-111">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot; to true.</span></span>
- <span data-ttu-id="732fb-112">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; su true.</span><span class="sxs-lookup"><span data-stu-id="732fb-112">&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot; to true.</span></span>
<span data-ttu-id="732fb-113">Nel codice:</span><span class="sxs-lookup"><span data-stu-id="732fb-113">In code:</span></span>

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey&quot;, true);&#13;&#10;System.AppContext.SetSwitch(&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKey&quot;, true);&#13;&#10;</code></pre>

<span data-ttu-id="732fb-114">O nel file di configurazione (deve essere il file di configurazione per l'applicazione con cui si sta creando l'oggetto <xref:System.Workflow.Runtime.WorkflowRuntime>):</span><span class="sxs-lookup"><span data-stu-id="732fb-114">Or in the configuration file (this needs to be in the config file for the application that is creating the <xref:System.Workflow.Runtime.WorkflowRuntime> object):</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForWorkflowDefinitionDispenserCacheKey=true&quot; /&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.Runtime.UseLegacyHashForSqlTrackingCacheKeytrue&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="732fb-115">Nome</span><span class="sxs-lookup"><span data-stu-id="732fb-115">Name</span></span>    | <span data-ttu-id="732fb-116">Valore</span><span class="sxs-lookup"><span data-stu-id="732fb-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="732fb-117">Scope</span><span class="sxs-lookup"><span data-stu-id="732fb-117">Scope</span></span>   | <span data-ttu-id="732fb-118">Minorenne</span><span class="sxs-lookup"><span data-stu-id="732fb-118">Minor</span></span>       |
| <span data-ttu-id="732fb-119">Version</span><span class="sxs-lookup"><span data-stu-id="732fb-119">Version</span></span> | <span data-ttu-id="732fb-120">4.8</span><span class="sxs-lookup"><span data-stu-id="732fb-120">4.8</span></span>         |
| <span data-ttu-id="732fb-121">Type</span><span class="sxs-lookup"><span data-stu-id="732fb-121">Type</span></span>    | <span data-ttu-id="732fb-122">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="732fb-122">Retargeting</span></span> |
