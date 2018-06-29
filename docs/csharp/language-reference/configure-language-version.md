---
title: Selezionare la versione del linguaggio C# - Guida a C#
description: Configurare il compilatore per eseguire la convalida della sintassi con una versione specifica del compilatore
ms.date: 05/24/2018
ms.openlocfilehash: 9b91e62168ced0f373e1a55def8b279dc64833d8
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207981"
---
# <a name="select-the-c-language-version"></a><span data-ttu-id="e8cf3-103">Selezionare la versione del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e8cf3-103">Select the C# language version</span></span>

<span data-ttu-id="e8cf3-104">Per impostazione predefinita viene usata la versione del compilatore C# corrispondente all'ultima versione principale del linguaggio rilasciata.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-104">The C# compiler defaults to the latest major version of the language that has been released.</span></span> <span data-ttu-id="e8cf3-105">È possibile scegliere di compilare tutti i progetti usando una nuova versione intermedia del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-105">You may choose to compile any project using a new point release of the language.</span></span> <span data-ttu-id="e8cf3-106">La scelta di una versione più recente del linguaggio consente al progetto di usare le nuove funzionalità del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-106">Choosing a newer version of the language enables your project to make use of the latest language features.</span></span> <span data-ttu-id="e8cf3-107">In altri scenari può essere necessario verificare che un progetto viene compilato senza errori quando si usa una versione precedente del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-107">In other scenarios, you may need to validate that a project compiles cleanly when using an older version of the language.</span></span>

<span data-ttu-id="e8cf3-108">Questa funzionalità separa l'installazione delle nuove versioni dell'SDK e degli strumenti nell'ambiente di sviluppo dalla decisione di incorporare nuove funzionalità del linguaggio in un progetto.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-108">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="e8cf3-109">È possibile installare l'SDK e gli strumenti più recenti nel computer di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-109">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="e8cf3-110">Ogni progetto può essere configurato per usare una versione specifica del linguaggio in base alla relativa build.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-110">Each project can be configured to use a specific version of the language for its build.</span></span>

<span data-ttu-id="e8cf3-111">La versione del linguaggio può essere impostata in modi diversi:</span><span class="sxs-lookup"><span data-stu-id="e8cf3-111">There are several ways to set the language version:</span></span>

