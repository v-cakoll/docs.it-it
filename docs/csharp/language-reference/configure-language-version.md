---
title: Controllo delle versioni del linguaggio C# - Guida a C#
description: Informazioni su come viene determinata la versione del linguaggio C# in base al progetto e sui diversi valori ai quali è possibile adattarlo manualmente.
ms.date: 07/10/2019
ms.openlocfilehash: 744cec0aac21f743648cccbdc93cf2977c32d644
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796538"
---
# <a name="c-language-versioning"></a><span data-ttu-id="71904-103">Controllo delle versioni del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="71904-103">C# language versioning</span></span>

<span data-ttu-id="71904-104">Il C# compilatore determina la versione di un linguaggio predefinito basata su uno o più framework di destinazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="71904-104">The C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="71904-105">Il linguaggio C# può infatti includere funzionalità che si basano su tipi o componenti di runtime che non sono disponibili in ogni implementazione .NET.</span><span class="sxs-lookup"><span data-stu-id="71904-105">This is because the C# language may have features that rely on types or runtime components that are not available in every .NET implementation.</span></span> <span data-ttu-id="71904-106">Ciò garantisce anche che, per qualsiasi framework di destinazione del progetto, si otterrà per impostazione predefinita la versione del linguaggio maggiormente compatibile.</span><span class="sxs-lookup"><span data-stu-id="71904-106">This also ensures that for whatever target your project is built against, you get the highest compatible language version by default.</span></span>

## <a name="defaults"></a><span data-ttu-id="71904-107">attività</span><span class="sxs-lookup"><span data-stu-id="71904-107">Defaults</span></span>

<span data-ttu-id="71904-108">Il compilatore determina un'impostazione predefinita in base a queste regole:</span><span class="sxs-lookup"><span data-stu-id="71904-108">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="71904-109">Framework di destinazione</span><span class="sxs-lookup"><span data-stu-id="71904-109">Target framework</span></span>|<span data-ttu-id="71904-110">version</span><span class="sxs-lookup"><span data-stu-id="71904-110">version</span></span>|<span data-ttu-id="71904-111">Impostazione predefinita della versione del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="71904-111">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="71904-112">.NET Core</span><span class="sxs-lookup"><span data-stu-id="71904-112">.NET Core</span></span>|<span data-ttu-id="71904-113">3.x</span><span class="sxs-lookup"><span data-stu-id="71904-113">3.x</span></span>|<span data-ttu-id="71904-114">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="71904-114">C# 8.0</span></span>|
|<span data-ttu-id="71904-115">.NET Core</span><span class="sxs-lookup"><span data-stu-id="71904-115">.NET Core</span></span>|<span data-ttu-id="71904-116">2.x</span><span class="sxs-lookup"><span data-stu-id="71904-116">2.x</span></span>|<span data-ttu-id="71904-117">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="71904-117">C# 7.3</span></span>|
|<span data-ttu-id="71904-118">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="71904-118">.NET Standard</span></span>|<span data-ttu-id="71904-119">tutti</span><span class="sxs-lookup"><span data-stu-id="71904-119">all</span></span>|<span data-ttu-id="71904-120">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="71904-120">C# 7.3</span></span>|
|<span data-ttu-id="71904-121">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="71904-121">.NET Framework</span></span>|<span data-ttu-id="71904-122">tutti</span><span class="sxs-lookup"><span data-stu-id="71904-122">all</span></span>|<span data-ttu-id="71904-123">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="71904-123">C# 7.3</span></span>|

## <a name="default-for-previews"></a><span data-ttu-id="71904-124">Impostazione predefinita per le anteprime</span><span class="sxs-lookup"><span data-stu-id="71904-124">Default for previews</span></span>

