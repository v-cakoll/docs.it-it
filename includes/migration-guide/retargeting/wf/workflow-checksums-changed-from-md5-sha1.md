---
ms.openlocfilehash: 72d48d1daa85b6891c122f2fcc5279642253b926
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614840"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a><span data-ttu-id="0b6ff-101">Checksum del flusso di lavoro modificati da MD5 a SHA1</span><span class="sxs-lookup"><span data-stu-id="0b6ff-101">Workflow checksums changed from MD5 to SHA1</span></span>

#### <a name="details"></a><span data-ttu-id="0b6ff-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0b6ff-102">Details</span></span>

<span data-ttu-id="0b6ff-103">Per supportare il debug con Visual Studio, il runtime del flusso di lavoro genera un checksum per un'istanza del flusso di lavoro usando un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="0b6ff-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow instance using a hashing algorithm.</span></span> <span data-ttu-id="0b6ff-104">In .NET Framework 4.6.2 e versioni precedenti, l'hash del checksum del flusso di lavoro usava l'algoritmo MD5, che causava problemi nei sistemi abilitati per FIPS.</span><span class="sxs-lookup"><span data-stu-id="0b6ff-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="0b6ff-105">A partire da .NET Framework 4.7 l'algoritmo è SHA1.</span><span class="sxs-lookup"><span data-stu-id="0b6ff-105">Starting with the .NET Framework 4.7, the algorithm is SHA1.</span></span> <span data-ttu-id="0b6ff-106">Se il codice ha mantenuto i checksum, questi non saranno compatibili.</span><span class="sxs-lookup"><span data-stu-id="0b6ff-106">If your code has persisted these checksums, they will be incompatible.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0b6ff-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="0b6ff-107">Suggestion</span></span>

<span data-ttu-id="0b6ff-108">Se il codice non riesce a caricare le istanze del flusso di lavoro a causa di un errore di checksum, provare a impostare lo switch `AppContext`&quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; su true. Nel codice:</span><span class="sxs-lookup"><span data-stu-id="0b6ff-108">If your code is unable to load workflow instances due to a checksum failure, try setting the `AppContext` switch &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; to true.In code:</span></span>

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseMD5ForWFDebugger", true);
```

<span data-ttu-id="0b6ff-109">O nella configurazione:</span><span class="sxs-lookup"><span data-stu-id="0b6ff-109">Or in configuration:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseMD5ForWFDebugger=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="0b6ff-110">Nome</span><span class="sxs-lookup"><span data-stu-id="0b6ff-110">Name</span></span>    | <span data-ttu-id="0b6ff-111">Valore</span><span class="sxs-lookup"><span data-stu-id="0b6ff-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0b6ff-112">Scope</span><span class="sxs-lookup"><span data-stu-id="0b6ff-112">Scope</span></span>   | <span data-ttu-id="0b6ff-113">Minorenne</span><span class="sxs-lookup"><span data-stu-id="0b6ff-113">Minor</span></span>       |
| <span data-ttu-id="0b6ff-114">Version</span><span class="sxs-lookup"><span data-stu-id="0b6ff-114">Version</span></span> | <span data-ttu-id="0b6ff-115">4.7</span><span class="sxs-lookup"><span data-stu-id="0b6ff-115">4.7</span></span>         |
| <span data-ttu-id="0b6ff-116">Type</span><span class="sxs-lookup"><span data-stu-id="0b6ff-116">Type</span></span>    | <span data-ttu-id="0b6ff-117">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="0b6ff-117">Retargeting</span></span> |
