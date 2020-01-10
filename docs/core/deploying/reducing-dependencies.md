---
title: Riduzione delle dipendenze dei pacchetti con project.json
description: Ridurre le dipendenze dei pacchetti durante la creazione di librerie basate su project.json.
author: cartermp
ms.date: 06/20/2016
ms.openlocfilehash: 48ba3ef578388fd98fe7cb830df313512d359483
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740830"
---
# <a name="reducing-package-dependencies-with-projectjson"></a><span data-ttu-id="c3c50-103">Riduzione delle dipendenze dei pacchetti con project.json</span><span class="sxs-lookup"><span data-stu-id="c3c50-103">Reducing Package Dependencies with project.json</span></span>

<span data-ttu-id="c3c50-104">Questo articolo descrive cosa è necessario conoscere sulla riduzione delle dipendenze dei pacchetti durante la creazione di librerie `project.json`.</span><span class="sxs-lookup"><span data-stu-id="c3c50-104">This article covers what you need to know about reducing your package dependencies when authoring `project.json` libraries.</span></span> <span data-ttu-id="c3c50-105">Al termine dell'articolo, si apprenderà come creare la libreria in modo che usi solo le dipendenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="c3c50-105">By the end of this article, you will learn how to compose your library such that it only uses the dependencies it needs.</span></span>

## <a name="why-its-important"></a><span data-ttu-id="c3c50-106">Perché è importante?</span><span class="sxs-lookup"><span data-stu-id="c3c50-106">Why it's Important</span></span>

