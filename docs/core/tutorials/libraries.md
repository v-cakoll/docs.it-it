---
title: Sviluppare librerie con l'interfaccia della riga di comando di .NET CoreDevelop libraries with the .NET Core CLI
description: Informazioni su come creare librerie .NET Core usando l'interfaccia della riga di comando di .NET Core.Learn how to create .NET Core libraries using the .NET Core CLI. Si creerà una libreria che supporta più framework.
author: cartermp
ms.date: 05/01/2017
ms.openlocfilehash: c23c1f027b4d6d09c50eb2257d34f72ec56302f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503500"
---
# <a name="develop-libraries-with-the-net-core-cli"></a><span data-ttu-id="7b586-104">Sviluppare librerie con l'interfaccia della riga di comando di .NET CoreDevelop libraries with the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="7b586-104">Develop libraries with the .NET Core CLI</span></span>

<span data-ttu-id="7b586-105">In questo articolo viene illustrato come scrivere librerie per .NET utilizzando l'interfaccia della riga di comando di .NET Core.This article covers how to write libraries for .NET using the .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="7b586-105">This article covers how to write libraries for .NET using the .NET Core CLI.</span></span> <span data-ttu-id="7b586-106">L'interfaccia della riga di comando offre un'esperienza efficace e di basso livello per qualsiasi sistema operativo supportato.</span><span class="sxs-lookup"><span data-stu-id="7b586-106">The CLI provides an efficient and low-level experience that works across any supported OS.</span></span> <span data-ttu-id="7b586-107">È comunque sempre possibile creare librerie con Visual Studio. Se si preferisce questo tipo di esperienza, [consultare la Guida di Visual Studio](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="7b586-107">You can still build libraries with Visual Studio, and if that is your preferred experience [refer to the Visual Studio guide](library-with-visual-studio.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7b586-108">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="7b586-108">Prerequisites</span></span>

