---
title: 'Procedura: rimuovere un assembly dalla Global Assembly Cache'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a17478c350d789d320e97d6b50d6f5f9daaf6db3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-remove-an-assembly-from-the-global-assembly-cache"></a><span data-ttu-id="2c25c-102">Procedura: rimuovere un assembly dalla Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="2c25c-102">How to: Remove an Assembly from the Global Assembly Cache</span></span>
<span data-ttu-id="2c25c-103">Esistono due modi per rimuovere un assembly dalla Global Assembly Cache (GAC):</span><span class="sxs-lookup"><span data-stu-id="2c25c-103">There are two ways to remove an assembly from the global assembly cache (GAC):</span></span>  
  
-   <span data-ttu-id="2c25c-104">Usando lo [strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2c25c-104">By using the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span> <span data-ttu-id="2c25c-105">È possibile usare questa opzione per disinstallare gli assembly inseriti nella GAC durante le fasi di sviluppo e test.</span><span class="sxs-lookup"><span data-stu-id="2c25c-105">You can use this option to uninstall assemblies that you've placed in the GAC during development and testing.</span></span>  
  
-   <span data-ttu-id="2c25c-106">Usando [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx).</span><span class="sxs-lookup"><span data-stu-id="2c25c-106">By using [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx).</span></span> <span data-ttu-id="2c25c-107">È possibile usare questa opzione per disinstallare gli assembly quando si esegue il test dei pacchetti di installazione o per i sistemi di produzione.</span><span class="sxs-lookup"><span data-stu-id="2c25c-107">You should use this option to uninstall assemblies when testing installation packages and for production systems.</span></span>  
  
### <a name="removing-an-assembly-with-gacutilexe"></a><span data-ttu-id="2c25c-108">Rimozione di un assembly con Gacutil.exe</span><span class="sxs-lookup"><span data-stu-id="2c25c-108">Removing an assembly with Gacutil.exe</span></span>  
  
1.  <span data-ttu-id="2c25c-109">Al prompt dei comandi digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="2c25c-109">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="2c25c-110">**gacutil –u** \<*nome assembly*></span><span class="sxs-lookup"><span data-stu-id="2c25c-110">**gacutil –u** \<*assembly name*></span></span>  
  
     <span data-ttu-id="2c25c-111">In questo comando *nome assembly* è il nome dell'assembly da rimuovere dalla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="2c25c-111">In this command, *assembly name* is the name of the assembly to remove from the global assembly cache.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="2c25c-112">Evitare di usare Gacutil.exe per rimuovere assembly nei sistemi di produzione, perché è possibile che un assembly sia ancora richiesto da qualche applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c25c-112">You should not use Gacutil.exe to remove assemblies on production systems because of the possibility that the assembly may still be required by some application.</span></span> <span data-ttu-id="2c25c-113">Usare invece Windows Installer che mantiene un conteggio dei riferimenti per ogni assembly installato nella GAC.</span><span class="sxs-lookup"><span data-stu-id="2c25c-113">Instead, you should use the Windows Installer, which maintains a reference count for each assembly it installs in the GAC.</span></span>  
  
 <span data-ttu-id="2c25c-114">L'esempio seguente rimuove un assembly denominato `hello.dll` dalla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="2c25c-114">The following example removes an assembly named `hello.dll` from the global assembly cache.</span></span>  
  
```  
gacutil -u hello  
```  
  
### <a name="removing-an-assembly-with-windows-installer"></a><span data-ttu-id="2c25c-115">Rimozione di un assembly con Windows Installer</span><span class="sxs-lookup"><span data-stu-id="2c25c-115">Removing an assembly with Windows Installer</span></span>  
  
1.  <span data-ttu-id="2c25c-116">In **Programmi e funzionalità** nel **Pannello di controllo** selezionare l'app da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="2c25c-116">From the **Programs and Features** app in **Control Panel**, select the app that you want to uninstall.</span></span> <span data-ttu-id="2c25c-117">Se il pacchetto di installazione ha inserito assembly nella GAC, questi saranno rimossi da Windows Installer se non vengono usati da altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2c25c-117">If the installation package placed assemblies in the GAC, Windows Installer will remove them if they are not used by another application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c25c-118">Windows Installer mantiene un conteggio dei riferimenti per gli assembly installati nella GAC.</span><span class="sxs-lookup"><span data-stu-id="2c25c-118">Windows Installer maintains a reference count for assemblies installed in the GAC.</span></span> <span data-ttu-id="2c25c-119">La rimozione di un assembly dalla Global Assembly Cache avviene solo quando il conteggio dei riferimenti raggiunge zero. Ciò indica che non viene usato da altre applicazioni installate da un pacchetto di Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="2c25c-119">An assembly is removed from the GAC only when its reference count reaches zero, which indicates that it is not used by any application installed by a Windows Installer package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c25c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c25c-120">See Also</span></span>  
 [<span data-ttu-id="2c25c-121">Uso di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="2c25c-121">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="2c25c-122">Procedura: Installare un assembly nella Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="2c25c-122">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [<span data-ttu-id="2c25c-123">Gacutil.exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="2c25c-123">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
