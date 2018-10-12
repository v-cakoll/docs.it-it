---
title: Installare un assembly nella Global Assembly Cache
ms.date: 09/20/2018
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
ms.openlocfilehash: d365ac77fe6cd7fc4fca36705729ec12b06d6830
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46584581"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="a9931-102">Procedura: Installare un assembly nella Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a9931-102">How to: Install an assembly into the global assembly cache</span></span>

<span data-ttu-id="a9931-103">Esistono due modi per installare un assembly con nome sicuro nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a9931-103">There are two ways to install a strong-named assembly into the global assembly cache (GAC).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9931-104">Nella GAC possono essere installati solo assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="a9931-104">Only strong-named assemblies can be installed into the GAC.</span></span> <span data-ttu-id="a9931-105">Per informazioni su come creare un assembly con nome sicuro, vedere [Procedura: Firmare un assembly con un nome sicuro](how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="a9931-105">For information about how to create a strong-named assembly, see [How to: Sign an Assembly with a Strong Name](how-to-sign-an-assembly-with-a-strong-name.md).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="a9931-106">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="a9931-106">Windows Installer</span></span>

<span data-ttu-id="a9931-107">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), il motore di installazione di Windows, è la scelta consigliata per aggiungere gli assembly alla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a9931-107">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), the Windows installation engine, is the recommended way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="a9931-108">Windows Installer ottiene il conteggio dei riferimenti degli assembly nella Global Assembly Cache e altre utili funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a9931-108">Windows Installer provides reference counting of assemblies in the global assembly cache and other benefits.</span></span> <span data-ttu-id="a9931-109">È possibile usare l'[estensione WiX Toolset per Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension) per creare un pacchetto di installazione per Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="a9931-109">You can use the [WiX Toolset extension for Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension) to create an installer package for Windows Installer.</span></span>

## <a name="global-assembly-cache-tool"></a><span data-ttu-id="a9931-110">Strumento Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a9931-110">Global assembly cache tool</span></span>

<span data-ttu-id="a9931-111">È possibile usare lo [strumento Global Assembly Cache (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) per aggiungere assembly con nome sicuro alla Global Assembly Cache e visualizzare il contenuto di tale cache.</span><span class="sxs-lookup"><span data-stu-id="a9931-111">You can use the [Global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add strong-named assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a9931-112">È necessario usare Gacutil.exe solo in fase di sviluppo e non se ne consiglia l'uso per l'installazione di assembly di produzione nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a9931-112">Gacutil.exe is only for development purposes and should not be used to install production assemblies into the global assembly cache.</span></span>

<span data-ttu-id="a9931-113">La sintassi di gacutil è la seguente:</span><span class="sxs-lookup"><span data-stu-id="a9931-113">The syntax for gacutil is as follows:</span></span>

```shell
gacutil -i <assembly name>
```

<span data-ttu-id="a9931-114">In questo comando *nome assembly* è il nome dell'assembly da installare nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a9931-114">In this command, *assembly name* is the name of the assembly to install in the global assembly cache.</span></span>

<span data-ttu-id="a9931-115">L'esempio seguente consente di installare un assembly con nome file `hello.dll` nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="a9931-115">The following example installs an assembly with the file name `hello.dll` into the global assembly cache.</span></span>

```shell
gacutil -i hello.dll
```

> [!NOTE]
> <span data-ttu-id="a9931-116">Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows Shfusion.dll consente di installare gli assembly trascinandoli in **Esplora file**.</span><span class="sxs-lookup"><span data-stu-id="a9931-116">In earlier versions of the .NET Framework, the Shfusion.dll Windows shell extension enabled you to install assemblies by dragging them in **File Explorer**.</span></span> <span data-ttu-id="a9931-117">A partire da .NET Framework 4, Shfusion.dll è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="a9931-117">Beginning with the .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9931-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9931-118">See also</span></span>

- [<span data-ttu-id="a9931-119">Uso di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a9931-119">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="a9931-120">Procedura: Rimuovere un assembly dalla Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a9931-120">How to: Remove an Assembly from the Global Assembly Cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)
- [<span data-ttu-id="a9931-121">Gacutil.exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="a9931-121">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
- [<span data-ttu-id="a9931-122">Procedura: Firmare un assembly con un nome sicuro</span><span class="sxs-lookup"><span data-stu-id="a9931-122">How to: Sign an Assembly with a Strong Name</span></span>](how-to-sign-an-assembly-with-a-strong-name.md)