<span data-ttu-id="7b586-109">È necessario che [l'SDK e l'interfaccia della riga di comando di .NET Core](https://dotnet.microsoft.com/download) siano installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="7b586-109">You need [the .NET Core SDK and CLI](https://dotnet.microsoft.com/download) installed on your machine.</span></span>

<span data-ttu-id="7b586-110">Per le sezioni di questo documento relative alle versioni di .NET Framework è necessario avere [.NET Framework](https://dotnet.microsoft.com) installato in un computer Windows.</span><span class="sxs-lookup"><span data-stu-id="7b586-110">For the sections of this document dealing with .NET Framework versions, you need the [.NET Framework](https://dotnet.microsoft.com) installed on a Windows machine.</span></span>

<span data-ttu-id="7b586-111">Inoltre, se si desidera supportare destinazioni .NET Framework meno recenti, è necessario installare i pacchetti di destinazione o i pacchetti per sviluppatori dalla pagina archivi di download di [.NET.](https://dotnet.microsoft.com/download/archives)</span><span class="sxs-lookup"><span data-stu-id="7b586-111">Additionally, if you wish to support older .NET Framework targets, you need to install targeting packs or developer packs from the [.NET download archives page](https://dotnet.microsoft.com/download/archives).</span></span> <span data-ttu-id="7b586-112">Fare riferimento a questa tabella:</span><span class="sxs-lookup"><span data-stu-id="7b586-112">Refer to this table:</span></span>

| <span data-ttu-id="7b586-113">Versione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7b586-113">.NET Framework version</span></span> | <span data-ttu-id="7b586-114">Pacchetto da scaricare</span><span class="sxs-lookup"><span data-stu-id="7b586-114">What to download</span></span>                                       |
| ---------------------- | ------------------------------------------------------ |
| <span data-ttu-id="7b586-115">4.6.1</span><span class="sxs-lookup"><span data-stu-id="7b586-115">4.6.1</span></span>                  | <span data-ttu-id="7b586-116">.NET Framework 4.6.1 Targeting Pack</span><span class="sxs-lookup"><span data-stu-id="7b586-116">.NET Framework 4.6.1 Targeting Pack</span></span>                    |
| <span data-ttu-id="7b586-117">4.6</span><span class="sxs-lookup"><span data-stu-id="7b586-117">4.6</span></span>                    | <span data-ttu-id="7b586-118">.NET Framework 4.6 Targeting Pack</span><span class="sxs-lookup"><span data-stu-id="7b586-118">.NET Framework 4.6 Targeting Pack</span></span>                      |
| <span data-ttu-id="7b586-119">4.5.2</span><span class="sxs-lookup"><span data-stu-id="7b586-119">4.5.2</span></span>                  | <span data-ttu-id="7b586-120">.NET Framework 4.5.2 Developer Pack</span><span class="sxs-lookup"><span data-stu-id="7b586-120">.NET Framework 4.5.2 Developer Pack</span></span>                    |
| <span data-ttu-id="7b586-121">4.5.1</span><span class="sxs-lookup"><span data-stu-id="7b586-121">4.5.1</span></span>                  | <span data-ttu-id="7b586-122">.NET Framework 4.5.1 Developer Pack</span><span class="sxs-lookup"><span data-stu-id="7b586-122">.NET Framework 4.5.1 Developer Pack</span></span>                    |
| <span data-ttu-id="7b586-123">4.5</span><span class="sxs-lookup"><span data-stu-id="7b586-123">4.5</span></span>                    | <span data-ttu-id="7b586-124">Windows Software Development Kit per Windows 8</span><span class="sxs-lookup"><span data-stu-id="7b586-124">Windows Software Development Kit for Windows 8</span></span>         |
| <span data-ttu-id="7b586-125">4.0</span><span class="sxs-lookup"><span data-stu-id="7b586-125">4.0</span></span>                    | <span data-ttu-id="7b586-126">Windows SDK per Windows 7 e .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="7b586-126">Windows SDK for Windows 7 and .NET Framework 4</span></span>         |
| <span data-ttu-id="7b586-127">2.0, 3.0 e 3.5</span><span class="sxs-lookup"><span data-stu-id="7b586-127">2.0, 3.0, and 3.5</span></span>      | <span data-ttu-id="7b586-128">Runtime di .NET Framework 3.5 SP1 (o versione per Windows 8 o successiva)</span><span class="sxs-lookup"><span data-stu-id="7b586-128">.NET Framework 3.5 SP1 Runtime (or Windows 8+ version)</span></span> |

## <a name="how-to-target-the-net-standard"></a><span data-ttu-id="7b586-129">Come definire .NET Standard come destinazione</span><span class="sxs-lookup"><span data-stu-id="7b586-129">How to target the .NET Standard</span></span>

<span data-ttu-id="7b586-130">Se non si ha familiarità con .NET Standard, fare riferimento a [.NET Standard](../../standard/net-standard.md) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="7b586-130">If you're not familiar with .NET Standard, refer to [.NET Standard](../../standard/net-standard.md) to learn more.</span></span>

<span data-ttu-id="7b586-131">In questo articolo è disponibile una tabella che esegue il mapping delle versioni di .NET Standard a varie implementazioni:In that article, there is a table that maps .NET Standard versions to various implementations:</span><span class="sxs-lookup"><span data-stu-id="7b586-131">In that article, there is a table that maps .NET Standard versions to various implementations:</span></span>

[!INCLUDE [net-standard-table](../../../includes/net-standard-table.md)]

<span data-ttu-id="7b586-132">Ecco cosa significa questa tabella ai fini della creazione di una libreria:</span><span class="sxs-lookup"><span data-stu-id="7b586-132">Here's what this table means for the purposes of creating a library:</span></span>

<span data-ttu-id="7b586-133">La versione di .NET Standard scelta sarà un compromesso tra l'accesso alle API più recenti e la possibilità di scegliere come destinazione più implementazioni .NET e versioni di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="7b586-133">The version of .NET Standard you pick will be a tradeoff between access to the newest APIs and the ability to target more .NET implementations and .NET Standard versions.</span></span> <span data-ttu-id="7b586-134">È possibile controllare l'intervallo di piattaforme `netstandardX.X` e `X.X` versioni destinabili selezionando una versione di`.csproj` `.fsproj`(dove è un numero di versione) e aggiungendola al file di progetto ( o o ).</span><span class="sxs-lookup"><span data-stu-id="7b586-134">You control the range of targetable platforms and versions by picking a version of `netstandardX.X` (where `X.X` is a version number) and adding it to your project file (`.csproj` or `.fsproj`).</span></span>

<span data-ttu-id="7b586-135">Sono disponibili tre opzioni principali quando si ha come destinazione .NET Standard, a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="7b586-135">You have three primary options when targeting .NET Standard, depending on your needs.</span></span>

1. <span data-ttu-id="7b586-136">È possibile utilizzare la versione predefinita di .NET Standard fornita dai modelli, `netstandard1.4`, che consente di accedere alla maggior parte delle API in .NET Standard pur rimanendo compatibile con UWP, .NET Framework 4.6.1 e .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="7b586-136">You can use the default version of .NET Standard supplied by templates, `netstandard1.4`, which gives you access to most APIs on .NET Standard while still being compatible with UWP, .NET Framework 4.6.1, and .NET Standard 2.0.</span></span>

    ```xml
    <Project Sdk="Microsoft.NET.Sdk">
      <PropertyGroup>
        <TargetFramework>netstandard1.4</TargetFramework>
      </PropertyGroup>
    </Project>
    ```

2. <span data-ttu-id="7b586-137">È possibile utilizzare una versione inferiore o superiore di `TargetFramework` .NET Standard modificando il valore nel nodo del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="7b586-137">You can use a lower or higher version of .NET Standard by modifying the value in the `TargetFramework` node of your project file.</span></span>

    <span data-ttu-id="7b586-138">Le versioni di .NET Standard sono compatibili con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="7b586-138">.NET Standard versions are backward compatible.</span></span> <span data-ttu-id="7b586-139">Ciò significa che le librerie `netstandard1.0` possono essere eseguite su piattaforme `netstandard1.1` e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="7b586-139">That means that `netstandard1.0` libraries run on `netstandard1.1` platforms and higher.</span></span> <span data-ttu-id="7b586-140">Tuttavia, non esiste alcuna compatibilità in avanti.</span><span class="sxs-lookup"><span data-stu-id="7b586-140">However, there is no forward compatibility.</span></span> <span data-ttu-id="7b586-141">Le piattaforme .NET Standard inferiori non possono fare riferimento a quelle più alte.</span><span class="sxs-lookup"><span data-stu-id="7b586-141">Lower .NET Standard platforms cannot reference higher ones.</span></span> <span data-ttu-id="7b586-142">Ciò significa che le librerie `netstandard1.0` non possono fare riferimento alle librerie `netstandard1.1` o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="7b586-142">This means that `netstandard1.0` libraries cannot reference libraries targeting `netstandard1.1` or higher.</span></span> <span data-ttu-id="7b586-143">Selezionare la versione di .NET Standard che contiene la combinazione di API e supporto per piattaforme più adatta alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="7b586-143">Select the Standard version that has the right mix of APIs and platform support for your needs.</span></span> <span data-ttu-id="7b586-144">Attualmente è consigliabile selezionare `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="7b586-144">We recommend `netstandard1.4` for now.</span></span>

3. <span data-ttu-id="7b586-145">Se si desidera impostare come destinazione .NET Framework versioni successive 4.0 o successive oppure utilizzare un'API disponibile in .NET Framework ma non in .NET Standard (ad esempio, `System.Drawing`), leggere le sezioni seguenti e scoprire come multitargeting.</span><span class="sxs-lookup"><span data-stu-id="7b586-145">If you want to target .NET Framework versions 4.0 or below, or you wish to use an API available in .NET Framework but not in .NET Standard (for example, `System.Drawing`), read the following sections and learn how to multitarget.</span></span>

## <a name="how-to-target-net-framework"></a><span data-ttu-id="7b586-146">Come scegliere come destinazione .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7b586-146">How to target .NET Framework</span></span>

> [!NOTE]
> <span data-ttu-id="7b586-147">Queste istruzioni presuppongono che nel computer sia installato .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7b586-147">These instructions assume you have .NET Framework installed on your machine.</span></span> <span data-ttu-id="7b586-148">Vedere la sezione [Prerequisiti](#prerequisites) per informazioni sulle dipendenze da installare.</span><span class="sxs-lookup"><span data-stu-id="7b586-148">Refer to the [Prerequisites](#prerequisites) to get dependencies installed.</span></span>

<span data-ttu-id="7b586-149">Tenere presente che alcune delle versioni di .NET Framework utilizzate qui non sono più supportate.</span><span class="sxs-lookup"><span data-stu-id="7b586-149">Keep in mind that some of the .NET Framework versions used here are no longer supported.</span></span> <span data-ttu-id="7b586-150">Per informazioni sulle versioni non supportate, vedere [Domande frequenti sui criteri relativi al ciclo di vita del supporto per Microsoft .NET Framework](https://support.microsoft.com/gp/framework_faq/en-us).</span><span class="sxs-lookup"><span data-stu-id="7b586-150">Refer to the [.NET Framework Support Lifecycle Policy FAQ](https://support.microsoft.com/gp/framework_faq/en-us) about unsupported versions.</span></span>

<span data-ttu-id="7b586-151">Se si desidera raggiungere il numero massimo di sviluppatori e progetti, utilizzare .NET Framework 4.0 come destinazione di base.</span><span class="sxs-lookup"><span data-stu-id="7b586-151">If you want to reach the maximum number of developers and projects, use .NET Framework 4.0 as your baseline target.</span></span> <span data-ttu-id="7b586-152">Per utilizzare .NET Framework di destinazione, iniziare utilizzando il moniker (TFM) di Framework di destinazione corretto che corrisponde alla versione di .NET Framework che si desidera supportare.</span><span class="sxs-lookup"><span data-stu-id="7b586-152">To target .NET Framework, begin by using the correct Target Framework Moniker (TFM) that corresponds to the .NET Framework version you wish to support.</span></span>

| <span data-ttu-id="7b586-153">Versione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7b586-153">.NET Framework version</span></span> | <span data-ttu-id="7b586-154">Moniker framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="7b586-154">TFM</span></span>      |
| ---------------------- | -------- |
| <span data-ttu-id="7b586-155">.NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="7b586-155">.NET Framework 2.0</span></span>     | `net20`  |
| <span data-ttu-id="7b586-156">.NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="7b586-156">.NET Framework 3.0</span></span>     | `net30`  |
| <span data-ttu-id="7b586-157">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="7b586-157">.NET Framework 3.5</span></span>     | `net35`  |
| <span data-ttu-id="7b586-158">.NET Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="7b586-158">.NET Framework 4.0</span></span>     | `net40`  |
| <span data-ttu-id="7b586-159">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="7b586-159">.NET Framework 4.5</span></span>     | `net45`  |
| <span data-ttu-id="7b586-160">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="7b586-160">.NET Framework 4.5.1</span></span>   | `net451` |
| <span data-ttu-id="7b586-161">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="7b586-161">.NET Framework 4.5.2</span></span>   | `net452` |
| <span data-ttu-id="7b586-162">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="7b586-162">.NET Framework 4.6</span></span>     | `net46`  |
| <span data-ttu-id="7b586-163">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="7b586-163">.NET Framework 4.6.1</span></span>   | `net461` |
| <span data-ttu-id="7b586-164">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="7b586-164">.NET Framework 4.6.2</span></span>   | `net462` |
| <span data-ttu-id="7b586-165">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="7b586-165">.NET Framework 4.7</span></span>     | `net47`  |
| <span data-ttu-id="7b586-166">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="7b586-166">.NET Framework 4.8</span></span>     | `net48`  |

<span data-ttu-id="7b586-167">Quindi inserire il TFM nella sezione `TargetFramework` del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="7b586-167">You then insert this TFM into the `TargetFramework` section of your project file.</span></span> <span data-ttu-id="7b586-168">Ad esempio, ecco come scrivere una libreria destinata a .NET Framework 4.0:For example, here's how you would write a library that targets .NET Framework 4.0:</span><span class="sxs-lookup"><span data-stu-id="7b586-168">For example, here's how you would write a library that targets .NET Framework 4.0:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net40</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="7b586-169">L'attività è terminata.</span><span class="sxs-lookup"><span data-stu-id="7b586-169">And that's it!</span></span> <span data-ttu-id="7b586-170">Sebbene questo compilato solo per .NET Framework 4, è possibile utilizzare la libreria nelle versioni più recenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7b586-170">Although this compiled only for .NET Framework 4, you can use the library on newer versions of .NET Framework.</span></span>

## <a name="how-to-multitarget"></a><span data-ttu-id="7b586-171">Come multitarget</span><span class="sxs-lookup"><span data-stu-id="7b586-171">How to multitarget</span></span>

> [!NOTE]
> <span data-ttu-id="7b586-172">Le istruzioni seguenti presuppongono che nel computer sia installato .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7b586-172">The following instructions assume you have the .NET Framework installed on your machine.</span></span> <span data-ttu-id="7b586-173">Vedere la sezione [Prerequisiti](#prerequisites) per informazioni sulle dipendenze da installare e sull'area da cui scaricarle.</span><span class="sxs-lookup"><span data-stu-id="7b586-173">Refer to the [Prerequisites](#prerequisites) section to learn which dependencies you need to install and where to download them from.</span></span>

<span data-ttu-id="7b586-174">Quando il progetto supporta sia .NET Framework che .NET Core, può essere opportuno definire come destinazione le versioni precedenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7b586-174">You may need to target older versions of the .NET Framework when your project supports both the .NET Framework and .NET Core.</span></span> <span data-ttu-id="7b586-175">In questo scenario, per usare API e costrutti di linguaggio più recenti per le destinazioni più recenti, inserire direttive `#if` nel codice.</span><span class="sxs-lookup"><span data-stu-id="7b586-175">In this scenario, if you want to use newer APIs and language constructs for the newer targets, use `#if` directives in your code.</span></span> <span data-ttu-id="7b586-176">Può anche essere necessario aggiungere diversi pacchetti e dipendenze per ogni piattaforma di destinazione per includere le diverse API necessarie per ogni caso.</span><span class="sxs-lookup"><span data-stu-id="7b586-176">You also might need to add different packages and dependencies for each platform you're targeting to include the different APIs needed for each case.</span></span>

<span data-ttu-id="7b586-177">Si supponga ad esempio di avere una libreria che esegue operazioni di rete tramite HTTP.</span><span class="sxs-lookup"><span data-stu-id="7b586-177">For example, let's say you have a library that performs networking operations over HTTP.</span></span> <span data-ttu-id="7b586-178">Per .NET Standard e .NET Framework 4.5 o versioni successive, è possibile usare la classe `HttpClient` dello spazio dei nomi `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="7b586-178">For .NET Standard and the .NET Framework versions 4.5 or higher, you can use the `HttpClient` class from the `System.Net.Http` namespace.</span></span> <span data-ttu-id="7b586-179">Tuttavia, le versioni precedenti di .NET Framework non dispongono della classe `HttpClient` e per tali versioni è quindi possibile usare in alternativa la classe `WebClient` dello spazio dei nomi `System.Net`.</span><span class="sxs-lookup"><span data-stu-id="7b586-179">However, earlier versions of the .NET Framework don't have the `HttpClient` class, so you could use the `WebClient` class from the `System.Net` namespace for those instead.</span></span>

<span data-ttu-id="7b586-180">Il file di progetto può avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7b586-180">Your project file could look like this:</span></span>

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

<span data-ttu-id="7b586-181">Si noteranno tre modifiche principali:</span><span class="sxs-lookup"><span data-stu-id="7b586-181">You'll notice three major changes here:</span></span>

1. <span data-ttu-id="7b586-182">Il nodo `TargetFramework` è stato sostituito da `TargetFrameworks` e all'interno sono espressi tre TFM.</span><span class="sxs-lookup"><span data-stu-id="7b586-182">The `TargetFramework` node has been replaced by `TargetFrameworks`, and three TFMs are expressed inside.</span></span>
1. <span data-ttu-id="7b586-183">Un nodo `<ItemGroup>` per la destinazione `net40` chiama un riferimento di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7b586-183">There is an `<ItemGroup>` node for the `net40` target pulling in one .NET Framework reference.</span></span>
1. <span data-ttu-id="7b586-184">Un nodo `<ItemGroup>` per la destinazione `net45` chiama due riferimenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7b586-184">There is an `<ItemGroup>` node for the `net45` target pulling in two .NET Framework references.</span></span>

<span data-ttu-id="7b586-185">Il sistema di compilazione è in grado di riconoscere i seguenti simboli di preprocessore usati nelle direttive `#if`:</span><span class="sxs-lookup"><span data-stu-id="7b586-185">The build system is aware of the following preprocessor symbols used in `#if` directives:</span></span>

[!INCLUDE [Preprocessor symbols](../../../includes/preprocessor-symbols.md)]

<span data-ttu-id="7b586-186">Ecco un esempio che usa la compilazione condizionale basata sulla destinazione:</span><span class="sxs-lookup"><span data-stu-id="7b586-186">Here is an example making use of conditional compilation per-target:</span></span>

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
            string url = "https://www.dotnetfoundation.org/";

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
            string url = "https://www.dotnetfoundation.org/";

            // HttpClient is thread-safe, so no need to explicitly lock here
            var result = await _client.GetStringAsync(url);

            int dotNetCount = Regex.Matches(result, ".NET").Count;

            return $"dotnetfoundation.org mentions .NET {dotNetCount} times in its HTML!";
        }
#endif
    }
}
```

<span data-ttu-id="7b586-187">Se si compila il progetto con `dotnet build` si noteranno tre directory sotto la cartella `bin/`:</span><span class="sxs-lookup"><span data-stu-id="7b586-187">If you build this project with `dotnet build`, you'll notice three directories under the `bin/` folder:</span></span>

```
net40/
net45/
netstandard1.4/
```

<span data-ttu-id="7b586-188">Ogni directory contiene i file `.dll` per ciascuna destinazione.</span><span class="sxs-lookup"><span data-stu-id="7b586-188">Each of these contain the `.dll` files for each target.</span></span>

## <a name="how-to-test-libraries-on-net-core"></a><span data-ttu-id="7b586-189">Come testare le librerie in .NET Core</span><span class="sxs-lookup"><span data-stu-id="7b586-189">How to test libraries on .NET Core</span></span>

<span data-ttu-id="7b586-190">È importante essere in grado di eseguire test tra diverse piattaforme.</span><span class="sxs-lookup"><span data-stu-id="7b586-190">It's important to be able to test across platforms.</span></span> <span data-ttu-id="7b586-191">È possibile usare [xUnit](https://xunit.github.io/) o MSTest senza modifiche.</span><span class="sxs-lookup"><span data-stu-id="7b586-191">You can use either [xUnit](https://xunit.github.io/) or MSTest out of the box.</span></span> <span data-ttu-id="7b586-192">Entrambi sono adatti per gli unit test della libreria in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7b586-192">Both are perfectly suitable for unit testing your library on .NET Core.</span></span> <span data-ttu-id="7b586-193">La modalità di configurazione della soluzione con progetti di test dipende dalla [struttura della soluzione](#structuring-a-solution).</span><span class="sxs-lookup"><span data-stu-id="7b586-193">How you set up your solution with test projects will depend on the [structure of your solution](#structuring-a-solution).</span></span> <span data-ttu-id="7b586-194">Nell'esempio seguente si presuppone che le directory di test e di origine si trovino nella stessa directory di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="7b586-194">The following example assumes that the test and source directories live in the same top-level directory.</span></span>

> [!NOTE]
> <span data-ttu-id="7b586-195">In questo modo vengono utilizzati alcuni comandi [CLI di .NET Core.This](../tools/index.md) uses some .NET Core CLI commands.</span><span class="sxs-lookup"><span data-stu-id="7b586-195">This uses some [.NET Core CLI](../tools/index.md) commands.</span></span> <span data-ttu-id="7b586-196">Per altre informazioni, vedere [dotnet new](../tools/dotnet-new.md) e [dotnet sln](../tools/dotnet-sln.md).</span><span class="sxs-lookup"><span data-stu-id="7b586-196">See [dotnet new](../tools/dotnet-new.md) and [dotnet sln](../tools/dotnet-sln.md) for more information.</span></span>

1. <span data-ttu-id="7b586-197">Configurare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="7b586-197">Set up your solution.</span></span> <span data-ttu-id="7b586-198">È possibile farlo con i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b586-198">You can do so with the following commands:</span></span>

   ```dotnetcli
   mkdir SolutionWithSrcAndTest
   cd SolutionWithSrcAndTest
   dotnet new sln
   dotnet new classlib -o MyProject
   dotnet new xunit -o MyProject.Test
   dotnet sln add MyProject/MyProject.csproj
   dotnet sln add MyProject.Test/MyProject.Test.csproj
   ```

   <span data-ttu-id="7b586-199">I progetti vengono creati e collegati in una soluzione.</span><span class="sxs-lookup"><span data-stu-id="7b586-199">This will create projects and link them together in a solution.</span></span> <span data-ttu-id="7b586-200">La directory per `SolutionWithSrcAndTest` ha un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7b586-200">Your directory for `SolutionWithSrcAndTest` should look like this:</span></span>

   ```
   /SolutionWithSrcAndTest
   |__SolutionWithSrcAndTest.sln
   |__MyProject/
   |__MyProject.Test/
   ```

1. <span data-ttu-id="7b586-201">Passare alla directory del progetto di test e aggiungere un riferimento a `MyProject.Test` da `MyProject`.</span><span class="sxs-lookup"><span data-stu-id="7b586-201">Navigate to the test project's directory and add a reference to `MyProject.Test` from `MyProject`.</span></span>

   ```dotnetcli
   cd MyProject.Test
   dotnet add reference ../MyProject/MyProject.csproj
   ```

1. <span data-ttu-id="7b586-202">Ripristinare i pacchetti e compilare i progetti:</span><span class="sxs-lookup"><span data-stu-id="7b586-202">Restore packages and build projects:</span></span>

   ```dotnetcli
   dotnet restore
   dotnet build
   ```

   [!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

1. <span data-ttu-id="7b586-203">Verificare che xUnit sia in esecuzione con il comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="7b586-203">Verify that xUnit runs by executing the `dotnet test` command.</span></span> <span data-ttu-id="7b586-204">Se si sceglie di usare MSTest, va invece eseguita l'utilità di test delle console MSTest.</span><span class="sxs-lookup"><span data-stu-id="7b586-204">If you chose to use MSTest, then the MSTest console runner should run instead.</span></span>

<span data-ttu-id="7b586-205">L'attività è terminata.</span><span class="sxs-lookup"><span data-stu-id="7b586-205">And that's it!</span></span> <span data-ttu-id="7b586-206">È ora possibile testare la libreria su tutte le piattaforme utilizzando gli strumenti della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="7b586-206">You can now test your library across all platforms using command-line tools.</span></span> <span data-ttu-id="7b586-207">Una volta completata la configurazione, è possibile procedere con il testing della libreria in modo molto semplice:</span><span class="sxs-lookup"><span data-stu-id="7b586-207">To continue testing now that you have everything set up, testing your library is very simple:</span></span>

1. <span data-ttu-id="7b586-208">Eseguire le opportune modifiche nella libreria.</span><span class="sxs-lookup"><span data-stu-id="7b586-208">Make changes to your library.</span></span>
1. <span data-ttu-id="7b586-209">Eseguire i test dalla riga di comando, nella directory di test, usando il comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="7b586-209">Run tests from the command line, in your test directory, with `dotnet test` command.</span></span>

<span data-ttu-id="7b586-210">Il codice viene ricompilato automaticamente quando si richiama il comando `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="7b586-210">Your code will be automatically rebuilt when you invoke `dotnet test` command.</span></span>

