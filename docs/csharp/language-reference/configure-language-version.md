---
title: Controllo delle versioni del linguaggio C# - Guida a C#
description: Informazioni su come viene determinata la versione del linguaggio C# in base al progetto e sui diversi valori ai quali è possibile adattarlo manualmente.
ms.date: 07/10/2019
ms.openlocfilehash: fae36f5305e23fbfa1c55c5881e37391670f93ab
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040344"
---
# <a name="c-language-versioning"></a><span data-ttu-id="b2dfe-103">Controllo delle versioni del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b2dfe-103">C# language versioning</span></span>

<span data-ttu-id="b2dfe-104">Il compilatore C# più recente determina la versione di un linguaggio predefinito in base ai framework di destinazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-104">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="b2dfe-105">Il linguaggio C# può infatti includere funzionalità che si basano su tipi o componenti di runtime che non sono disponibili in ogni implementazione .NET.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-105">This is because the C# language may have features that rely on types or runtime components that are not available in every .NET implementation.</span></span> <span data-ttu-id="b2dfe-106">Ciò garantisce anche che, per qualsiasi framework di destinazione del progetto, si otterrà per impostazione predefinita la versione del linguaggio maggiormente compatibile.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-106">This also ensures that for whatever target your project is built against, you get the highest compatible language version by default.</span></span>

<span data-ttu-id="b2dfe-107">Le regole in questo articolo si applicano al compilatore fornito con Visual Studio 2019 o .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-107">The rules in this article apply to the compiler delivered with Visual Studio 2019, or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="b2dfe-108">I compilatori C# che fanno parte dell'installazione di Visual Studio 2017 o di versioni precedenti di .NET Core SDK usano C# 7.0 come destinazione per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-108">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span> 

## <a name="defaults"></a><span data-ttu-id="b2dfe-109">attività</span><span class="sxs-lookup"><span data-stu-id="b2dfe-109">Defaults</span></span>

<span data-ttu-id="b2dfe-110">Il compilatore determina un'impostazione predefinita in base a queste regole:</span><span class="sxs-lookup"><span data-stu-id="b2dfe-110">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="b2dfe-111">Framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="b2dfe-111">Target framework</span></span>|<span data-ttu-id="b2dfe-112">version</span><span class="sxs-lookup"><span data-stu-id="b2dfe-112">version</span></span>|<span data-ttu-id="b2dfe-113">Impostazione predefinita della versione del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b2dfe-113">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="b2dfe-114">.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2dfe-114">.NET Core</span></span>|<span data-ttu-id="b2dfe-115">3.x</span><span class="sxs-lookup"><span data-stu-id="b2dfe-115">3.x</span></span>|<span data-ttu-id="b2dfe-116">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="b2dfe-116">C# 8.0</span></span>|
|<span data-ttu-id="b2dfe-117">.NET Core</span><span class="sxs-lookup"><span data-stu-id="b2dfe-117">.NET Core</span></span>|<span data-ttu-id="b2dfe-118">2.x</span><span class="sxs-lookup"><span data-stu-id="b2dfe-118">2.x</span></span>|<span data-ttu-id="b2dfe-119">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="b2dfe-119">C# 7.3</span></span>|
|<span data-ttu-id="b2dfe-120">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="b2dfe-120">.NET Standard</span></span>|<span data-ttu-id="b2dfe-121">tutti</span><span class="sxs-lookup"><span data-stu-id="b2dfe-121">all</span></span>|<span data-ttu-id="b2dfe-122">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="b2dfe-122">C# 7.3</span></span>|
|<span data-ttu-id="b2dfe-123">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="b2dfe-123">.NET Framework</span></span>|<span data-ttu-id="b2dfe-124">tutti</span><span class="sxs-lookup"><span data-stu-id="b2dfe-124">all</span></span>|<span data-ttu-id="b2dfe-125">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="b2dfe-125">C# 7.3</span></span>|

## <a name="default-for-previews"></a><span data-ttu-id="b2dfe-126">Impostazione predefinita per le anteprime</span><span class="sxs-lookup"><span data-stu-id="b2dfe-126">Default for previews</span></span>