<span data-ttu-id="c3c50-107">.NET Core è un prodotto costituito da pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="c3c50-107">.NET Core is a product made up of NuGet packages.</span></span>  <span data-ttu-id="c3c50-108">Un pacchetto fondamentale è il [metapacchetto .NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library), ovvero un pacchetto NuGet composto da altri pacchetti.</span><span class="sxs-lookup"><span data-stu-id="c3c50-108">An essential package is the [.NETStandard.Library metapackage](https://www.nuget.org/packages/NETStandard.Library), which is a NuGet package composed of other packages.</span></span> <span data-ttu-id="c3c50-109">Fornisce il set di pacchetti che sono garantiti per lavorare su più implementazioni di .NET, ad esempio .NET Framework, .NET Core e Novell/mono.</span><span class="sxs-lookup"><span data-stu-id="c3c50-109">It provides you with the set of packages that are guaranteed to work on multiple .NET implementations, such as .NET Framework, .NET Core, and Xamarin/Mono.</span></span>

<span data-ttu-id="c3c50-110">È tuttavia probabile che la libreria non usi tutti i pacchetti che contiene.</span><span class="sxs-lookup"><span data-stu-id="c3c50-110">However, there's a good chance that your library won't use every single package it contains.</span></span>  <span data-ttu-id="c3c50-111">Quando si crea una libreria e la si distribuisce tramite NuGet, è opportuno ridurre il numero delle dipendenze ai soli pacchetti che vengono effettivamente usati.</span><span class="sxs-lookup"><span data-stu-id="c3c50-111">When authoring a library and distributing it over NuGet, it's a best practice to "trim" your dependencies down to only the packages you actually use.</span></span>  <span data-ttu-id="c3c50-112">In questo modo, si otterrà un impatto minore per i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="c3c50-112">This results in a smaller overall footprint for NuGet packages.</span></span>

## <a name="how-to-do-it"></a><span data-ttu-id="c3c50-113">Come procedere?</span><span class="sxs-lookup"><span data-stu-id="c3c50-113">How to do it</span></span>

<span data-ttu-id="c3c50-114">Attualmente non è presente alcun comando ufficiale `dotnet` che ritaglia i riferimenti ai pacchetti.</span><span class="sxs-lookup"><span data-stu-id="c3c50-114">Currently, there is no official `dotnet` command that trims package references.</span></span>  <span data-ttu-id="c3c50-115">È tuttavia possibile eseguire questa operazione manualmente.</span><span class="sxs-lookup"><span data-stu-id="c3c50-115">Instead, you'll have to do it manually.</span></span>  <span data-ttu-id="c3c50-116">Il processo generale è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c3c50-116">The general process looks like the following:</span></span>

1. <span data-ttu-id="c3c50-117">Fare riferimento a `NETStandard.Library` versione `1.6.0` in una sezione `dependencies` di `project.json`.</span><span class="sxs-lookup"><span data-stu-id="c3c50-117">Reference `NETStandard.Library` version `1.6.0` in a `dependencies` section of your `project.json`.</span></span>
2. <span data-ttu-id="c3c50-118">Ripristinare i pacchetti con `dotnet restore` ([vedere la nota](#dotnet-restore-note)) dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c3c50-118">Restore packages with `dotnet restore` ([see note](#dotnet-restore-note)) from the command line.</span></span>
3. <span data-ttu-id="c3c50-119">Esaminare il file `project.lock.json` e trovare la sezione `NETStandard.Library`</span><span class="sxs-lookup"><span data-stu-id="c3c50-119">Inspect the `project.lock.json` file and find the `NETStandard.Library` section.</span></span>  <span data-ttu-id="c3c50-120">in genere all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="c3c50-120">It's near the beginning of the file.</span></span>
4. <span data-ttu-id="c3c50-121">Copiare tutti i pacchetti elencati in `dependencies`.</span><span class="sxs-lookup"><span data-stu-id="c3c50-121">Copy all of the listed packages under `dependencies`.</span></span>
5. <span data-ttu-id="c3c50-122">Rimuovere il riferimento `.NETStandard.Library` e sostituirlo con i pacchetti copiati.</span><span class="sxs-lookup"><span data-stu-id="c3c50-122">Remove the `.NETStandard.Library` reference and replace it with the copied packages.</span></span>
6. <span data-ttu-id="c3c50-123">Rimuovere i riferimenti ai pacchetti non necessari.</span><span class="sxs-lookup"><span data-stu-id="c3c50-123">Remove references to packages you don't need.</span></span>

<span data-ttu-id="c3c50-124">È possibile individuare i pacchetti non necessari in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3c50-124">You can find out which packages you don't need by one of the following ways:</span></span>

1. <span data-ttu-id="c3c50-125">Tentativi ed errori.</span><span class="sxs-lookup"><span data-stu-id="c3c50-125">Trial and error.</span></span> <span data-ttu-id="c3c50-126">Questo metodo fa riferimento alla rimozione di un pacchetto, al relativo ripristino, se la libreria continua a eseguire la compilazione, e alla ripetizione del processo.</span><span class="sxs-lookup"><span data-stu-id="c3c50-126">This involves removing a package, restoring, seeing if your library still compiles, and repeating this process.</span></span>
2. <span data-ttu-id="c3c50-127">Tramite uno strumento come [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) o [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector) per la selezione dei riferimenti in modo da visualizzare quali vengono effettivamente usati dal codice.</span><span class="sxs-lookup"><span data-stu-id="c3c50-127">Using a tool such as [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) or [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector) to peek at references to see what your code is actually using.</span></span> <span data-ttu-id="c3c50-128">È quindi possibile rimuovere i pacchetti che non corrispondono ai tipi in uso.</span><span class="sxs-lookup"><span data-stu-id="c3c50-128">You can then remove packages that don't correspond to types you're using.</span></span>

## <a name="example"></a><span data-ttu-id="c3c50-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="c3c50-129">Example</span></span>

<span data-ttu-id="c3c50-130">Si supponga di aver scritto una libreria che fornisce funzionalità aggiuntive ai tipi di raccolte generiche.</span><span class="sxs-lookup"><span data-stu-id="c3c50-130">Imagine that you wrote a library that provided additional functionality to generic collection types.</span></span> <span data-ttu-id="c3c50-131">Tale libreria deve dipendere da pacchetti come `System.Collections`, ma può non dipendere da pacchetti come `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="c3c50-131">Such a library would need to depend on packages such as `System.Collections`, but may not at all depend on packages such as `System.Net.Http`.</span></span> <span data-ttu-id="c3c50-132">Di conseguenza, può essere opportuno ridurre le dipendenze dei pacchetti alla quantità necessaria per la libreria.</span><span class="sxs-lookup"><span data-stu-id="c3c50-132">As such, it would be good to trim package dependencies down to only what this library required!</span></span>

<span data-ttu-id="c3c50-133">Per ridurre questa libreria, iniziare con il file `project.json` e aggiungere un riferimento a `NETStandard.Library` versione `1.6.0`.</span><span class="sxs-lookup"><span data-stu-id="c3c50-133">To trim this library, you start with the `project.json` file and add a reference to `NETStandard.Library` version `1.6.0`.</span></span>

```json
{
    "version":"1.0.0",
    "dependencies":{
        "NETStandard.Library":"1.6.0"
    },
    "frameworks": {
        "netstandard1.0": {}
     }
}
```

<span data-ttu-id="c3c50-134">Successivamente, si ripristinano i pacchetti con `dotnet restore` ([vedere la nota](#dotnet-restore-note)), si analizza il file `project.lock.json` e si trovano tutti i pacchetti ripristinati per `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="c3c50-134">Next, you restore packages with `dotnet restore` ([see note](#dotnet-restore-note)), inspect the `project.lock.json` file, and find all the packages restored for `NETStandard.Library`.</span></span>

<span data-ttu-id="c3c50-135">Di seguito è presentata la specifica sezione del file `project.lock.json` quando punta a `netstandard1.0`:</span><span class="sxs-lookup"><span data-stu-id="c3c50-135">Here's what the relevant section in the `project.lock.json` file looks like when targeting `netstandard1.0`:</span></span>

```json
"NETStandard.Library/1.6.0":{
    "type": "package",
    "dependencies": {
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    }
}
```

<span data-ttu-id="c3c50-136">Successivamente, sovrascrivere i riferimenti dei pacchetti nella sezione `dependencies` del file della libreria `project.json`, sostituendo il riferimento `NETStandard.Library`:</span><span class="sxs-lookup"><span data-stu-id="c3c50-136">Next, copy over the package references into the `dependencies` section of the library's `project.json` file, replacing the `NETStandard.Library` reference:</span></span>

```json
{
    "version":"1.0.0",
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
    }
}
```

<span data-ttu-id="c3c50-137">Si tratta di numerosi pacchetti, molti dei quali certamente non necessari per l'estensione dei tipi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="c3c50-137">That's quite a lot of packages, many of which certainly aren't necessary for extending collection types.</span></span>  <span data-ttu-id="c3c50-138">È possibile rimuovere manualmente i pacchetti o usare uno strumento come [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) o [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector/) per identificare i pacchetti effettivamente usati dal codice.</span><span class="sxs-lookup"><span data-stu-id="c3c50-138">You can either remove packages manually or use a tool such as [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) or [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector/) to identify which packages your code actually uses.</span></span>

<span data-ttu-id="c3c50-139">Di seguito un esempio di pacchetto dopo la riduzione delle dipendenze:</span><span class="sxs-lookup"><span data-stu-id="c3c50-139">Here's what a trimmed package could look like:</span></span>

```json
{
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Linq": "4.1.0",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Runtime.Handles": "4.0.1",
        "System.Runtime.InteropServices": "4.1.0",
        "System.Runtime.InteropServices.RuntimeInformation": "4.0.0",
        "System.Threading.Tasks": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
     }
}
```

<span data-ttu-id="c3c50-140">A questo punto, l'impatto è ridotto rispetto a quello che avrebbe se dipendesse dal metapacchetto `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="c3c50-140">Now, it has a smaller footprint than if it had depended on the `NETStandard.Library` metapackage.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
