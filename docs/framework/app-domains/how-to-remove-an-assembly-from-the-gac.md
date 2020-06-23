---
title: 'Procedura: Rimuovere un assembly dalla Global Assembly Cache'
description: Informazioni su come rimuovere un assembly dal Global Assembly Cache in .NET, usando lo strumento di Global Assembly Cache (Gacutil.exe) o Windows Installer.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- global assembly cache, removing assemblies
- strong-named assemblies, global assembly cache
- removing assemblies from global assembly cache
- deleting assemblies in global assembly cache
- Global Assembly Cache tool
- GAC (global assembly cache), removing assemblies
ms.assetid: acdcc588-b458-436d-876c-726de68244c1
ms.openlocfilehash: e3a596ea6029ded190c33032e96b601de9d4012d
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104767"
---
# <a name="how-to-remove-an-assembly-from-the-global-assembly-cache"></a><span data-ttu-id="5b14b-103">Procedura: Rimuovere un assembly dalla Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="5b14b-103">How to: Remove an Assembly from the Global Assembly Cache</span></span>

<span data-ttu-id="5b14b-104">Esistono due modi per rimuovere un assembly dalla Global Assembly Cache (GAC):</span><span class="sxs-lookup"><span data-stu-id="5b14b-104">There are two ways to remove an assembly from the global assembly cache (GAC):</span></span>

- <span data-ttu-id="5b14b-105">Usando lo [strumento Global Assembly Cache (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md).</span><span class="sxs-lookup"><span data-stu-id="5b14b-105">By using the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md).</span></span> <span data-ttu-id="5b14b-106">È possibile usare questa opzione per disinstallare gli assembly inseriti nella GAC durante le fasi di sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="5b14b-106">You can use this option to uninstall assemblies that you've placed in the GAC during development and testing.</span></span>

- <span data-ttu-id="5b14b-107">Usando [Windows Installer](/windows/desktop/Msi/windows-installer-portal).</span><span class="sxs-lookup"><span data-stu-id="5b14b-107">By using [Windows Installer](/windows/desktop/Msi/windows-installer-portal).</span></span> <span data-ttu-id="5b14b-108">È possibile usare questa opzione per disinstallare gli assembly quando si esegue il test dei pacchetti di installazione o per i sistemi di produzione.</span><span class="sxs-lookup"><span data-stu-id="5b14b-108">You should use this option to uninstall assemblies when testing installation packages and for production systems.</span></span>

## <a name="removing-an-assembly-with-gacutilexe"></a><span data-ttu-id="5b14b-109">Rimozione di un assembly con Gacutil.exe</span><span class="sxs-lookup"><span data-stu-id="5b14b-109">Removing an assembly with Gacutil.exe</span></span>

<span data-ttu-id="5b14b-110">Al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5b14b-110">At the command prompt, type the following command:</span></span>

<span data-ttu-id="5b14b-111">**gacutil – u**\<*assembly name*></span><span class="sxs-lookup"><span data-stu-id="5b14b-111">**gacutil –u** \<*assembly name*></span></span>

<span data-ttu-id="5b14b-112">In questo comando *nome assembly* è il nome dell'assembly da rimuovere dalla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="5b14b-112">In this command, *assembly name* is the name of the assembly to remove from the global assembly cache.</span></span>

> [!WARNING]
> <span data-ttu-id="5b14b-113">Evitare di usare Gacutil.exe per rimuovere assembly nei sistemi di produzione, perché è possibile che un assembly sia ancora richiesto da qualche applicazione.</span><span class="sxs-lookup"><span data-stu-id="5b14b-113">You should not use Gacutil.exe to remove assemblies on production systems because of the possibility that the assembly may still be required by some application.</span></span> <span data-ttu-id="5b14b-114">Usare invece Windows Installer che mantiene un conteggio dei riferimenti per ogni assembly installato nella GAC.</span><span class="sxs-lookup"><span data-stu-id="5b14b-114">Instead, you should use the Windows Installer, which maintains a reference count for each assembly it installs in the GAC.</span></span>

<span data-ttu-id="5b14b-115">Nell'esempio seguente viene rimosso un assembly denominato `hello.dll` dal Global assembly cache:</span><span class="sxs-lookup"><span data-stu-id="5b14b-115">The following example removes an assembly named `hello.dll` from the global assembly cache:</span></span>

```console
gacutil -u hello
```

## <a name="removing-an-assembly-with-windows-installer"></a><span data-ttu-id="5b14b-116">Rimozione di un assembly con Windows Installer</span><span class="sxs-lookup"><span data-stu-id="5b14b-116">Removing an assembly with Windows Installer</span></span>

<span data-ttu-id="5b14b-117">In **Programmi e funzionalità** nel **Pannello di controllo** selezionare l'app da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="5b14b-117">From the **Programs and Features** app in **Control Panel**, select the app that you want to uninstall.</span></span> <span data-ttu-id="5b14b-118">Se il pacchetto di installazione ha inserito assembly nella GAC, questi saranno rimossi da Windows Installer se non vengono usati da altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="5b14b-118">If the installation package placed assemblies in the GAC, Windows Installer will remove them if they are not used by another application.</span></span>

> [!NOTE]
> <span data-ttu-id="5b14b-119">Windows Installer mantiene un conteggio dei riferimenti per gli assembly installati nella GAC.</span><span class="sxs-lookup"><span data-stu-id="5b14b-119">Windows Installer maintains a reference count for assemblies installed in the GAC.</span></span> <span data-ttu-id="5b14b-120">La rimozione di un assembly dalla Global Assembly Cache avviene solo quando il conteggio dei riferimenti raggiunge zero. Ciò indica che non viene usato da altre applicazioni installate da un pacchetto di Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="5b14b-120">An assembly is removed from the GAC only when its reference count reaches zero, which indicates that it is not used by any application installed by a Windows Installer package.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b14b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b14b-121">See also</span></span>

- [<span data-ttu-id="5b14b-122">Utilizzo di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="5b14b-122">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="5b14b-123">Procedura: installare un assembly nella global assembly cache</span><span class="sxs-lookup"><span data-stu-id="5b14b-123">How to: Install an Assembly into the Global Assembly Cache</span></span>](install-assembly-into-gac.md)
- [<span data-ttu-id="5b14b-124">Gacutil.exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="5b14b-124">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