<span data-ttu-id="b2dfe-127">Quando il progetto ha come destinazione un framework in anteprima con una versione del linguaggio in anteprima corrispondente, la versione del linguaggio usata è la versione del linguaggio in anteprima.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-127">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="b2dfe-128">In questo modo, sarà possibile usare le funzionalità più recenti che sicuramente funzioneranno con l'anteprima in qualsiasi ambiente senza alcun effetto sui progetti che hanno come destinazione una versione rilasciata di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-128">This ensures that you can use the latest features that are guaranteed to work with that preview in any environment without affecting your projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="b2dfe-129">Sostituire un valore predefinito</span><span class="sxs-lookup"><span data-stu-id="b2dfe-129">Override a default</span></span>

<span data-ttu-id="b2dfe-130">Se è necessario specificare in modo esplicito la versione di C#, è possibile farlo in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="b2dfe-130">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="b2dfe-131">Modificare manualmente il [file di progetto](#edit-the-project-file).</span><span class="sxs-lookup"><span data-stu-id="b2dfe-131">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="b2dfe-132">Impostare la versione del linguaggio [per più progetti in una sottodirectory](#configure-multiple-projects).</span><span class="sxs-lookup"><span data-stu-id="b2dfe-132">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="b2dfe-133">Configurare l'[`-langversion`opzione del compilatore](compiler-options/langversion-compiler-option.md)</span><span class="sxs-lookup"><span data-stu-id="b2dfe-133">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md)</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="b2dfe-134">Modificare il file di progetto</span><span class="sxs-lookup"><span data-stu-id="b2dfe-134">Edit the project file</span></span>

<span data-ttu-id="b2dfe-135">È possibile impostare la versione del linguaggio nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-135">You can set the language version in your project file.</span></span> <span data-ttu-id="b2dfe-136">Ad esempio, se si vuole accedere esplicitamente alle funzionalità di anteprima, aggiungere un elemento simile a questo:</span><span class="sxs-lookup"><span data-stu-id="b2dfe-136">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="b2dfe-137">Il valore `preview` usa la versione del linguaggio C# in anteprima disponibile più recente supportata dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-137">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="b2dfe-138">Configurare più progetti</span><span class="sxs-lookup"><span data-stu-id="b2dfe-138">Configure multiple projects</span></span>