## <a name="how-to-use-multiple-projects"></a><span data-ttu-id="7b586-211">Come usare più progetti</span><span class="sxs-lookup"><span data-stu-id="7b586-211">How to use multiple projects</span></span>

<span data-ttu-id="7b586-212">Per le librerie di maggiori dimensioni, è spesso necessario inserire funzionalità in progetti diversi.</span><span class="sxs-lookup"><span data-stu-id="7b586-212">A common need for larger libraries is to place functionality in different projects.</span></span>

<span data-ttu-id="7b586-213">Si supponga di voler compilare una libreria che potrebbe essere utilizzata in idiomatica C .</span><span class="sxs-lookup"><span data-stu-id="7b586-213">Imagine you want to build a library that could be consumed in idiomatic C# and F#.</span></span> <span data-ttu-id="7b586-214">Ciò significherebbe che i consumer della libreria lo utilizzano in modi che sono naturali per C .</span><span class="sxs-lookup"><span data-stu-id="7b586-214">That would mean that consumers of your library consume it in ways that are natural to C# or F#.</span></span> <span data-ttu-id="7b586-215">In C#, ad esempio, la libreria può essere utilizzata in un modo simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7b586-215">For example, in C# you might consume the library like this:</span></span>

```csharp
using AwesomeLibrary.CSharp;

public Task DoThings(Data data)
{
    var convertResult = await AwesomeLibrary.ConvertAsync(data);
    var result = AwesomeLibrary.Process(convertResult);
    // do something with result
}
```

