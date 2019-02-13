---
title: 'Procedura: Installare un assembly nella Global Assembly Cache'
ms.date: 02/05/2019
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 233a7803cb59f9bfeac15d293dc3fb5a0db449c9
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2019
ms.locfileid: "55903751"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="9d0cc-102">Procedura: Installare un assembly nella Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="9d0cc-102">How to: Install an assembly into the global assembly cache</span></span>

<span data-ttu-id="9d0cc-103">Gli assembly condivisi da più applicazioni vengono archiviati nella Global Assembly Cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="9d0cc-103">The global assembly cache (GAC) stores assemblies that several applications share.</span></span> <span data-ttu-id="9d0cc-104">Installare un assembly nella [Global Assembly Cache](gac.md) con uno dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d0cc-104">Install an assembly into the [global assembly cache](gac.md) with one of the following components:</span></span> 
- [<span data-ttu-id="9d0cc-105">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="9d0cc-105">Windows Installer</span></span>](#windows-installer)
- [<span data-ttu-id="9d0cc-106">Strumento Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="9d0cc-106">Global assembly cache tool</span></span>](#global-assembly-cache-tool)

> [!IMPORTANT]
> <span data-ttu-id="9d0cc-107">Nella GAC possono essere installati solo assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="9d0cc-107">You can install only strong-named assemblies into the GAC.</span></span> <span data-ttu-id="9d0cc-108">Per informazioni sulla creazione di un assembly con nome sicuro, vedere [Procedura: Firmare un assembly con un nome sicuro](how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="9d0cc-108">For information about how to create a strong-named assembly, see [How to: Sign an assembly with a strong name](how-to-sign-an-assembly-with-a-strong-name.md).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="9d0cc-109">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="9d0cc-109">Windows Installer</span></span>

<span data-ttu-id="9d0cc-110">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), il motore di installazione di Windows, è la scelta consigliata per aggiungere gli assembly alla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="9d0cc-110">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), the Windows installation engine, is the recommended way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="9d0cc-111">Windows Installer ottiene il conteggio dei riferimenti degli assembly nella Global Assembly Cache e altre utili funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9d0cc-111">Windows Installer provides reference counting of assemblies in the global assembly cache and other benefits.</span></span> <span data-ttu-id="9d0cc-112">Per creare un pacchetto di installazione per Windows Installer, usare l'[estensione WiX Toolset per Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).</span><span class="sxs-lookup"><span data-stu-id="9d0cc-112">To create an installer package for Windows Installer, use the [WiX toolset extension for Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).</span></span>

## <a name="global-assembly-cache-tool"></a><span data-ttu-id="9d0cc-113">Strumento Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="9d0cc-113">Global assembly cache tool</span></span>

<span data-ttu-id="9d0cc-114">È possibile usare lo [strumento Global Assembly Cache (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per aggiungere assembly alla Global Assembly Cache e visualizzare il contenuto di tale cache.</span><span class="sxs-lookup"><span data-stu-id="9d0cc-114">You can use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9d0cc-115">*Gacutil.exe* è progettato esclusivamente per lo sviluppo.</span><span class="sxs-lookup"><span data-stu-id="9d0cc-115">*Gacutil.exe* is for development purposes only.</span></span> <span data-ttu-id="9d0cc-116">Non usarlo per installare assembly di produzione nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="9d0cc-116">Don't use it to install production assemblies into the global assembly cache.</span></span>

<span data-ttu-id="9d0cc-117">La sintassi per usare *gacutil.exe* per installare un assembly nella Global Assembly Cache è la seguente:</span><span class="sxs-lookup"><span data-stu-id="9d0cc-117">The syntax for using *gacutil.exe* to install an assembly in the GAC is as follows:</span></span>

```console
gacutil -i <assembly name>
```

<span data-ttu-id="9d0cc-118">In questo comando *\<nome assembly>* è il nome dell'assembly da installare nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="9d0cc-118">In this command, *\<assembly name>* is the name of the assembly to install in the global assembly cache.</span></span>

<span data-ttu-id="9d0cc-119">Se *gacutil.exe* non è presente nel percorso di sistema, usare il [Prompt dei comandi per gli sviluppatori per VS *\<versione>*](../tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="9d0cc-119">If *gacutil.exe* isn't in your system path, use the [Developer Command Prompt for VS *\<version>*](../tools/developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="9d0cc-120">L'esempio seguente consente di installare un assembly con nome file *hello.dll* nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="9d0cc-120">The following example installs an assembly with the file name *hello.dll* into the global assembly cache.</span></span>

```console
gacutil -i hello.dll
```

> [!NOTE]
> <span data-ttu-id="9d0cc-121">Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows *Shfusion.dll* consente di installare gli assembly trascinandoli in Esplora file.</span><span class="sxs-lookup"><span data-stu-id="9d0cc-121">In earlier versions of the .NET Framework, the *Shfusion.dll* Windows shell extension let you install assemblies by dragging them to File Explorer.</span></span> <span data-ttu-id="9d0cc-122">A partire da .NET Framework 4, *Shfusion.dll* è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="9d0cc-122">Beginning with .NET Framework 4, *Shfusion.dll* is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d0cc-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d0cc-123">See also</span></span>

- [<span data-ttu-id="9d0cc-124">Uso di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="9d0cc-124">Working with assemblies and the global assembly cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="9d0cc-125">Procedura: Rimuovere un assembly dalla Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="9d0cc-125">How to: Remove an assembly from the global assembly cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)
- [<span data-ttu-id="9d0cc-126">Gacutil.exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="9d0cc-126">Gacutil.exe (Global assembly cache tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
- [<span data-ttu-id="9d0cc-127">Procedura: Firmare un assembly con un nome sicuro</span><span class="sxs-lookup"><span data-stu-id="9d0cc-127">How to: Sign an assembly with a strong name</span></span>](how-to-sign-an-assembly-with-a-strong-name.md)
