---
title: Selezionare la versione del linguaggio Visual Basic
description: Configurare il compilatore per eseguire la convalida della sintassi usando una specifica versione del compilatore.
ms.date: 05/24/2018
ms.openlocfilehash: 3b6d8055dbf64f2a5c38f46b6d66794fc48a1cea
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415104"
---
# <a name="select-the-visual-basic-language-version"></a><span data-ttu-id="9f73f-103">Selezionare la versione del linguaggio Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f73f-103">Select the Visual Basic language version</span></span>

<span data-ttu-id="9f73f-104">Il compilatore Visual Basic per impostazione predefinita la versione principale più recente del linguaggio che è stata rilasciata.</span><span class="sxs-lookup"><span data-stu-id="9f73f-104">The Visual Basic compiler defaults to the latest major version of the language that has been released.</span></span> <span data-ttu-id="9f73f-105">È possibile scegliere di compilare tutti i progetti usando una nuova versione intermedia del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="9f73f-105">You may choose to compile any project using a new point release of the language.</span></span> <span data-ttu-id="9f73f-106">La scelta di una versione più recente del linguaggio consente al progetto di usare le nuove funzionalità del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="9f73f-106">Choosing a newer version of the language enables your project to make use of the latest language features.</span></span> <span data-ttu-id="9f73f-107">In altri scenari può essere necessario verificare che un progetto viene compilato senza errori quando si usa una versione precedente del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="9f73f-107">In other scenarios, you may need to validate that a project compiles cleanly when using an older version of the language.</span></span>

<span data-ttu-id="9f73f-108">Questa funzionalità separa l'installazione delle nuove versioni dell'SDK e degli strumenti nell'ambiente di sviluppo dalla decisione di incorporare nuove funzionalità del linguaggio in un progetto.</span><span class="sxs-lookup"><span data-stu-id="9f73f-108">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="9f73f-109">È possibile installare l'SDK e gli strumenti più recenti nel computer di compilazione.</span><span class="sxs-lookup"><span data-stu-id="9f73f-109">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="9f73f-110">Ogni progetto può essere configurato per usare una versione specifica del linguaggio in base alla relativa build.</span><span class="sxs-lookup"><span data-stu-id="9f73f-110">Each project can be configured to use a specific version of the language for its build.</span></span>

<span data-ttu-id="9f73f-111">Esistono tre modi per impostare la versione del linguaggio:</span><span class="sxs-lookup"><span data-stu-id="9f73f-111">There are three ways to set the language version:</span></span>