<span data-ttu-id="7b586-216">In F#, invece, può assumere l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="7b586-216">In F#, it might look like this:</span></span>

```fsharp
open AwesomeLibrary.FSharp

let doWork data = async {
    let! result = AwesomeLibrary.AsyncConvert data // Uses an F# async function rather than C# async method
    // do something with result
}
```

<span data-ttu-id="7b586-217">Scenari di utilizzo come questo indicano che le API a cui si accede devono avere una struttura diversa per C# e F#.</span><span class="sxs-lookup"><span data-stu-id="7b586-217">Consumption scenarios like this mean that the APIs being accessed have to have a different structure for C# and F#.</span></span>  <span data-ttu-id="7b586-218">Un approccio comune per gestire questa situazione consiste nel definire l'intera logica di una libreria in un progetto di base, a cui eseguono chiamate i livelli di API definiti nei progetti C# e F#.</span><span class="sxs-lookup"><span data-stu-id="7b586-218">A common approach to accomplishing this is to factor all of the logic of a library into a core project, with C# and F# projects defining the API layers that call into that core project.</span></span>  <span data-ttu-id="7b586-219">Nella parte restante della sezione verranno usati i nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b586-219">The rest of the section will use the following names:</span></span>

* <span data-ttu-id="7b586-220">**AwesomeLibrary.Core** - Un progetto di base che contiene tutta la logica per la libreria</span><span class="sxs-lookup"><span data-stu-id="7b586-220">**AwesomeLibrary.Core** - A core project that contains all logic for the library</span></span>
* <span data-ttu-id="7b586-221">**AwesomeLibrary.CSharp**: un progetto con API pubbliche destinato all'utilizzo in C#</span><span class="sxs-lookup"><span data-stu-id="7b586-221">**AwesomeLibrary.CSharp** - A project with public APIs intended for consumption in C#</span></span>
* <span data-ttu-id="7b586-222">**AwesomeLibrary.FSharp**: un progetto con API pubbliche destinato all'utilizzo in F#</span><span class="sxs-lookup"><span data-stu-id="7b586-222">**AwesomeLibrary.FSharp** - A project with public APIs intended for consumption in F#</span></span>

