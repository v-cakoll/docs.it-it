---
title: Sviluppo di librerie con strumenti multipiattaforma
description: Informazioni su come creare librerie per .NET usando gli strumenti dell'interfaccia della riga di comando di .NET Core.
author: cartermp
ms.author: mairaw
ms.date: 05/01/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 6bdb5b11a54ce23c676d10ef6e440fa46ea12f72
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="developing-libraries-with-cross-platform-tools"></a><span data-ttu-id="78a18-103">Sviluppo di librerie con strumenti multipiattaforma</span><span class="sxs-lookup"><span data-stu-id="78a18-103">Developing Libraries with Cross Platform Tools</span></span>

<span data-ttu-id="78a18-104">Questo articolo illustra come scrivere librerie per .NET usando gli strumenti dell'interfaccia della riga di comando multipiattaforma.</span><span class="sxs-lookup"><span data-stu-id="78a18-104">This article covers how to write libraries for .NET using cross-platform CLI tools.</span></span> <span data-ttu-id="78a18-105">L'interfaccia della riga di comando offre un'esperienza efficace e di basso livello per qualsiasi sistema operativo supportato.</span><span class="sxs-lookup"><span data-stu-id="78a18-105">The CLI provides an efficient and low-level experience that works across any supported OS.</span></span> <span data-ttu-id="78a18-106">È comunque sempre possibile creare librerie con Visual Studio. Se si preferisce questo tipo di esperienza, [consultare la Guida di Visual Studio](libraries-with-vs.md).</span><span class="sxs-lookup"><span data-stu-id="78a18-106">You can still build libraries with Visual Studio, and if that is your preferred experience [refer to the Visual Studio guide](libraries-with-vs.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="78a18-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="78a18-107">Prerequisites</span></span>

