---
ms.openlocfilehash: 946e71f2f466664c8f9fcf4811288ce693a872eb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616262"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a><span data-ttu-id="ac95c-101">Checksum di Workflow XAML per i simboli modificati da SHA1 in SHA256</span><span class="sxs-lookup"><span data-stu-id="ac95c-101">Workflow XAML checksums for symbols changed from SHA1 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="ac95c-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ac95c-102">Details</span></span>

<span data-ttu-id="ac95c-103">Per supportare il debug con Visual Studio, il runtime di Workflow genera un checksum per un file Workflow XAML usando un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="ac95c-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow XAML file using a hashing algorithm.</span></span> <span data-ttu-id="ac95c-104">In .NET Framework 4.6.2 e versioni precedenti, l'hash del checksum del flusso di lavoro usava l'algoritmo MD5, che causava problemi nei sistemi abilitati per FIPS.</span><span class="sxs-lookup"><span data-stu-id="ac95c-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="ac95c-105">A partire da .NET Framework 4.7, l'algoritmo predefinito è stato modificato in SHA1.</span><span class="sxs-lookup"><span data-stu-id="ac95c-105">Starting with the .NET Framework 4.7, the default algorithm was changed to SHA1.</span></span> <span data-ttu-id="ac95c-106">A partire da .NET Framework 4.8, l'algoritmo predefinito è stato modificato in SHA256.</span><span class="sxs-lookup"><span data-stu-id="ac95c-106">Starting with the .NET Framework 4.8, the default algorithm was changed to SHA256.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ac95c-107">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="ac95c-107">Suggestion</span></span>

<span data-ttu-id="ac95c-108">Se il codice non è in grado di caricare le istanze del flusso di lavoro o trovare i simboli appropriati a causa di un errore di checksum, provare a impostare l' `AppContext` opzione "Switch.System. Activities. UseSHA1HashForDebuggerSymbols "a `true` .</span><span class="sxs-lookup"><span data-stu-id="ac95c-108">If your code is unable to load workflow instances or to find appropriate symbols due to a checksum failure, try setting the `AppContext` switch "Switch.System.Activities.UseSHA1HashForDebuggerSymbols" to `true`.</span></span> <span data-ttu-id="ac95c-109">Nel codice:</span><span class="sxs-lookup"><span data-stu-id="ac95c-109">In code:</span></span>

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseSHA1HashForDebuggerSymbols", true);
```

<span data-ttu-id="ac95c-110">O nella configurazione:</span><span class="sxs-lookup"><span data-stu-id="ac95c-110">Or in configuration:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="ac95c-111">Nome</span><span class="sxs-lookup"><span data-stu-id="ac95c-111">Name</span></span>    | <span data-ttu-id="ac95c-112">Valore</span><span class="sxs-lookup"><span data-stu-id="ac95c-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ac95c-113">Scope</span><span class="sxs-lookup"><span data-stu-id="ac95c-113">Scope</span></span>   | <span data-ttu-id="ac95c-114">Minorenne</span><span class="sxs-lookup"><span data-stu-id="ac95c-114">Minor</span></span>       |
| <span data-ttu-id="ac95c-115">Version</span><span class="sxs-lookup"><span data-stu-id="ac95c-115">Version</span></span> | <span data-ttu-id="ac95c-116">4.8</span><span class="sxs-lookup"><span data-stu-id="ac95c-116">4.8</span></span>         |
| <span data-ttu-id="ac95c-117">Type</span><span class="sxs-lookup"><span data-stu-id="ac95c-117">Type</span></span>    | <span data-ttu-id="ac95c-118">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="ac95c-118">Retargeting</span></span> |