<span data-ttu-id="7b586-223">Eseguire i seguenti comandi nel terminale in uso per ottenere la stessa struttura mostrata in questa Guida:</span><span class="sxs-lookup"><span data-stu-id="7b586-223">You can run the following commands in your terminal to produce the same structure as this guide:</span></span>

```dotnetcli
mkdir AwesomeLibrary && cd AwesomeLibrary
dotnet new sln
mkdir AwesomeLibrary.Core && cd AwesomeLibrary.Core && dotnet new classlib
cd ..
mkdir AwesomeLibrary.CSharp && cd AwesomeLibrary.CSharp && dotnet new classlib
cd ..
mkdir AwesomeLibrary.FSharp && cd AwesomeLibrary.FSharp && dotnet new classlib -lang "F#"
cd ..
dotnet sln add AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
dotnet sln add AwesomeLibrary.CSharp/AwesomeLibrary.CSharp.csproj
dotnet sln add AwesomeLibrary.FSharp/AwesomeLibrary.FSharp.fsproj
```

<span data-ttu-id="7b586-224">Verranno aggiunti i tre progetti precedenti e un file di soluzione che li collega tra loro.</span><span class="sxs-lookup"><span data-stu-id="7b586-224">This will add the three projects above and a solution file that links them together.</span></span> <span data-ttu-id="7b586-225">La creazione del file di soluzione e il collegamento di progetti consentiranno di ripristinare e compilare progetti da un livello superiore.</span><span class="sxs-lookup"><span data-stu-id="7b586-225">Creating the solution file and linking projects will allow you to restore and build projects from a top level.</span></span>