<span data-ttu-id="78a18-108">È necessario che [l'SDK e l'interfaccia della riga di comando di .NET Core](https://www.microsoft.com/net/core) siano installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="78a18-108">You need [the .NET Core SDK and CLI](https://www.microsoft.com/net/core) installed on your machine.</span></span>

<span data-ttu-id="78a18-109">Per le sezioni di questo documento relative alle versioni di .NET Framework è necessario avere [.NET Framework](http://getdotnet.azurewebsites.net/) installato in un computer Windows.</span><span class="sxs-lookup"><span data-stu-id="78a18-109">For the sections of this document dealing with .NET Framework versions, you need the [.NET Framework](http://getdotnet.azurewebsites.net/) installed on a Windows machine.</span></span>

<span data-ttu-id="78a18-110">Inoltre, se si desidera supportare destinazioni precedenti di .NET Framework, è necessario installare Targeting/Developer Pack per versioni precedenti del framework dalla [pagina delle piattaforme di destinazione .NET](http://getdotnet.azurewebsites.net/target-dotnet-platforms.html).</span><span class="sxs-lookup"><span data-stu-id="78a18-110">Additionally, if you wish to support older .NET Framework targets, you need to install targeting/developer packs for older framework versions from the [.NET target platforms page](http://getdotnet.azurewebsites.net/target-dotnet-platforms.html).</span></span> <span data-ttu-id="78a18-111">Fare riferimento a questa tabella:</span><span class="sxs-lookup"><span data-stu-id="78a18-111">Refer to this table:</span></span>

| <span data-ttu-id="78a18-112">Versione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="78a18-112">.NET Framework Version</span></span> | <span data-ttu-id="78a18-113">Pacchetto da scaricare</span><span class="sxs-lookup"><span data-stu-id="78a18-113">What to download</span></span>                                       |
| ---------------------- | ------------------------------------------------------ |
| <span data-ttu-id="78a18-114">4.6.1</span><span class="sxs-lookup"><span data-stu-id="78a18-114">4.6.1</span></span>                  | <span data-ttu-id="78a18-115">.NET Framework 4.6.1 Targeting Pack</span><span class="sxs-lookup"><span data-stu-id="78a18-115">.NET Framework 4.6.1 Targeting Pack</span></span>                    |
| <span data-ttu-id="78a18-116">4.6</span><span class="sxs-lookup"><span data-stu-id="78a18-116">4.6</span></span>                    | <span data-ttu-id="78a18-117">.NET Framework 4.6 Targeting Pack</span><span class="sxs-lookup"><span data-stu-id="78a18-117">.NET Framework 4.6 Targeting Pack</span></span>                      |
| <span data-ttu-id="78a18-118">4.5.2</span><span class="sxs-lookup"><span data-stu-id="78a18-118">4.5.2</span></span>                  | <span data-ttu-id="78a18-119">.NET Framework 4.5.2 Developer Pack</span><span class="sxs-lookup"><span data-stu-id="78a18-119">.NET Framework 4.5.2 Developer Pack</span></span>                    |
| <span data-ttu-id="78a18-120">4.5.1</span><span class="sxs-lookup"><span data-stu-id="78a18-120">4.5.1</span></span>                  | <span data-ttu-id="78a18-121">.NET Framework 4.5.1 Developer Pack</span><span class="sxs-lookup"><span data-stu-id="78a18-121">.NET Framework 4.5.1 Developer Pack</span></span>                    |
| <span data-ttu-id="78a18-122">4.5</span><span class="sxs-lookup"><span data-stu-id="78a18-122">4.5</span></span>                    | <span data-ttu-id="78a18-123">Windows Software Development Kit per Windows 8</span><span class="sxs-lookup"><span data-stu-id="78a18-123">Windows Software Development Kit for Windows 8</span></span>         |
| <span data-ttu-id="78a18-124">4.0</span><span class="sxs-lookup"><span data-stu-id="78a18-124">4.0</span></span>                    | <span data-ttu-id="78a18-125">Windows SDK per Windows 7 e .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="78a18-125">Windows SDK for Windows 7 and .NET Framework 4</span></span>         |
| <span data-ttu-id="78a18-126">2.0, 3.0 e 3.5</span><span class="sxs-lookup"><span data-stu-id="78a18-126">2.0, 3.0, and 3.5</span></span>      | <span data-ttu-id="78a18-127">Runtime di .NET Framework 3.5 SP1 (o versione per Windows 8 o successiva)</span><span class="sxs-lookup"><span data-stu-id="78a18-127">.NET Framework 3.5 SP1 Runtime (or Windows 8+ version)</span></span> |

## <a name="how-to-target-the-net-standard"></a><span data-ttu-id="78a18-128">Come definire .NET Standard come destinazione</span><span class="sxs-lookup"><span data-stu-id="78a18-128">How to target the .NET Standard</span></span>

<span data-ttu-id="78a18-129">Se non si ha molta familiarità con .NET Standard, leggere l'articolo [.NET Standard](../../standard/net-standard.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="78a18-129">If you're not quite familiar with the .NET Standard, refer to the [.NET Standard](../../standard/net-standard.md) to learn more.</span></span>

<span data-ttu-id="78a18-130">In questo articolo è presente una tabella in cui le diverse versioni di .NET Standard sono associate alle varie implementazioni:</span><span class="sxs-lookup"><span data-stu-id="78a18-130">In that article, there is a table which maps .NET Standard versions to various implementations:</span></span>

[!INCLUDE [net-standard-table](~/includes/net-standard-table.md)]

<span data-ttu-id="78a18-131">Ecco cosa significa questa tabella ai fini della creazione di una libreria:</span><span class="sxs-lookup"><span data-stu-id="78a18-131">Here's what this table means for the purposes of creating a library:</span></span>

<span data-ttu-id="78a18-132">La versione di .NET Standard selezionata sarà un compromesso tra l'accesso alle API più recenti e la possibilità di definire come destinazione più implementazioni di .NET e versioni di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="78a18-132">The version of the .NET Standard you pick will be a tradeoff between access to the newest APIs and the ability to target more .NET implementations and .NET Standard versions.</span></span> <span data-ttu-id="78a18-133">Per controllare l'intervallo di piattaforme e versioni definibili come destinazione selezionare una versione di `netstandardX.X` (dove `X.X` è un numero di versione) e aggiungerla al file di progetto (`.csproj` o `.fsproj`).</span><span class="sxs-lookup"><span data-stu-id="78a18-133">You control the range of targetable platforms and versions by picking a version of `netstandardX.X` (Where `X.X` is a version number) and adding it to your project file (`.csproj` or `.fsproj`).</span></span>

<span data-ttu-id="78a18-134">Quando si definisce .NET Standard come destinazione sono disponibili tre opzioni principali, a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="78a18-134">You have three primary options when targeting the .NET Standard, depending on your needs.</span></span>

1. <span data-ttu-id="78a18-135">È possibile usare la versione predefinita di .NET Standard inclusa nei modelli (`netstandard1.4`) che offre l'accesso alla maggior parte delle API .NET Standard pur essendo compatibile con UWP, .NET Framework 4.6.1 e con l'imminente .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="78a18-135">You can use the default version of the .NET Standard supplied by templates - `netstandard1.4` - which gives you access to most APIs on .NET Standard while still being compatible with UWP, .NET Framework 4.6.1, and the forthcoming .NET Standard 2.0.</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>netstandard1.4</TargetFramework>
      </PropertyGroup>
    </Project>
    ```

2. <span data-ttu-id="78a18-136">È possibile usare una versione inferiore o superiore di .NET Standard modificando il valore nel nodo `TargetFramework` del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="78a18-136">You can use a lower or higher version of the .NET Standard by modifying the value in the `TargetFramework` node of your project file.</span></span>
    
    <span data-ttu-id="78a18-137">Le versioni di .NET Standard sono compatibili con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="78a18-137">.NET Standard versions are backward compatible.</span></span> <span data-ttu-id="78a18-138">Ciò significa che le librerie `netstandard1.0` possono essere eseguite su piattaforme `netstandard1.1` e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="78a18-138">That means that `netstandard1.0` libraries run on `netstandard1.1` platforms and higher.</span></span> <span data-ttu-id="78a18-139">Tuttavia, non è prevista la compatibilità con le versioni successive. Le piattaforme .NET Standard precedenti non possono fare riferimento a quelle più recenti.</span><span class="sxs-lookup"><span data-stu-id="78a18-139">However, there is no forward compatibility - lower .NET Standard platforms cannot reference higher ones.</span></span> <span data-ttu-id="78a18-140">Ciò significa che le librerie `netstandard1.0` non possono fare riferimento alle librerie `netstandard1.1` o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="78a18-140">This means that `netstandard1.0` libraries cannot reference libraries targeting `netstandard1.1` or higher.</span></span> <span data-ttu-id="78a18-141">Selezionare la versione di .NET Standard che contiene la combinazione di API e supporto per piattaforme più adatta alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="78a18-141">Select the Standard version that has the right mix of APIs and platform support for your needs.</span></span> <span data-ttu-id="78a18-142">Attualmente è consigliabile selezionare `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="78a18-142">We recommend `netstandard1.4` for now.</span></span>
    
3. <span data-ttu-id="78a18-143">Se si vuole definire come destinazione .NET Framework 4.0 o versione precedente, o si desidera usare un'API disponibile in .NET Framework ma non in .NET Standard (ad esempio, `System.Drawing`), leggere le sezioni seguenti per apprendere come definire più destinazioni.</span><span class="sxs-lookup"><span data-stu-id="78a18-143">If you want to target the .NET Framework versions 4.0 or below, or you wish to use an API available in the .NET Framework but not in the .NET Standard (for example, `System.Drawing`), read the following sections and learn how to multitarget.</span></span>

## <a name="how-to-target-the-net-framework"></a><span data-ttu-id="78a18-144">Come definire .NET Framework come destinazione</span><span class="sxs-lookup"><span data-stu-id="78a18-144">How to target the .NET Framework</span></span>

> [!NOTE]
> <span data-ttu-id="78a18-145">Queste istruzioni presuppongono che nel computer sia installato .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="78a18-145">These instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="78a18-146">Vedere la sezione [Prerequisiti](#prerequisites) per informazioni sulle dipendenze da installare.</span><span class="sxs-lookup"><span data-stu-id="78a18-146">Refer to the [Prerequisites](#prerequisites) to get dependencies installed.</span></span>

<span data-ttu-id="78a18-147">Tenere presente che alcune delle versioni di .NET Framework indicate in questo argomento non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="78a18-147">Keep in mind that some of the .NET Framework versions used here are no longer in support.</span></span> <span data-ttu-id="78a18-148">Per informazioni sulle versioni non supportate, vedere [Domande frequenti sui criteri relativi al ciclo di vita del supporto per Microsoft .NET Framework](https://support.microsoft.com/gp/framework_faq/en-us).</span><span class="sxs-lookup"><span data-stu-id="78a18-148">Refer to the [.NET Framework Support Lifecycle Policy FAQ](https://support.microsoft.com/gp/framework_faq/en-us) about unsupported versions.</span></span>

<span data-ttu-id="78a18-149">Se si vuole raggiungere il numero massimo di sviluppatori e progetti, usare .NET Framework 4.0 come destinazione di base.</span><span class="sxs-lookup"><span data-stu-id="78a18-149">If you want to reach the maximum number of developers and projects, use the .NET Framework 4.0 as your baseline target.</span></span> <span data-ttu-id="78a18-150">Per definire .NET Framework come destinazione, è necessario iniziare usando il TFM (Target Framework Moniker) corretto, corrispondente alla versione di .NET Framework da supportare.</span><span class="sxs-lookup"><span data-stu-id="78a18-150">To target the .NET Framework, you will need to begin by using the correct Target Framework Moniker (TFM) that corresponds to the .NET Framework version you wish to support.</span></span>

```
.NET Framework 2.0   --> net20
.NET Framework 3.0   --> net30
.NET Framework 3.5   --> net35
.NET Framework 4.0   --> net40
.NET Framework 4.5   --> net45
.NET Framework 4.5.1 --> net451
.NET Framework 4.5.2 --> net452
.NET Framework 4.6   --> net46
.NET Framework 4.6.1 --> net461
.NET Framework 4.6.2 --> net462
.NET Framework 4.7   --> net47
```

<span data-ttu-id="78a18-151">Quindi inserire il TFM nella sezione `TargetFramework` del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="78a18-151">You then insert this TFM into the `TargetFramework` section of your project file.</span></span> <span data-ttu-id="78a18-152">Ad esempio, ecco come scrivere una libreria con destinazione .NET Framework 4.0:</span><span class="sxs-lookup"><span data-stu-id="78a18-152">For example, here's how you would write a library which targets the .NET Framework 4.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="78a18-153">L'operazione è ora completata.</span><span class="sxs-lookup"><span data-stu-id="78a18-153">And that's it!</span></span> <span data-ttu-id="78a18-154">Anche se compilata solo per .NET Framework 4, la libreria può essere usata nelle versioni più recenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="78a18-154">Although this compiled only for the .NET Framework 4, you can use the library on newer versions of the .NET Framework.</span></span>

## <a name="how-to-multitarget"></a><span data-ttu-id="78a18-155">Come definire più destinazioni</span><span class="sxs-lookup"><span data-stu-id="78a18-155">How to Multitarget</span></span>

> [!NOTE]
> <span data-ttu-id="78a18-156">Le istruzioni seguenti presuppongono che nel computer sia installato .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="78a18-156">The following instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="78a18-157">Vedere la sezione [Prerequisiti](#prerequisites) per informazioni sulle dipendenze da installare e sull'area da cui scaricarle.</span><span class="sxs-lookup"><span data-stu-id="78a18-157">Refer to the [Prerequisites](#prerequisites) section to learn which dependencies you need to install and where to download them from.</span></span>

<span data-ttu-id="78a18-158">Quando il progetto supporta sia .NET Framework che .NET Core, può essere opportuno definire come destinazione le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="78a18-158">You may need to target older versions of the .NET Framework when your project supports both the .NET Framework and .NET Core.</span></span> <span data-ttu-id="78a18-159">In questo scenario, per usare API e costrutti di linguaggio più recenti per le destinazioni più recenti, inserire direttive `#if` nel codice.</span><span class="sxs-lookup"><span data-stu-id="78a18-159">In this scenario, if you want to use newer APIs and language constructs for the newer targets, use `#if` directives in your code.</span></span> <span data-ttu-id="78a18-160">Può anche essere necessario aggiungere diversi pacchetti e dipendenze per ogni piattaforma di destinazione per includere le diverse API necessarie per ogni caso.</span><span class="sxs-lookup"><span data-stu-id="78a18-160">You also might need to add different packages and dependencies for each platform you're targeting to include the different APIs needed for each case.</span></span>

<span data-ttu-id="78a18-161">Si supponga ad esempio di avere una libreria che esegue operazioni di rete tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="78a18-161">For example, let's say you have a library that performs networking operations over HTTP.</span></span> <span data-ttu-id="78a18-162">Per .NET Standard e .NET Framework 4.5 o versioni successive, è possibile usare la classe `HttpClient` dello spazio dei nomi `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="78a18-162">For .NET Standard and the .NET Framework versions 4.5 or higher, you can use the `HttpClient` class from the `System.Net.Http` namespace.</span></span> <span data-ttu-id="78a18-163">Tuttavia, le versioni precedenti di .NET Framework non dispongono della classe `HttpClient` e per tali versioni è quindi possibile usare in alternativa la classe `WebClient` dello spazio dei nomi `System.Net`.</span><span class="sxs-lookup"><span data-stu-id="78a18-163">However, earlier versions of the .NET Framework don't have the `HttpClient` class, so you could use the `WebClient` class from the `System.Net` namespace for those instead.</span></span>

<span data-ttu-id="78a18-164">Il file di progetto può avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="78a18-164">Your project file could look like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.0 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net40'">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Need to conditionally bring in references for the .NET Framework 4.5 target -->
  <ItemGroup Condition="'$(TargetFramework)' == 'net45'">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="78a18-165">Si noteranno tre modifiche principali:</span><span class="sxs-lookup"><span data-stu-id="78a18-165">You'll notice three major changes here:</span></span>

1. <span data-ttu-id="78a18-166">Il nodo `TargetFramework` è stato sostituito da `TargetFrameworks` e all'interno sono espressi tre TFM.</span><span class="sxs-lookup"><span data-stu-id="78a18-166">The `TargetFramework` node has been replaced by `TargetFrameworks`, and three TFMs are expressed inside.</span></span>
1. <span data-ttu-id="78a18-167">Un nodo `<ItemGroup>` per la destinazione `net40 ` chiama un riferimento di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="78a18-167">There is an `<ItemGroup>` node for the `net40 ` target pulling in one .NET Framework reference.</span></span>
1. <span data-ttu-id="78a18-168">Un nodo `<ItemGroup>` per la destinazione `net45` chiama due riferimenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="78a18-168">There is an `<ItemGroup>` node for the `net45` target pulling in two .NET Framework references.</span></span>

<span data-ttu-id="78a18-169">Il sistema di compilazione è in grado di riconoscere i seguenti simboli di preprocessore usati nelle direttive `#if`:</span><span class="sxs-lookup"><span data-stu-id="78a18-169">The build system is aware of the following preprocessor symbols used in `#if` directives:</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

<span data-ttu-id="78a18-170">Ecco un esempio che usa la compilazione condizionale basata sulla destinazione:</span><span class="sxs-lookup"><span data-stu-id="78a18-170">Here is an example making use of conditional compilation per-target:</span></span>

```csharp
using System;
using System.Text.RegularExpressions;
#if NET40
// This only compiles for the .NET Framework 4 targets
using System.Net;
#else
 // This compiles for all other targets
using System.Net.Http;
using System.Threading.Tasks;
#endif

namespace MultitargetLib
{
    public class Library
    {
#if NET40
        private readonly WebClient _client = new WebClient();
        private readonly object _locker = new object();
#else
        private readonly HttpClient _client = new HttpClient();
#endif

#if NET40
        // .NET Framework 4.0 does not have async/await
        public string GetDotNetCount()
        {
            string url = "http://www.dotnetfoundation.org/";

            var uri = new Uri(url);

            string result = "";

            // Lock here to provide thread-safety.
            lock(_locker)
            {
                result = _client.DownloadString(uri);
            }

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"Dotnet Foundation mentions .NET {dotNetCount} times!";
        }
#else
        // .NET 4.5+ can use async/await!
        public async Task<string> GetDotNetCountAsync()
        {
            string url = "http://www.dotnetfoundation.org/";

            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"dotnetfoundation.org mentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
}
```

<span data-ttu-id="78a18-171">Se si compila il progetto con `dotnet build` si noteranno tre directory sotto la cartella `bin/`:</span><span class="sxs-lookup"><span data-stu-id="78a18-171">If you build this project with `dotnet build`, you'll notice three directories under the `bin/` folder:</span></span>

```
net40/
net45/
netstandard1.4/
```

<span data-ttu-id="78a18-172">Ogni directory contiene i file `.dll` per ciascuna destinazione.</span><span class="sxs-lookup"><span data-stu-id="78a18-172">Each of these contain the `.dll` files for each target.</span></span>

## <a name="how-to-test-libraries-on-net-core"></a><span data-ttu-id="78a18-173">Come testare le librerie in .NET Core</span><span class="sxs-lookup"><span data-stu-id="78a18-173">How to test libraries on .NET Core</span></span>

<span data-ttu-id="78a18-174">È importante essere in grado di eseguire test tra diverse piattaforme.</span><span class="sxs-lookup"><span data-stu-id="78a18-174">It's important to be able to test across platforms.</span></span> <span data-ttu-id="78a18-175">È possibile usare [xUnit](http://xunit.github.io/) o MSTest senza modifiche.</span><span class="sxs-lookup"><span data-stu-id="78a18-175">You can use either [xUnit](http://xunit.github.io/) or MSTest out of the box.</span></span> <span data-ttu-id="78a18-176">Entrambi sono adatti per gli unit test della libreria in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="78a18-176">Both are perfectly suitable for unit testing your library on .NET Core.</span></span> <span data-ttu-id="78a18-177">La modalità di configurazione della soluzione con progetti di test dipende dalla [struttura della soluzione](#structuring-a-solution).</span><span class="sxs-lookup"><span data-stu-id="78a18-177">How you set up your solution with test projects will depend on the [structure of your solution](#structuring-a-solution).</span></span> <span data-ttu-id="78a18-178">Nell'esempio seguente si presuppone che le directory di test e di origine si trovino nella stessa directory di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="78a18-178">The following example assumes that the test and source directories live in the same top-level directory.</span></span>

> [!NOTE]
> <span data-ttu-id="78a18-179">Questa procedura usa alcuni [comandi dell'interfaccia della riga di comando di .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="78a18-179">This uses some [.NET Core CLI commands](../tools/index.md).</span></span> <span data-ttu-id="78a18-180">Per altre informazioni, vedere [dotnet new](../tools/dotnet-new.md) e [dotnet sln](../tools/dotnet-sln.md).</span><span class="sxs-lookup"><span data-stu-id="78a18-180">See [dotnet new](../tools/dotnet-new.md) and [dotnet sln](../tools/dotnet-sln.md) for more information.</span></span>

1. <span data-ttu-id="78a18-181">Configurare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="78a18-181">Set up your solution.</span></span> <span data-ttu-id="78a18-182">È possibile farlo con i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="78a18-182">You can do so with the following commands:</span></span>

   ```bash
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   <span data-ttu-id="78a18-183">I progetti vengono creati e collegati in una soluzione.</span><span class="sxs-lookup"><span data-stu-id="78a18-183">This will create projects and link them together in a solution.</span></span> <span data-ttu-id="78a18-184">La directory per `SolutionWithSrcAndTest` ha un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="78a18-184">Your directory for `SolutionWithSrcAndTest` should look like this:</span></span>

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. <span data-ttu-id="78a18-185">Passare alla directory del progetto di test e aggiungere un riferimento a `MyProject.Test` da `MyProject`.</span><span class="sxs-lookup"><span data-stu-id="78a18-185">Navigate to the test project's directory and add a reference to `MyProject.Test` from `MyProject`.</span></span>

   ```bash
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. <span data-ttu-id="78a18-186">Ripristinare i pacchetti e compilare i progetti:</span><span class="sxs-lookup"><span data-stu-id="78a18-186">Restore packages and build projects:</span></span>

   ```bash
   dotnet restore
   dotnet build
   ```

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

1. <span data-ttu-id="78a18-187">Verificare che xUnit sia in esecuzione con il comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="78a18-187">Verify that xUnit runs by executing the `dotnet test` command.</span></span> <span data-ttu-id="78a18-188">Se si sceglie di usare MSTest, va invece eseguita l'utilità di test delle console MSTest.</span><span class="sxs-lookup"><span data-stu-id="78a18-188">If you chose to use MSTest, then the MSTest console runner should run instead.</span></span>
    
<span data-ttu-id="78a18-189">L'operazione è ora completata.</span><span class="sxs-lookup"><span data-stu-id="78a18-189">And that's it!</span></span> <span data-ttu-id="78a18-190">È ora possibile testare la libreria su tutte le piattaforme usando gli strumenti da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="78a18-190">You can now test your library across all platforms using command line tools.</span></span> <span data-ttu-id="78a18-191">Una volta completata la configurazione, è possibile procedere con il testing della libreria in modo molto semplice:</span><span class="sxs-lookup"><span data-stu-id="78a18-191">To continue testing now that you have everything set up, testing your library is very simple:</span></span>

1. <span data-ttu-id="78a18-192">Eseguire le opportune modifiche nella libreria.</span><span class="sxs-lookup"><span data-stu-id="78a18-192">Make changes to your library.</span></span>
1. <span data-ttu-id="78a18-193">Eseguire i test dalla riga di comando, nella directory di test, usando il comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="78a18-193">Run tests from the command line, in your test directory, with `dotnet test` command.</span></span>

<span data-ttu-id="78a18-194">Il codice viene ricompilato automaticamente quando si richiama il comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="78a18-194">Your code will be automatically rebuilt when you invoke `dotnet test` command.</span></span>

## <a name="how-to-use-multiple-projects"></a><span data-ttu-id="78a18-195">Come usare più progetti</span><span class="sxs-lookup"><span data-stu-id="78a18-195">How to use multiple projects</span></span>

<span data-ttu-id="78a18-196">Per le librerie di maggiori dimensioni, è spesso necessario inserire funzionalità in progetti diversi.</span><span class="sxs-lookup"><span data-stu-id="78a18-196">A common need for larger libraries is to place functionality in different projects.</span></span>

<span data-ttu-id="78a18-197">Si supponga di voler creare una libreria che sia utilizzabile in C# e F# idiomatico.</span><span class="sxs-lookup"><span data-stu-id="78a18-197">Imagine you wished to build a library which could be consumed in idiomatic C# and F#.</span></span> <span data-ttu-id="78a18-198">Ciò significa che la libreria viene utilizzata in modi che sono naturali per C# o F#.</span><span class="sxs-lookup"><span data-stu-id="78a18-198">That would mean that consumers of your library consume them in ways which are natural to C# or F#.</span></span> <span data-ttu-id="78a18-199">In C#, ad esempio, la libreria può essere utilizzata in un modo simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="78a18-199">For example, in C# you might consume the library like this:</span></span>

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

<span data-ttu-id="78a18-200">In F#, invece, può assumere l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="78a18-200">In F#, it might look like this:</span></span>

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

<span data-ttu-id="78a18-201">Scenari di utilizzo come questo indicano che le API a cui si accede devono avere una struttura diversa per C# e F#.</span><span class="sxs-lookup"><span data-stu-id="78a18-201">Consumption scenarios like this mean that the APIs being accessed have to have a different structure for C# and F#.</span></span>  <span data-ttu-id="78a18-202">Un approccio comune per gestire questa situazione consiste nel definire l'intera logica di una libreria in un progetto di base, a cui eseguono chiamate i livelli di API definiti nei progetti C# e F#.</span><span class="sxs-lookup"><span data-stu-id="78a18-202">A common approach to accomplishing this is to factor all of the logic of a library into a core project, with C# and F# projects defining the API layers that call into that core project.</span></span>  <span data-ttu-id="78a18-203">Nella parte restante della sezione verranno usati i nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="78a18-203">The rest of the section will use the following names:</span></span>

* <span data-ttu-id="78a18-204">**AwesomeLibrary.Core**: un progetto di base che contiene tutta la logica della libreria</span><span class="sxs-lookup"><span data-stu-id="78a18-204">**AwesomeLibrary.Core** - A core project which contains all logic for the library</span></span>
* <span data-ttu-id="78a18-205">**AwesomeLibrary.CSharp**: un progetto con API pubbliche destinato all'utilizzo in C#</span><span class="sxs-lookup"><span data-stu-id="78a18-205">**AwesomeLibrary.CSharp** - A project with public APIs intended for consumption in C#</span></span>
* <span data-ttu-id="78a18-206">**AwesomeLibrary.FSharp**: un progetto con API pubbliche destinato all'utilizzo in F#</span><span class="sxs-lookup"><span data-stu-id="78a18-206">**AwesomeLibrary.FSharp** - A project with public APIs intended for consumption in F#</span></span>

<span data-ttu-id="78a18-207">Eseguire i seguenti comandi nel terminale in uso per ottenere la stessa struttura mostrata in questa Guida:</span><span class="sxs-lookup"><span data-stu-id="78a18-207">You can run the following commands in your terminal to produce the same structure as this guide:</span></span>

```console
mkdir AwesomeLibrary && cd AwesomeLibrary
dotnet new sln
mkdir AwesomeLibrary.Core && cd AwesomeLibrary.Core && dotnet new classlib
cd ..
mkdir AwesomeLibrary.CSharp && cd AwesomeLibrary.CSharp && dotnet new classlib
cd ..
mkdir AwesomeLibrary.FSharp && cd AwesomeLibrary.FSharp && dotnet new classlib -lang F#
cd ..
dotnet sln add AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
dotnet sln add AwesomeLibrary.CSharp/AwesomeLibrary.CSharp.csproj
dotnet sln add AwesomeLibrary.FSharp/AwesomeLibrary.FSharp.fsproj
```

<span data-ttu-id="78a18-208">Verranno aggiunti i tre progetti precedenti e un file soluzione che li collega.</span><span class="sxs-lookup"><span data-stu-id="78a18-208">This will add the three projects above and a solution file which links them together.</span></span> <span data-ttu-id="78a18-209">La creazione del file di soluzione e il collegamento dei progetti consentono di ripristinare e compilare i progetti da un livello superiore.</span><span class="sxs-lookup"><span data-stu-id="78a18-209">Creating the solution file and linking projects will allow you to restore and build projects from a top-level.</span></span>

### <a name="project-to-project-referencing"></a><span data-ttu-id="78a18-210">Definizione di riferimenti da progetto a progetto</span><span class="sxs-lookup"><span data-stu-id="78a18-210">Project-to-project referencing</span></span>

<span data-ttu-id="78a18-211">Il modo migliore per creare un riferimento a un progetto è l'uso dell'interfaccia della riga di comando di .NET Core per aggiungere un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="78a18-211">The best way to reference a project is to use the .NET Core CLI to add a project reference.</span></span> <span data-ttu-id="78a18-212">Dalle directory di progetto **AwesomeLibrary.CSharp** e **AwesomeLibrary.FSharp** è possibile eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="78a18-212">From the **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** project directories, you can run the following command:</span></span>

```console
$ dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

<span data-ttu-id="78a18-213">I file di progetto per **AwesomeLibrary.CSharp** e **AwesomeLibrary.FSharp** includeranno ora un riferimento a **AwesomeLibrary.Core** come destinazione `ProjectReference`.</span><span class="sxs-lookup"><span data-stu-id="78a18-213">The project files for both **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** will now reference **AwesomeLibrary.Core** as a `ProjectReference` target.</span></span>  <span data-ttu-id="78a18-214">È possibile verificare la presenza del riferimento cercando quanto segue nei file di progetto:</span><span class="sxs-lookup"><span data-stu-id="78a18-214">You can verify this by inspecting the project files and seeing the following in them:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

<span data-ttu-id="78a18-215">Se si preferisce non usare l'interfaccia della riga di comando .NET Core, è possibile aggiungere manualmente questa sezione a ogni file di progetto.</span><span class="sxs-lookup"><span data-stu-id="78a18-215">You can add this section to each project file manually if you prefer not to use the .NET Core CLI.</span></span>

### <a name="structuring-a-solution"></a><span data-ttu-id="78a18-216">Definizione della struttura di una soluzione</span><span class="sxs-lookup"><span data-stu-id="78a18-216">Structuring a solution</span></span>

<span data-ttu-id="78a18-217">Un altro aspetto importante delle soluzioni basate su più progetti è quello di stabilire una buona struttura complessiva dei progetti.</span><span class="sxs-lookup"><span data-stu-id="78a18-217">Another important aspect of multi-project solutions is establishing a good overall project structure.</span></span> <span data-ttu-id="78a18-218">È possibile organizzare il codice come desiderato. A condizione che si colleghi ogni progetto al file di soluzione mediante `dotnet sln add`, sarà possibile eseguire `dotnet restore` e `dotnet build` a livello della soluzione.</span><span class="sxs-lookup"><span data-stu-id="78a18-218">You can organize code however you like, and as long as you link each project to your solution file with `dotnet sln add`, you will be able to run `dotnet restore` and `dotnet build` at the solution level.</span></span>
