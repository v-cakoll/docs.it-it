---
title: Controllo delle versioni del linguaggio C# - Guida a C#
description: Informazioni su come la versione del linguaggio C# viene determinata in base al progetto e ai motivi alla base di tale scelta. Informazioni su come eseguire manualmente l'override del valore predefinito.
ms.date: 05/20/2020
ms.openlocfilehash: bbe5b12e378cf47b7c9b2c8576088e949e526a9a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803012"
---
# <a name="c-language-versioning"></a><span data-ttu-id="cc74f-104">Controllo delle versioni del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="cc74f-104">C# language versioning</span></span>

<span data-ttu-id="cc74f-105">Il compilatore C# più recente determina la versione di un linguaggio predefinito in base ai framework di destinazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cc74f-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="cc74f-106">Visual Studio non fornisce un'interfaccia utente per modificare il valore, ma è possibile modificarlo modificando il file *csproj* .</span><span class="sxs-lookup"><span data-stu-id="cc74f-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="cc74f-107">La scelta del valore predefinito consente di usare la versione più recente del linguaggio compatibile con il Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cc74f-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="cc74f-108">È possibile trarre vantaggio dall'accesso alle funzionalità più recenti del linguaggio compatibili con la destinazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cc74f-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="cc74f-109">Questa scelta predefinita garantisce anche di non usare un linguaggio che richiede tipi o comportamenti di runtime non disponibili nel Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cc74f-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="cc74f-110">La scelta di una versione della lingua più recente di quella predefinita può causare difficoltà nella diagnosi degli errori di runtime e della fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="cc74f-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="cc74f-111">Le regole in questo articolo si applicano al compilatore fornito con Visual Studio 2019 o .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="cc74f-111">The rules in this article apply to the compiler delivered with Visual Studio 2019 or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="cc74f-112">I compilatori C# che fanno parte dell'installazione di Visual Studio 2017 o di versioni precedenti di .NET Core SDK usano C# 7.0 come destinazione per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="cc74f-112">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span>

<span data-ttu-id="cc74f-113">C# 8,0 (e versioni successive) è supportato solo in .NET Core 3. x e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="cc74f-113">C# 8.0 (and higher) is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="cc74f-114">Molte delle funzionalità più recenti richiedono la libreria e le funzionalità di runtime introdotte in .NET Core 3. x:</span><span class="sxs-lookup"><span data-stu-id="cc74f-114">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="cc74f-115">L' [implementazione dell'interfaccia predefinita](../whats-new/csharp-8.md#default-interface-methods) richiede nuove funzionalità in CLR di .net core 3,0.</span><span class="sxs-lookup"><span data-stu-id="cc74f-115">[Default interface implementation](../whats-new/csharp-8.md#default-interface-methods) requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="cc74f-116">I [flussi asincroni](../whats-new/csharp-8.md#asynchronous-streams) richiedono i nuovi tipi <xref:System.IAsyncDisposable?displayProperty=nameWithType> , <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> e <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="cc74f-116">[Async streams](../whats-new/csharp-8.md#asynchronous-streams) require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="cc74f-117">Per gli [indici e gli intervalli](../whats-new/csharp-8.md#indices-and-ranges) sono necessari i nuovi tipi <xref:System.Index?displayProperty=nameWithType> e <xref:System.Range?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="cc74f-117">[Indices and ranges](../whats-new/csharp-8.md#indices-and-ranges) require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="cc74f-118">I [tipi di riferimento Nullable](../whats-new/csharp-8.md#nullable-reference-types) fanno uso di diversi [attributi](attributes/nullable-analysis.md) per fornire avvisi migliori.</span><span class="sxs-lookup"><span data-stu-id="cc74f-118">[Nullable reference types](../whats-new/csharp-8.md#nullable-reference-types) make use of several [attributes](attributes/nullable-analysis.md) to provide better warnings.</span></span> <span data-ttu-id="cc74f-119">Questi attributi sono stati aggiunti in .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="cc74f-119">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="cc74f-120">Altri Framework di destinazione non sono stati annotati con nessuno di questi attributi.</span><span class="sxs-lookup"><span data-stu-id="cc74f-120">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="cc74f-121">Questo significa che gli avvisi Nullable potrebbero non riflettere accuratamente i potenziali problemi.</span><span class="sxs-lookup"><span data-stu-id="cc74f-121">That means nullable warnings may not accurately reflect potential issues.</span></span>