<span data-ttu-id="b2dfe-139">È possibile creare un file **Directory.build.props** che contiene l'elemento `<LangVersion>` per configurare più directory.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-139">You can create a **Directory.Build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="b2dfe-140">Questa operazione viene in genere eseguita nella directory della soluzione.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-140">You typically do that in your solution directory.</span></span> <span data-ttu-id="b2dfe-141">Aggiungere il codice seguente a un file **Directory.Build.props** nella directory della soluzione:</span><span class="sxs-lookup"><span data-stu-id="b2dfe-141">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="b2dfe-142">Ora le build presenti in ogni sottodirectory della directory contenente il file useranno la versione di C# in anteprima.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-142">Now, builds in every subdirectory of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="b2dfe-143">Per altre informazioni, vedere l'articolo [Personalizzare la compilazione](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="b2dfe-143">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="b2dfe-144">Informazioni di riferimento sulle versioni del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b2dfe-144">C# language version reference</span></span>

<span data-ttu-id="b2dfe-145">La tabella seguente illustra tutte le versioni del linguaggio C# correnti.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-145">The following table shows all current C# language versions.</span></span> <span data-ttu-id="b2dfe-146">Il compilatore in uso potrebbe non riconoscere necessariamente ogni valore, se è antecedente.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-146">Your compiler may not necessarily understand every value if it is older.</span></span> <span data-ttu-id="b2dfe-147">Se si installa .NET Core 3.0, si avrà accesso a tutti gli elementi elencati.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-147">If you install .NET Core 3.0, then you will have access to everything listed.</span></span>

|<span data-ttu-id="b2dfe-148">Value</span><span class="sxs-lookup"><span data-stu-id="b2dfe-148">Value</span></span>|<span data-ttu-id="b2dfe-149">Significato</span><span class="sxs-lookup"><span data-stu-id="b2dfe-149">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="b2dfe-150">preview</span><span class="sxs-lookup"><span data-stu-id="b2dfe-150">preview</span></span>|<span data-ttu-id="b2dfe-151">Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione di anteprima più recente.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-151">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="b2dfe-152">latest</span><span class="sxs-lookup"><span data-stu-id="b2dfe-152">latest</span></span>|<span data-ttu-id="b2dfe-153">Il compilatore accetta la sintassi dalla versione rilasciata più recente del compilatore (inclusa la versione secondaria).</span><span class="sxs-lookup"><span data-stu-id="b2dfe-153">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="b2dfe-154">latestMajor</span><span class="sxs-lookup"><span data-stu-id="b2dfe-154">latestMajor</span></span>|<span data-ttu-id="b2dfe-155">Il compilatore accetta la sintassi dalla versione principale più recente rilasciata del compilatore.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-155">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="b2dfe-156">8.0</span><span class="sxs-lookup"><span data-stu-id="b2dfe-156">8.0</span></span>|<span data-ttu-id="b2dfe-157">Il compilatore accetta solo la sintassi inclusa in C# 8.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-157">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="b2dfe-158">7.3</span><span class="sxs-lookup"><span data-stu-id="b2dfe-158">7.3</span></span>|<span data-ttu-id="b2dfe-159">Il compilatore accetta solo la sintassi inclusa in C# 7.3 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-159">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="b2dfe-160">7.2</span><span class="sxs-lookup"><span data-stu-id="b2dfe-160">7.2</span></span>|<span data-ttu-id="b2dfe-161">Il compilatore accetta solo la sintassi inclusa in C# 7.2 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-161">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="b2dfe-162">7.1</span><span class="sxs-lookup"><span data-stu-id="b2dfe-162">7.1</span></span>|<span data-ttu-id="b2dfe-163">Il compilatore accetta solo la sintassi inclusa in C# 7.1 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-163">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="b2dfe-164">7</span><span class="sxs-lookup"><span data-stu-id="b2dfe-164">7</span></span>|<span data-ttu-id="b2dfe-165">Il compilatore accetta solo la sintassi inclusa in C# 7.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-165">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="b2dfe-166">6</span><span class="sxs-lookup"><span data-stu-id="b2dfe-166">6</span></span>|<span data-ttu-id="b2dfe-167">Il compilatore accetta solo la sintassi inclusa in C# 6.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-167">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="b2dfe-168">5</span><span class="sxs-lookup"><span data-stu-id="b2dfe-168">5</span></span>|<span data-ttu-id="b2dfe-169">Il compilatore accetta solo la sintassi inclusa in C# 5.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-169">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="b2dfe-170">4</span><span class="sxs-lookup"><span data-stu-id="b2dfe-170">4</span></span>|<span data-ttu-id="b2dfe-171">Il compilatore accetta solo la sintassi inclusa in C# 4.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-171">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="b2dfe-172">3</span><span class="sxs-lookup"><span data-stu-id="b2dfe-172">3</span></span>|<span data-ttu-id="b2dfe-173">Il compilatore accetta solo la sintassi inclusa in C# 3.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="b2dfe-173">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="b2dfe-174">ISO-2</span><span class="sxs-lookup"><span data-stu-id="b2dfe-174">ISO-2</span></span>|<span data-ttu-id="b2dfe-175">Il compilatore accetta solo la sintassi inclusa nella specifica ISO/IEC 23270:2006 C# (2.0)</span><span class="sxs-lookup"><span data-stu-id="b2dfe-175">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="b2dfe-176">ISO-1</span><span class="sxs-lookup"><span data-stu-id="b2dfe-176">ISO-1</span></span>|<span data-ttu-id="b2dfe-177">Il compilatore accetta solo la sintassi inclusa nella specifica ISO/IEC 23270:2003 C# (1.0/1.2)</span><span class="sxs-lookup"><span data-stu-id="b2dfe-177">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