### <a name="project-to-project-referencing"></a><span data-ttu-id="7b586-226">Definizione di riferimenti da progetto a progetto</span><span class="sxs-lookup"><span data-stu-id="7b586-226">Project-to-project referencing</span></span>

<span data-ttu-id="7b586-227">Il modo migliore per creare un riferimento a un progetto è l'uso dell'interfaccia della riga di comando di .NET Core per aggiungere un riferimento al progetto.</span><span class="sxs-lookup"><span data-stu-id="7b586-227">The best way to reference a project is to use the .NET Core CLI to add a project reference.</span></span> <span data-ttu-id="7b586-228">Dalle directory di progetto **AwesomeLibrary.CSharp** e **AwesomeLibrary.FSharp** è possibile eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7b586-228">From the **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** project directories, you can run the following command:</span></span>

```dotnetcli
dotnet add reference ../AwesomeLibrary.Core/AwesomeLibrary.Core.csproj
```

<span data-ttu-id="7b586-229">I file di progetto per **AwesomeLibrary.CSharp** e **AwesomeLibrary.FSharp** includeranno ora un riferimento a **AwesomeLibrary.Core** come destinazione `ProjectReference`.</span><span class="sxs-lookup"><span data-stu-id="7b586-229">The project files for both **AwesomeLibrary.CSharp** and **AwesomeLibrary.FSharp** will now reference **AwesomeLibrary.Core** as a `ProjectReference` target.</span></span>  <span data-ttu-id="7b586-230">È possibile verificare la presenza del riferimento cercando quanto segue nei file di progetto:</span><span class="sxs-lookup"><span data-stu-id="7b586-230">You can verify this by inspecting the project files and seeing the following in them:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\AwesomeLibrary.Core\AwesomeLibrary.Core.csproj" />
</ItemGroup>
```

<span data-ttu-id="7b586-231">Se si preferisce non usare l'interfaccia della riga di comando .NET Core, è possibile aggiungere manualmente questa sezione a ogni file di progetto.</span><span class="sxs-lookup"><span data-stu-id="7b586-231">You can add this section to each project file manually if you prefer not to use the .NET Core CLI.</span></span>

### <a name="structuring-a-solution"></a><span data-ttu-id="7b586-232">Definizione della struttura di una soluzione</span><span class="sxs-lookup"><span data-stu-id="7b586-232">Structuring a solution</span></span>

<span data-ttu-id="7b586-233">Un altro aspetto importante delle soluzioni basate su più progetti è quello di stabilire una buona struttura complessiva dei progetti.</span><span class="sxs-lookup"><span data-stu-id="7b586-233">Another important aspect of multi-project solutions is establishing a good overall project structure.</span></span> <span data-ttu-id="7b586-234">È possibile organizzare il codice come desiderato. A condizione che si colleghi ogni progetto al file di soluzione mediante `dotnet sln add`, sarà possibile eseguire `dotnet restore` e `dotnet build` a livello della soluzione.</span><span class="sxs-lookup"><span data-stu-id="7b586-234">You can organize code however you like, and as long as you link each project to your solution file with `dotnet sln add`, you will be able to run `dotnet restore` and `dotnet build` at the solution level.</span></span>