## <a name="defaults"></a><span data-ttu-id="cc74f-122">Valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="cc74f-122">Defaults</span></span>

<span data-ttu-id="cc74f-123">Il compilatore determina un'impostazione predefinita in base a queste regole:</span><span class="sxs-lookup"><span data-stu-id="cc74f-123">The compiler determines a default based on these rules:</span></span>

| <span data-ttu-id="cc74f-124">Framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="cc74f-124">Target framework</span></span> | <span data-ttu-id="cc74f-125">version</span><span class="sxs-lookup"><span data-stu-id="cc74f-125">version</span></span> | <span data-ttu-id="cc74f-126">Impostazione predefinita della versione del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="cc74f-126">C# language version default</span></span> |
|------------------|---------|-----------------------------|
| <span data-ttu-id="cc74f-127">.NET Core</span><span class="sxs-lookup"><span data-stu-id="cc74f-127">.NET Core</span></span>        | <span data-ttu-id="cc74f-128">3.x</span><span class="sxs-lookup"><span data-stu-id="cc74f-128">3.x</span></span>     | <span data-ttu-id="cc74f-129">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="cc74f-129">C# 8.0</span></span>                      |
| <span data-ttu-id="cc74f-130">.NET Core</span><span class="sxs-lookup"><span data-stu-id="cc74f-130">.NET Core</span></span>        | <span data-ttu-id="cc74f-131">2.x</span><span class="sxs-lookup"><span data-stu-id="cc74f-131">2.x</span></span>     | <span data-ttu-id="cc74f-132">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="cc74f-132">C# 7.3</span></span>                      |
| <span data-ttu-id="cc74f-133">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="cc74f-133">.NET Standard</span></span>    | <span data-ttu-id="cc74f-134">2.1</span><span class="sxs-lookup"><span data-stu-id="cc74f-134">2.1</span></span>     | <span data-ttu-id="cc74f-135">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="cc74f-135">C# 8.0</span></span>                      |
| <span data-ttu-id="cc74f-136">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="cc74f-136">.NET Standard</span></span>    | <span data-ttu-id="cc74f-137">2.0</span><span class="sxs-lookup"><span data-stu-id="cc74f-137">2.0</span></span>     | <span data-ttu-id="cc74f-138">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="cc74f-138">C# 7.3</span></span>                      |
| <span data-ttu-id="cc74f-139">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="cc74f-139">.NET Standard</span></span>    | <span data-ttu-id="cc74f-140">1.x</span><span class="sxs-lookup"><span data-stu-id="cc74f-140">1.x</span></span>     | <span data-ttu-id="cc74f-141">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="cc74f-141">C# 7.3</span></span>                      |
| <span data-ttu-id="cc74f-142">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="cc74f-142">.NET Framework</span></span>   | <span data-ttu-id="cc74f-143">all</span><span class="sxs-lookup"><span data-stu-id="cc74f-143">all</span></span>     | <span data-ttu-id="cc74f-144">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="cc74f-144">C# 7.3</span></span>                      |

<span data-ttu-id="cc74f-145">Quando il progetto ha come destinazione un framework in anteprima con una versione del linguaggio in anteprima corrispondente, la versione del linguaggio usata è la versione del linguaggio in anteprima.</span><span class="sxs-lookup"><span data-stu-id="cc74f-145">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="cc74f-146">Si usano le funzionalità più recenti con questa anteprima in qualsiasi ambiente, senza influire sui progetti destinati a una versione di .NET Core rilasciata.</span><span class="sxs-lookup"><span data-stu-id="cc74f-146">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="cc74f-147">Sostituire un valore predefinito</span><span class="sxs-lookup"><span data-stu-id="cc74f-147">Override a default</span></span>