- <span data-ttu-id="e8cf3-112">Usare un'[azione rapida di Visual Studio](#visual-studio-quick-action).</span><span class="sxs-lookup"><span data-stu-id="e8cf3-112">Rely on a [Visual Studio quick action](#visual-studio-quick-action).</span></span>
- <span data-ttu-id="e8cf3-113">Impostare la versione del linguaggio nell'[interfaccia utente di Visual Studio](#set-the-language-version-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="e8cf3-113">Set the language version in the [Visual Studio UI](#set-the-language-version-in-visual-studio).</span></span>
- <span data-ttu-id="e8cf3-114">Modificare manualmente il [file **.csproj**](#edit-the-csproj-file).</span><span class="sxs-lookup"><span data-stu-id="e8cf3-114">Manually edit your [**.csproj** file](#edit-the-csproj-file).</span></span>
- <span data-ttu-id="e8cf3-115">Impostare la versione del linguaggio [per più progetti in una sottodirectory](#configure-multiple-projects).</span><span class="sxs-lookup"><span data-stu-id="e8cf3-115">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="e8cf3-116">Configurare l'[opzione del compilatore `-langversion`](#set-the-langversion-compiler-option).</span><span class="sxs-lookup"><span data-stu-id="e8cf3-116">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option).</span></span>

## <a name="visual-studio-quick-action"></a><span data-ttu-id="e8cf3-117">Azione rapida di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e8cf3-117">Visual Studio quick action</span></span>

<span data-ttu-id="e8cf3-118">Visual Studio consente di determinare la versione del linguaggio necessaria.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-118">Visual Studio helps you determine the language version you need.</span></span> <span data-ttu-id="e8cf3-119">Se si usa una funzionalità del linguaggio non disponibile per la versione correntemente configurata, Visual Studio visualizza una correzione potenziale per aggiornare la versione del linguaggio per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-119">If you use a language feature that is not available for the currently configured version, Visual Studio shows a potential fix to update the language version for the project.</span></span>

## <a name="set-the-language-version-in-visual-studio"></a><span data-ttu-id="e8cf3-120">Impostare la versione del linguaggio in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e8cf3-120">Set the language version in Visual Studio</span></span>

<span data-ttu-id="e8cf3-121">È possibile impostare la versione in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-121">You can set the version in Visual Studio.</span></span> <span data-ttu-id="e8cf3-122">Fare clic con il pulsante destro del mouse sul nodo del progetto in Esplora soluzioni e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-122">Right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="e8cf3-123">Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-123">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="e8cf3-124">Nell'elenco a discesa selezionare la versione.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-124">In the dropdown, select the version.</span></span> <span data-ttu-id="e8cf3-125">L'immagine seguente mostra l'impostazione più recente:</span><span class="sxs-lookup"><span data-stu-id="e8cf3-125">The following image shows the "latest" setting:</span></span>

![Screenshot delle impostazioni di compilazione avanzate in cui è possibile specificare la versione del linguaggio](./media/configure-language-version/advanced-build-settings.png)

> [!NOTE]
> <span data-ttu-id="e8cf3-127">Se si usa l'IDE di Visual Studio per aggiornare i file csproj, l'IDE crea nodi separati per ogni configurazione della build.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-127">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="e8cf3-128">In genere si imposta lo stesso valore in tutte le configurazioni della build, ma è necessario impostarlo in modo esplicito per ogni configurazione della build o selezionare "Tutte le configurazioni" quando si modifica questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-128">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="e8cf3-129">Nel file csproj verrà visualizzato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e8cf3-129">You'll see the following in your csproj file:</span></span>
>
>```xml
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
>  <LangVersion>latest</LangVersion>
></PropertyGroup>
>
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
>  <LangVersion>latest</LangVersion>
> </PropertyGroup>
> ```
>

## <a name="edit-the-csproj-file"></a><span data-ttu-id="e8cf3-130">Modificare il file csproj</span><span class="sxs-lookup"><span data-stu-id="e8cf3-130">Edit the csproj file</span></span>

<span data-ttu-id="e8cf3-131">È possibile impostare la versione del linguaggio nel file con estensione **csproj**.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-131">You can set the language version in your **.csproj** file.</span></span> <span data-ttu-id="e8cf3-132">Aggiungere un elemento simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e8cf3-132">Add an element like the following:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="e8cf3-133">Il valore `latest` usa la versione secondaria più recente del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-133">The value `latest` uses the latest minor version of the C# language.</span></span> <span data-ttu-id="e8cf3-134">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="e8cf3-134">Valid values are:</span></span>

|<span data-ttu-id="e8cf3-135">Valore</span><span class="sxs-lookup"><span data-stu-id="e8cf3-135">Value</span></span>|<span data-ttu-id="e8cf3-136">Significato</span><span class="sxs-lookup"><span data-stu-id="e8cf3-136">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="e8cf3-137">default</span><span class="sxs-lookup"><span data-stu-id="e8cf3-137">default</span></span>|<span data-ttu-id="e8cf3-138">Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione principale più recente supportata.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-138">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="e8cf3-139">ISO-1</span><span class="sxs-lookup"><span data-stu-id="e8cf3-139">ISO-1</span></span>|<span data-ttu-id="e8cf3-140">Il compilatore accetta solo la sintassi inclusa nella specifica ISO/IEC 23270:2003 C# (1.0/1.2)</span><span class="sxs-lookup"><span data-stu-id="e8cf3-140">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
|<span data-ttu-id="e8cf3-141">ISO-2</span><span class="sxs-lookup"><span data-stu-id="e8cf3-141">ISO-2</span></span>|<span data-ttu-id="e8cf3-142">Il compilatore accetta solo la sintassi inclusa nella specifica ISO/IEC 23270:2006 C# (2.0)</span><span class="sxs-lookup"><span data-stu-id="e8cf3-142">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="e8cf3-143">3</span><span class="sxs-lookup"><span data-stu-id="e8cf3-143">3</span></span>|<span data-ttu-id="e8cf3-144">Il compilatore accetta solo la sintassi inclusa in C# 3.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-144">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="e8cf3-145">4</span><span class="sxs-lookup"><span data-stu-id="e8cf3-145">4</span></span>|<span data-ttu-id="e8cf3-146">Il compilatore accetta solo la sintassi inclusa in C# 4.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-146">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="e8cf3-147">5</span><span class="sxs-lookup"><span data-stu-id="e8cf3-147">5</span></span>|<span data-ttu-id="e8cf3-148">Il compilatore accetta solo la sintassi inclusa in C# 5.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-148">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="e8cf3-149">6</span><span class="sxs-lookup"><span data-stu-id="e8cf3-149">6</span></span>|<span data-ttu-id="e8cf3-150">Il compilatore accetta solo la sintassi inclusa in C# 6.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-150">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="e8cf3-151">7</span><span class="sxs-lookup"><span data-stu-id="e8cf3-151">7</span></span>|<span data-ttu-id="e8cf3-152">Il compilatore accetta solo la sintassi inclusa in C# 7.0 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-152">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="e8cf3-153">7.1</span><span class="sxs-lookup"><span data-stu-id="e8cf3-153">7.1</span></span>|<span data-ttu-id="e8cf3-154">Il compilatore accetta solo la sintassi inclusa in C# 7.1 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-154">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="e8cf3-155">7.2</span><span class="sxs-lookup"><span data-stu-id="e8cf3-155">7.2</span></span>|<span data-ttu-id="e8cf3-156">Il compilatore accetta solo la sintassi inclusa in C# 7.2 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-156">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="e8cf3-157">7.3</span><span class="sxs-lookup"><span data-stu-id="e8cf3-157">7.3</span></span>|<span data-ttu-id="e8cf3-158">Il compilatore accetta solo la sintassi inclusa in C# 7.3 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-158">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="e8cf3-159">latest</span><span class="sxs-lookup"><span data-stu-id="e8cf3-159">latest</span></span>|<span data-ttu-id="e8cf3-160">Il compilatore accetta tutte le sintassi di linguaggio valide.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-160">The compiler accepts all valid language syntax that it can support.</span></span>|

<span data-ttu-id="e8cf3-161">Le stringhe speciali `default` e `latest` si risolvono rispettivamente nelle versioni principale (C# 7.0) e secondaria (C#7.3) più recenti del linguaggio installate nel computer di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-161">The special strings `default` and `latest` resolve to the latest major (C# 7.0) and minor (C# 7.3) language versions installed on the build machine, respectively.</span></span>

## <a name="configure-multiple-projects"></a><span data-ttu-id="e8cf3-162">Configurare più progetti</span><span class="sxs-lookup"><span data-stu-id="e8cf3-162">Configure multiple projects</span></span>

<span data-ttu-id="e8cf3-163">È possibile creare un file **Directory.build.props** che contiene l'elemento `<LangVersion>` per configurare più directory.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-163">You can create a **Directory.build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="e8cf3-164">Questa operazione viene in genere eseguita nella directory della soluzione.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-164">You typically do that in your solution directory.</span></span> <span data-ttu-id="e8cf3-165">Aggiungere quanto segue a un file **Directory.build.props** nella directory della soluzione:</span><span class="sxs-lookup"><span data-stu-id="e8cf3-165">Add the following to a **Directory.build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>7.3</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="e8cf3-166">A questo punto, le compilazioni in tutte le sottodirectory della directory contenente il file useranno la sintassi di C# versione 7.3.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-166">Now, builds in every subdirectory of the directory containing that file will use C# version 7.3 syntax.</span></span> <span data-ttu-id="e8cf3-167">Per altre informazioni, vedere l'articolo [Personalizzare la compilazione](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="e8cf3-167">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="e8cf3-168">Impostare l'opzione del compilatore langversion</span><span class="sxs-lookup"><span data-stu-id="e8cf3-168">Set the langversion compiler option</span></span>

<span data-ttu-id="e8cf3-169">È possibile usare l'opzione della riga di comando `-langversion`.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-169">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="e8cf3-170">Per altre informazioni, vedere l'articolo relativo all'opzione del compilatore [-langversion](../language-reference/compiler-options/langversion-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e8cf3-170">For more information, see the article on the [-langversion](../language-reference/compiler-options/langversion-compiler-option.md) compiler option.</span></span> <span data-ttu-id="e8cf3-171">È possibile visualizzare un elenco dei valori validi digitando `csc -langversion:?`.</span><span class="sxs-lookup"><span data-stu-id="e8cf3-171">You can see a list of the valid values by typing  `csc -langversion:?`.</span></span>