- <span data-ttu-id="9f73f-112">Modificare manualmente il [ **vbproj** file](#edit-the-vbproj-file)</span><span class="sxs-lookup"><span data-stu-id="9f73f-112">Manually edit your [**.vbproj** file](#edit-the-vbproj-file)</span></span>
- <span data-ttu-id="9f73f-113">Impostare la versione del linguaggio [per più progetti in una sottodirectory](#configure-multiple-projects)</span><span class="sxs-lookup"><span data-stu-id="9f73f-113">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects)</span></span>
- <span data-ttu-id="9f73f-114">Configurare il [ `-langversion` opzione del compilatore](#set-the-langversion-compiler-option)</span><span class="sxs-lookup"><span data-stu-id="9f73f-114">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option)</span></span>

## <a name="edit-the-vbproj-file"></a><span data-ttu-id="9f73f-115">Modificare il file vbproj</span><span class="sxs-lookup"><span data-stu-id="9f73f-115">Edit the vbproj file</span></span>

<span data-ttu-id="9f73f-116">È possibile impostare la versione del linguaggio nel **vbproj** file.</span><span class="sxs-lookup"><span data-stu-id="9f73f-116">You can set the language version in your **.vbproj** file.</span></span> <span data-ttu-id="9f73f-117">Aggiungere l'elemento seguente:</span><span class="sxs-lookup"><span data-stu-id="9f73f-117">Add the following element:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="9f73f-118">Il valore `latest` Usa la versione secondaria più recente del linguaggio Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9f73f-118">The value `latest` uses the latest minor version of the Visual Basic language.</span></span> <span data-ttu-id="9f73f-119">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="9f73f-119">Valid values are:</span></span>

|<span data-ttu-id="9f73f-120">Value</span><span class="sxs-lookup"><span data-stu-id="9f73f-120">Value</span></span>|<span data-ttu-id="9f73f-121">Significato</span><span class="sxs-lookup"><span data-stu-id="9f73f-121">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="9f73f-122">default</span><span class="sxs-lookup"><span data-stu-id="9f73f-122">default</span></span>|<span data-ttu-id="9f73f-123">Il compilatore accetta tutte le sintassi di linguaggio valide dalla versione principale più recente supportata.</span><span class="sxs-lookup"><span data-stu-id="9f73f-123">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="9f73f-124">9</span><span class="sxs-lookup"><span data-stu-id="9f73f-124">9</span></span>|<span data-ttu-id="9f73f-125">Il compilatore accetta solo la sintassi inclusa in Visual Basic 9.0 o inferiore.</span><span class="sxs-lookup"><span data-stu-id="9f73f-125">The compiler accepts only syntax that is included in Visual Basic 9.0 or lower.</span></span>|
|<span data-ttu-id="9f73f-126">10</span><span class="sxs-lookup"><span data-stu-id="9f73f-126">10</span></span>|<span data-ttu-id="9f73f-127">Il compilatore accetta solo la sintassi inclusa in Visual Basic 10.0 o inferiore.</span><span class="sxs-lookup"><span data-stu-id="9f73f-127">The compiler accepts only syntax that is included in Visual Basic 10.0 or lower.</span></span>|
|<span data-ttu-id="9f73f-128">11</span><span class="sxs-lookup"><span data-stu-id="9f73f-128">11</span></span>|<span data-ttu-id="9f73f-129">Il compilatore accetta solo la sintassi inclusa in Visual Basic 11.0 o inferiore.</span><span class="sxs-lookup"><span data-stu-id="9f73f-129">The compiler accepts only syntax that is included in Visual Basic 11.0 or lower.</span></span>|
|<span data-ttu-id="9f73f-130">12</span><span class="sxs-lookup"><span data-stu-id="9f73f-130">12</span></span>|<span data-ttu-id="9f73f-131">Il compilatore accetta solo la sintassi inclusa in Visual Basic 12.0 o inferiore.</span><span class="sxs-lookup"><span data-stu-id="9f73f-131">The compiler accepts only syntax that is included in Visual Basic 12.0 or lower.</span></span>|
|<span data-ttu-id="9f73f-132">14</span><span class="sxs-lookup"><span data-stu-id="9f73f-132">14</span></span>|<span data-ttu-id="9f73f-133">Il compilatore accetta solo la sintassi inclusa in Visual Basic 14.0 o inferiore.</span><span class="sxs-lookup"><span data-stu-id="9f73f-133">The compiler accepts only syntax that is included in Visual Basic 14.0 or lower.</span></span>|
|<span data-ttu-id="9f73f-134">15</span><span class="sxs-lookup"><span data-stu-id="9f73f-134">15</span></span>|<span data-ttu-id="9f73f-135">Il compilatore accetta solo la sintassi inclusa in Visual Basic 15.0 o inferiore.</span><span class="sxs-lookup"><span data-stu-id="9f73f-135">The compiler accepts only syntax that is included in Visual Basic 15.0 or lower.</span></span>|
|<span data-ttu-id="9f73f-136">15.3</span><span class="sxs-lookup"><span data-stu-id="9f73f-136">15.3</span></span>|<span data-ttu-id="9f73f-137">Il compilatore accetta solo la sintassi inclusa in Visual Basic 15.3 o inferiore.</span><span class="sxs-lookup"><span data-stu-id="9f73f-137">The compiler accepts only syntax that is included in Visual Basic 15.3 or lower.</span></span>|
|<span data-ttu-id="9f73f-138">15.5</span><span class="sxs-lookup"><span data-stu-id="9f73f-138">15.5</span></span>|<span data-ttu-id="9f73f-139">Il compilatore accetta solo la sintassi inclusa in Visual Basic 15.5 o inferiore.</span><span class="sxs-lookup"><span data-stu-id="9f73f-139">The compiler accepts only syntax that is included in Visual Basic 15.5 or lower.</span></span>|
|<span data-ttu-id="9f73f-140">latest</span><span class="sxs-lookup"><span data-stu-id="9f73f-140">latest</span></span>|<span data-ttu-id="9f73f-141">Il compilatore accetta tutte le sintassi di linguaggio valide.</span><span class="sxs-lookup"><span data-stu-id="9f73f-141">The compiler accepts all valid language syntax that it can support.</span></span>|

<span data-ttu-id="9f73f-142">Le stringhe speciali `default` e `latest` si risolvono rispettivamente nelle versioni principale e secondaria più recenti del linguaggio installate nel computer di compilazione.</span><span class="sxs-lookup"><span data-stu-id="9f73f-142">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

## <a name="configure-multiple-projects"></a><span data-ttu-id="9f73f-143">Configurare più progetti</span><span class="sxs-lookup"><span data-stu-id="9f73f-143">Configure multiple projects</span></span>

<span data-ttu-id="9f73f-144">È possibile creare un file **Directory.build.props** che contiene l'elemento `<LangVersion>` per configurare più directory.</span><span class="sxs-lookup"><span data-stu-id="9f73f-144">You can create a **Directory.build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="9f73f-145">Questa operazione viene in genere eseguita nella directory della soluzione.</span><span class="sxs-lookup"><span data-stu-id="9f73f-145">You typically do that in your solution directory.</span></span> <span data-ttu-id="9f73f-146">Aggiungere quanto segue a un file **Directory.build.props** nella directory della soluzione:</span><span class="sxs-lookup"><span data-stu-id="9f73f-146">Add the following to a **Directory.build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>15.5</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="9f73f-147">A questo punto, le compilazioni in tutte le sottodirectory della directory contenente file userà la sintassi di Visual Basic versione 15.5.</span><span class="sxs-lookup"><span data-stu-id="9f73f-147">Now, builds in every subdirectory of the directory containing that file will use Visual Basic version 15.5 syntax.</span></span> <span data-ttu-id="9f73f-148">Per altre informazioni, vedere l'articolo [Personalizzare la compilazione](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="9f73f-148">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="9f73f-149">Impostare l'opzione del compilatore langversion</span><span class="sxs-lookup"><span data-stu-id="9f73f-149">Set the langversion compiler option</span></span>

<span data-ttu-id="9f73f-150">È possibile usare l'opzione della riga di comando `-langversion`.</span><span class="sxs-lookup"><span data-stu-id="9f73f-150">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="9f73f-151">Per altre informazioni, vedere l'articolo relativo all'opzione del compilatore [-langversion](../reference/command-line-compiler/langversion.md).</span><span class="sxs-lookup"><span data-stu-id="9f73f-151">For more information, see the article on the [-langversion](../reference/command-line-compiler/langversion.md) compiler option.</span></span> <span data-ttu-id="9f73f-152">È possibile visualizzare un elenco dei valori validi digitando `vbc -langversion:?` .</span><span class="sxs-lookup"><span data-stu-id="9f73f-152">You can see a list of the valid values by typing  `vbc -langversion:?` .</span></span>