<span data-ttu-id="cc74f-148">Se è necessario specificare in modo esplicito la versione di C#, è possibile farlo in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="cc74f-148">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="cc74f-149">Modificare manualmente il [file di progetto](#edit-the-project-file).</span><span class="sxs-lookup"><span data-stu-id="cc74f-149">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="cc74f-150">Impostare la versione del linguaggio [per più progetti in una sottodirectory](#configure-multiple-projects).</span><span class="sxs-lookup"><span data-stu-id="cc74f-150">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="cc74f-151">Configurare l' [ `-langversion` opzione del compilatore](compiler-options/langversion-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="cc74f-151">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="cc74f-152">Modificare il file di progetto</span><span class="sxs-lookup"><span data-stu-id="cc74f-152">Edit the project file</span></span>

<span data-ttu-id="cc74f-153">È possibile impostare la versione del linguaggio nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="cc74f-153">You can set the language version in your project file.</span></span> <span data-ttu-id="cc74f-154">Ad esempio, se si vuole accedere esplicitamente alle funzionalità di anteprima, aggiungere un elemento simile a questo:</span><span class="sxs-lookup"><span data-stu-id="cc74f-154">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="cc74f-155">Il valore `preview` usa la versione del linguaggio C# in anteprima disponibile più recente supportata dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="cc74f-155">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="cc74f-156">Configurare più progetti</span><span class="sxs-lookup"><span data-stu-id="cc74f-156">Configure multiple projects</span></span>

<span data-ttu-id="cc74f-157">Per configurare più progetti, è possibile creare un file **Directory. Build. props** che contiene l' `<LangVersion>` elemento.</span><span class="sxs-lookup"><span data-stu-id="cc74f-157">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="cc74f-158">Questa operazione viene in genere eseguita nella directory della soluzione.</span><span class="sxs-lookup"><span data-stu-id="cc74f-158">You typically do that in your solution directory.</span></span> <span data-ttu-id="cc74f-159">Aggiungere il codice seguente a un file **Directory. Build. props** nella directory della soluzione:</span><span class="sxs-lookup"><span data-stu-id="cc74f-159">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="cc74f-160">Compilazioni in tutte le sottodirectory della directory che contiene il file utilizzerà la versione di anteprima C#.</span><span class="sxs-lookup"><span data-stu-id="cc74f-160">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="cc74f-161">Per altre informazioni, vedere l'articolo [Personalizzare la compilazione](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="cc74f-161">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="cc74f-162">Informazioni di riferimento sulle versioni del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="cc74f-162">C# language version reference</span></span>

<span data-ttu-id="cc74f-163">La tabella seguente illustra tutte le versioni del linguaggio C# correnti.</span><span class="sxs-lookup"><span data-stu-id="cc74f-163">The following table shows all current C# language versions.</span></span> <span data-ttu-id="cc74f-164">Il compilatore potrebbe non comprendere necessariamente ogni valore se è meno recente.</span><span class="sxs-lookup"><span data-stu-id="cc74f-164">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="cc74f-165">Se si installa .NET Core 3,0 o versione successiva, è possibile accedere a tutti gli elementi elencati.</span><span class="sxs-lookup"><span data-stu-id="cc74f-165">If you install .NET Core 3.0 or later, then you have access to everything listed.</span></span>

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> <span data-ttu-id="cc74f-166">Aprire il [prompt dei comandi per gli sviluppatori per Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md)ed eseguire il comando seguente per visualizzare l'elenco delle versioni della lingua disponibili nel computer.</span><span class="sxs-lookup"><span data-stu-id="cc74f-166">Open the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), and run the following command to see the listing of language versions available on your machine.</span></span>
>
> ```CMD
> csc -langversion:?
> ```
>
> <span data-ttu-id="cc74f-167">Se si sta interrogando l'opzione di compilazione [-langversion](compiler-options/langversion-compiler-option.md) , verrà stampato un valore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="cc74f-167">Questioning the [-langversion](compiler-options/langversion-compiler-option.md) compile option like this, will print something similar to the following:</span></span>
>
> ```CMD
> Supported language versions:
> default
> 1
> 2
> 3
> 4
> 5
> 6
> 7.0
> 7.1
> 7.2
> 7.3
> 8.0 (default)
> latestmajor
> preview
> latest
> ```
