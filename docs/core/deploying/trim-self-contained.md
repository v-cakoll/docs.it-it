---
title: Tagliare le applicazioni autonome
description: Scopri come tagliare le app autonome per ridurne le dimensioni. .NET Core raggruppa il runtime con un'app pubblicata in modo autonomo e in genere include più tempo di runtime.
author: jamshedd
ms.author: jamshedd
ms.date: 01/23/2020
ms.openlocfilehash: 5206ca255c500b382402ac4e7dd3300b7face1cf
ms.sourcegitcommit: 45cced471d59d5dac3f0c92abc9d4849716098a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/04/2020
ms.locfileid: "80665635"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="0c86e-104">Tagliare distribuzioni ed eseguibili autonomi</span><span class="sxs-lookup"><span data-stu-id="0c86e-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="0c86e-105">Quando si pubblica un'applicazione autonoma, il runtime di .NET Core viene fornito insieme all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c86e-105">When publishing an application self-contained, the .NET Core runtime is bundled together with the application.</span></span> <span data-ttu-id="0c86e-106">Questo raggruppamento aggiunge una quantità significativa di contenuto all'applicazione in pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0c86e-106">This bundling adds a significant amount of content to your packaged application.</span></span>

<span data-ttu-id="0c86e-107">Quando si tratta di distribuire l'applicazione, le dimensioni sono spesso un fattore importante.</span><span class="sxs-lookup"><span data-stu-id="0c86e-107">When it comes to deploying your application, size is often an important factor.</span></span> <span data-ttu-id="0c86e-108">Mantenere le dimensioni dell'applicazione del pacchetto il più piccolo possibile è in genere un obiettivo per gli sviluppatori di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0c86e-108">Keeping the size of the package application as small as possible is typically a goal for application developers.</span></span>

<span data-ttu-id="0c86e-109">A seconda della complessità dell'applicazione, è necessario solo un sottoinsieme del runtime per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c86e-109">Depending on the complexity of the application, only a subset of the runtime is required to run the application.</span></span> <span data-ttu-id="0c86e-110">Queste parti inutilizzate del runtime non sono necessarie e possono essere tagliate dall'applicazione in pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0c86e-110">These unused parts of the runtime are unnecessary and can be trimmed from the packaged application.</span></span>

> [!NOTE]
> <span data-ttu-id="0c86e-111">Il taglio è una funzionalità sperimentale in .NET Core 3.1 ed è disponibile _solo_ per le applicazioni pubblicate autonome.</span><span class="sxs-lookup"><span data-stu-id="0c86e-111">Trimming is an experimental feature in .NET Core 3.1 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="trim-your-application"></a><span data-ttu-id="0c86e-112">Tagliare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="0c86e-112">Trim your application</span></span>

<span data-ttu-id="0c86e-113">L'esempio seguente mostra come tagliare l'applicazione utilizzando il comando [dotnet publish:](../tools/dotnet-publish.md)</span><span class="sxs-lookup"><span data-stu-id="0c86e-113">The following example shows how to trim your application using the [dotnet publish](../tools/dotnet-publish.md) command:</span></span>

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true /p:PublishSingleFile=false /p:PublishTrimmed=true
```

<span data-ttu-id="0c86e-114">La funzionalità di taglio funziona esaminando i file binari dell'applicazione per individuare e compilare un grafico degli assembly di runtime necessari.</span><span class="sxs-lookup"><span data-stu-id="0c86e-114">The trimming feature works by examining the application binaries to discover and build a graph of the required runtime assemblies.</span></span> <span data-ttu-id="0c86e-115">Gli assembly di runtime rimanenti a cui non viene fatto riferimento vengono tagliati.</span><span class="sxs-lookup"><span data-stu-id="0c86e-115">The remaining runtime assemblies that aren't referenced are trimmed.</span></span>

## <a name="trimming-issues-when-using-reflection"></a><span data-ttu-id="0c86e-116">Tagliare i problemi quando si usa la reflection</span><span class="sxs-lookup"><span data-stu-id="0c86e-116">Trimming issues when using reflection</span></span>

<span data-ttu-id="0c86e-117">Esistono scenari in cui la funzionalità di taglio non riuscirà a rilevare i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="0c86e-117">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="0c86e-118">Ad esempio, un'applicazione che utilizza la reflection potrebbe incorrere in questo problema perché la dipendenza dall'assembly sarà nota solo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0c86e-118">For example, an application that uses reflection could run into this issue because the dependency on the assembly will only be known at run time.</span></span>

<span data-ttu-id="0c86e-119">Il taglio è un problema solo se l'utilizzo della reflection dipende da un assembly di runtime a cui non viene fatto riferimento direttamente.</span><span class="sxs-lookup"><span data-stu-id="0c86e-119">Trimming is only a problem if the reflection usage depends on a runtime assembly that isn't referenced directly.</span></span> <span data-ttu-id="0c86e-120">Tenere presente che il codice dell'applicazione potrebbe non utilizzare direttamente la reflection, ma è possibile che venga utilizzato da un assembly di terze parti a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="0c86e-120">Keep in mind that your application code may not be using reflection directly, but a third-party assembly you're referencing may be using it.</span></span>

<span data-ttu-id="0c86e-121">Quando il codice fa riferimento a un'API tramite reflection e non si desidera che il linker tagli l'assembly che contiene tale API, è possibile modificare il file di progetto per escludere l'assembly dal processo di taglio.</span><span class="sxs-lookup"><span data-stu-id="0c86e-121">When the code is referencing an API through reflection and you don't want the linker to trim the assembly that contains that API, you can modify your project file to exclude the assembly from the trimming process.</span></span> <span data-ttu-id="0c86e-122">Nell'esempio seguente viene illustrato `System.Security` come impedire che un assembly chiamato venga tagliato:</span><span class="sxs-lookup"><span data-stu-id="0c86e-122">The following example shows how to prevent an assembly called `System.Security` from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="see-also"></a><span data-ttu-id="0c86e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c86e-123">See also</span></span>

- [<span data-ttu-id="0c86e-124">Distribuzione di applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="0c86e-124">.NET Core application deployment</span></span>](index.md)