<span data-ttu-id="71904-125">Quando il progetto ha come destinazione un framework in anteprima con una versione del linguaggio in anteprima corrispondente, la versione del linguaggio usata è la versione del linguaggio in anteprima.</span><span class="sxs-lookup"><span data-stu-id="71904-125">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="71904-126">In questo modo, sarà possibile usare le funzionalità più recenti che sicuramente funzioneranno con l'anteprima in qualsiasi ambiente senza alcun effetto sui progetti che hanno come destinazione una versione rilasciata di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="71904-126">This ensures that you can use the latest features that are guaranteed to work with that preview in any environment without affecting your projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="71904-127">Sostituire un valore predefinito</span><span class="sxs-lookup"><span data-stu-id="71904-127">Override a default</span></span>

<span data-ttu-id="71904-128">Se è necessario specificare in modo esplicito la versione di C#, è possibile farlo in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="71904-128">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="71904-129">Modificare manualmente il [file di progetto](#edit-the-project-file).</span><span class="sxs-lookup"><span data-stu-id="71904-129">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="71904-130">Impostare la versione del linguaggio [per più progetti in una sottodirectory](#configure-multiple-projects).</span><span class="sxs-lookup"><span data-stu-id="71904-130">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="71904-131">Configurare l'[`-langversion`opzione del compilatore](compiler-options/langversion-compiler-option.md)</span><span class="sxs-lookup"><span data-stu-id="71904-131">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md)</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="71904-132">Modificare il file di progetto</span><span class="sxs-lookup"><span data-stu-id="71904-132">Edit the project file</span></span>

<span data-ttu-id="71904-133">È possibile impostare la versione del linguaggio nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="71904-133">You can set the language version in your project file.</span></span> <span data-ttu-id="71904-134">Ad esempio, se si vuole accedere esplicitamente alle funzionalità di anteprima, aggiungere un elemento simile a questo:</span><span class="sxs-lookup"><span data-stu-id="71904-134">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="71904-135">Il valore `preview` usa la versione del linguaggio C# in anteprima disponibile più recente supportata dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="71904-135">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="71904-136">Configurare più progetti</span><span class="sxs-lookup"><span data-stu-id="71904-136">Configure multiple projects</span></span>

