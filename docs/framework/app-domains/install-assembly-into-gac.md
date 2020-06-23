---
title: 'Procedura: Installare un assembly nella Global Assembly Cache'
description: Installare un assembly nel Global Assembly Cache (GAC) in .NET in modo che possa essere condiviso da molte applicazioni. Utilizzare Windows Installer o l'utilità GAC.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
ms.openlocfilehash: 08a5475d74327265f28b65676ae56be15afb57d3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104671"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="72872-104">Procedura: Installare un assembly nella Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="72872-104">How to: Install an assembly into the global assembly cache</span></span>

<span data-ttu-id="72872-105">Gli assembly condivisi da più applicazioni vengono archiviati nella Global Assembly Cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="72872-105">The global assembly cache (GAC) stores assemblies that several applications share.</span></span> <span data-ttu-id="72872-106">Installare un assembly nella [Global Assembly Cache](gac.md) con uno dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="72872-106">Install an assembly into the [global assembly cache](gac.md) with one of the following components:</span></span>

- [<span data-ttu-id="72872-107">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="72872-107">Windows Installer</span></span>](#windows-installer)
- [<span data-ttu-id="72872-108">Strumento Global assembly cache</span><span class="sxs-lookup"><span data-stu-id="72872-108">Global Assembly Cache tool</span></span>](#global-assembly-cache-tool)

> [!IMPORTANT]
> <span data-ttu-id="72872-109">È possibile installare solo assembly con nome sicuro in Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="72872-109">You can install only strong-named assemblies into the global assembly cache.</span></span> <span data-ttu-id="72872-110">Per informazioni su come creare un assembly con nome sicuro, vedere [procedura: firmare un assembly con un nome sicuro](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="72872-110">For information about how to create a strong-named assembly, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="72872-111">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="72872-111">Windows Installer</span></span>

<span data-ttu-id="72872-112">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), il motore di installazione di Windows, è la scelta consigliata per aggiungere gli assembly alla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="72872-112">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), the Windows installation engine, is the recommended way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="72872-113">Windows Installer ottiene il conteggio dei riferimenti degli assembly nella Global Assembly Cache e altre utili funzionalità.</span><span class="sxs-lookup"><span data-stu-id="72872-113">Windows Installer provides reference counting of assemblies in the global assembly cache and other benefits.</span></span> <span data-ttu-id="72872-114">Per creare un pacchetto di installazione per Windows Installer, usare l'[estensione WiX Toolset per Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).</span><span class="sxs-lookup"><span data-stu-id="72872-114">To create an installer package for Windows Installer, use the [WiX toolset extension for Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).</span></span>

## <a name="global-assembly-cache-tool"></a><span data-ttu-id="72872-115">Global Assembly Cache (strumento)</span><span class="sxs-lookup"><span data-stu-id="72872-115">Global Assembly Cache tool</span></span>

<span data-ttu-id="72872-116">È possibile utilizzare l' [utilità Global Assembly Cache (gacutil.exe) di .NET](../tools/gacutil-exe-gac-tool.md) per aggiungere assembly al Global assembly cache e visualizzare il contenuto del Global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="72872-116">You can use the [.NET Global Assembly Cache utility (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>

   > [!NOTE]
   > <span data-ttu-id="72872-117">*Gacutil.exe* è progettato esclusivamente per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="72872-117">*Gacutil.exe* is for development purposes only.</span></span> <span data-ttu-id="72872-118">Non usarlo per installare assembly di produzione nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="72872-118">Don't use it to install production assemblies into the global assembly cache.</span></span>

<span data-ttu-id="72872-119">La sintassi per usare *gacutil.exe* per installare un assembly nella Global Assembly Cache è la seguente:</span><span class="sxs-lookup"><span data-stu-id="72872-119">The syntax for using *gacutil.exe* to install an assembly in the GAC is as follows:</span></span>

```cmd
gacutil -i <assembly name>
```

<span data-ttu-id="72872-120">In questo comando *\<assembly name>* è il nome dell'assembly da installare nel Global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="72872-120">In this command, *\<assembly name>* is the name of the assembly to install in the global assembly cache.</span></span>

<span data-ttu-id="72872-121">Se *gacutil.exe* non è presente nel percorso di sistema, usare il [prompt dei comandi *\<version>* per gli sviluppatori per Visual ](../tools/developer-command-prompt-for-vs.md)Studio.</span><span class="sxs-lookup"><span data-stu-id="72872-121">If *gacutil.exe* isn't in your system path, use the [Developer command prompt for VS *\<version>*](../tools/developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="72872-122">L'esempio seguente consente di installare un assembly con nome file *hello.dll* nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="72872-122">The following example installs an assembly with the file name *hello.dll* into the global assembly cache.</span></span>

```cmd
gacutil -i hello.dll
```

> [!NOTE]
> <span data-ttu-id="72872-123">Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows *Shfusion.dll* consente di installare gli assembly trascinandoli in Esplora file.</span><span class="sxs-lookup"><span data-stu-id="72872-123">In earlier versions of the .NET Framework, the *Shfusion.dll* Windows shell extension let you install assemblies by dragging them to File Explorer.</span></span> <span data-ttu-id="72872-124">A partire da .NET Framework 4, *Shfusion.dll* è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="72872-124">Beginning with .NET Framework 4, *Shfusion.dll* is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="72872-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72872-125">See also</span></span>

- [<span data-ttu-id="72872-126">Usare gli assembly e i Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="72872-126">Work with assemblies and the global assembly cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="72872-127">Procedura: rimuovere un assembly dalla Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="72872-127">How to: Remove an assembly from the global assembly cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)
- [<span data-ttu-id="72872-128">Gacutil.exe (strumento Global assembly cache)</span><span class="sxs-lookup"><span data-stu-id="72872-128">Gacutil.exe (Global Assembly Cache tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
- [<span data-ttu-id="72872-129">Procedura: firmare un assembly con un nome sicuro</span><span class="sxs-lookup"><span data-stu-id="72872-129">How to: Sign an assembly with a strong name</span></span>](../../standard/assembly/sign-strong-name.md)