<span data-ttu-id="71904-137">È possibile creare un file **Directory.build.props** che contiene l'elemento `<LangVersion>` per configurare più directory.</span><span class="sxs-lookup"><span data-stu-id="71904-137">You can create a **Directory.Build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="71904-138">Questa operazione viene in genere eseguita nella directory della soluzione.</span><span class="sxs-lookup"><span data-stu-id="71904-138">You typically do that in your solution directory.</span></span> <span data-ttu-id="71904-139">Aggiungere il codice seguente a un file **Directory.Build.props** nella directory della soluzione:</span><span class="sxs-lookup"><span data-stu-id="71904-139">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="71904-140">Ora le build presenti in ogni sottodirectory della directory contenente il file useranno la versione di C# in anteprima.</span><span class="sxs-lookup"><span data-stu-id="71904-140">Now, builds in every subdirectory of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="71904-141">Per altre informazioni, vedere l'articolo [Personalizzare la compilazione](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="71904-141">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="71904-142">Informazioni di riferimento sulle versioni del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="71904-142">C# language version reference</span></span>

<span data-ttu-id="71904-143">La tabella seguente illustra tutte le versioni del linguaggio C# correnti.</span><span class="sxs-lookup"><span data-stu-id="71904-143">The following table shows all current C# language versions.</span></span> <span data-ttu-id="71904-144">Il compilatore in uso potrebbe non riconoscere necessariamente ogni valore, se è antecedente.</span><span class="sxs-lookup"><span data-stu-id="71904-144">Your compiler may not necessarily understand every value if it is older.</span></span> <span data-ttu-id="71904-145">Se si installa .NET Core 3.0, si avrà accesso a tutti gli elementi elencati.</span><span class="sxs-lookup"><span data-stu-id="71904-145">If you install .NET Core 3.0, then you will have access to everything listed.</span></span>

|<span data-ttu-id="71904-146">Value</span><span class="sxs-lookup"><span data-stu-id="71904-146">Value</span></span>|<span data-ttu-id="71904-147">Significato</span><span class="sxs-lookup"><span data-stu-id="71904-147">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="71904-148">preview</span><span class="sxs-lookup"><span data-stu-id="71904-148">preview</span></span>|<span data-ttu-id="71904-149">Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione di anteprima più recente.</span><span class="sxs-lookup"><span data-stu-id="71904-149">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="71904-150">latest</span><span class="sxs-lookup"><span data-stu-id="71904-150">latest</span></span>|<span data-ttu-id="71904-151">Il compilatore accetta la sintassi dalla versione rilasciata più recente del compilatore (inclusa la versione secondaria).</span><span class="sxs-lookup"><span data-stu-id="71904-151">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="71904-152">latestMajor</span><span class="sxs-lookup"><span data-stu-id="71904-152">latestMajor</span></span>|<span data-ttu-id="71904-153">Il compilatore accetta la sintassi dalla versione principale più recente rilasciata del compilatore.</span><span class="sxs-lookup"><span data-stu-id="71904-153">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="71904-154">8.0</span><span class="sxs-lookup"><span data-stu-id="71904-154">8.0</span></span>|<span data-ttu-id="71904-155">Il compilatore accetta solo la sintassi inclusa in C# 8.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="71904-155">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="71904-156">7.3</span><span class="sxs-lookup"><span data-stu-id="71904-156">7.3</span></span>|<span data-ttu-id="71904-157">Il compilatore accetta solo la sintassi inclusa in C# 7.3 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="71904-157">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="71904-158">7.2</span><span class="sxs-lookup"><span data-stu-id="71904-158">7.2</span></span>|<span data-ttu-id="71904-159">Il compilatore accetta solo la sintassi inclusa in C# 7.2 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="71904-159">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="71904-160">7.1</span><span class="sxs-lookup"><span data-stu-id="71904-160">7.1</span></span>|<span data-ttu-id="71904-161">Il compilatore accetta solo la sintassi inclusa in C# 7.1 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="71904-161">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="71904-162">7</span><span class="sxs-lookup"><span data-stu-id="71904-162">7</span></span>|<span data-ttu-id="71904-163">Il compilatore accetta solo la sintassi inclusa in C# 7.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="71904-163">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="71904-164">6</span><span class="sxs-lookup"><span data-stu-id="71904-164">6</span></span>|<span data-ttu-id="71904-165">Il compilatore accetta solo la sintassi inclusa in C# 6.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="71904-165">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="71904-166">5</span><span class="sxs-lookup"><span data-stu-id="71904-166">5</span></span>|<span data-ttu-id="71904-167">Il compilatore accetta solo la sintassi inclusa in C# 5.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="71904-167">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="71904-168">4</span><span class="sxs-lookup"><span data-stu-id="71904-168">4</span></span>|<span data-ttu-id="71904-169">Il compilatore accetta solo la sintassi inclusa in C# 4.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="71904-169">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="71904-170">3</span><span class="sxs-lookup"><span data-stu-id="71904-170">3</span></span>|<span data-ttu-id="71904-171">Il compilatore accetta solo la sintassi inclusa in C# 3.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="71904-171">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="71904-172">ISO-2</span><span class="sxs-lookup"><span data-stu-id="71904-172">ISO-2</span></span>|<span data-ttu-id="71904-173">Il compilatore accetta solo la sintassi inclusa nella specifica ISO/IEC 23270:2006 C# (2.0)</span><span class="sxs-lookup"><span data-stu-id="71904-173">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="71904-174">ISO-1</span><span class="sxs-lookup"><span data-stu-id="71904-174">ISO-1</span></span>|<span data-ttu-id="71904-175">Il compilatore accetta solo la sintassi inclusa nella specifica ISO/IEC 23270:2003 C# (1.0/1.2)</span><span class="sxs-lookup"><span data-stu-id="71904-175">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
