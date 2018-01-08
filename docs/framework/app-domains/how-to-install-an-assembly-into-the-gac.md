---
title: 'Procedura: installare un assembly nella Global Assembly Cache'
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
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47867a82432ec6abe2245a0421d800c242d92b2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="6cc81-102">Procedura: installare un assembly nella Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="6cc81-102">How to: Install an Assembly into the Global Assembly Cache</span></span>
<span data-ttu-id="6cc81-103">Esistono due modi per installare un assembly con nome sicuro nella Global Assembly Cache:</span><span class="sxs-lookup"><span data-stu-id="6cc81-103">There are two ways to install a strong-named assembly into the global assembly cache (GAC):</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6cc81-104">Nella GAC possono essere installati solo assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="6cc81-104">Only strong-named assemblies can be installed into the GAC.</span></span> <span data-ttu-id="6cc81-105">Per informazioni su come creare un assembly con nome sicuro, vedere [Procedura: Firmare un assembly con un nome sicuro](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="6cc81-105">For information about how to create a strong-named assembly, see [How to: Sign an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
-   <span data-ttu-id="6cc81-106">Usando [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx).</span><span class="sxs-lookup"><span data-stu-id="6cc81-106">Using [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx).</span></span>  
  
     <span data-ttu-id="6cc81-107">Eseguire questa operazione in Visual Studio 2012 e Visual Studio 2013 creando un progetto InstallShield Limited Edition.</span><span class="sxs-lookup"><span data-stu-id="6cc81-107">You do this in Visual Studio 2012 and Visual Studio 2013 by creating an InstallShield Limited Edition Project.</span></span>  
  
     <span data-ttu-id="6cc81-108">Si tratta della modalità consigliata e più comune per l'aggiunta di assembly alla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="6cc81-108">This is the recommended and most common way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="6cc81-109">In tal modo si ottiene il conteggio dei riferimenti degli assembly nella Global Assembly Cache e altre utili funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6cc81-109">The installer provides reference counting of assemblies in the global assembly cache, plus other benefits.</span></span>  
  
-   <span data-ttu-id="6cc81-110">Usando lo [strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span><span class="sxs-lookup"><span data-stu-id="6cc81-110">Using the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span>  
  
     <span data-ttu-id="6cc81-111">È possibile usare Gacutil.exe per aggiungere assembly con nome sicuro alla Global Assembly Cache e visualizzare il contenuto di tale cache.</span><span class="sxs-lookup"><span data-stu-id="6cc81-111">You can use Gacutil.exe to add strong-named assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6cc81-112">È necessario usare Gacutil.exe solo in fase di sviluppo e non se ne consiglia l'uso per l'installazione di assembly di produzione nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="6cc81-112">Gacutil.exe is only for development purposes and should not be used to install production assemblies into the global assembly cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6cc81-113">Nelle versioni precedenti di .NET Framework, l'estensione della shell di Windows Shfusion.dll consente di installare gli assembly trascinandoli in Esplora file.</span><span class="sxs-lookup"><span data-stu-id="6cc81-113">In earlier versions of the .NET Framework, the Shfusion.dll Windows shell extension enabled you to install assemblies by dragging them in File Explorer.</span></span> <span data-ttu-id="6cc81-114">A partire da [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="6cc81-114">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
### <a name="to-use-the-global-assembly-cache-tool-gacutilexe"></a><span data-ttu-id="6cc81-115">Per usare lo strumento Global Assembly Cache (Gacutil.exe).</span><span class="sxs-lookup"><span data-stu-id="6cc81-115">To use the Global Assembly Cache tool (Gacutil.exe)</span></span>  
  
1.  <span data-ttu-id="6cc81-116">Al prompt dei comandi digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="6cc81-116">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="6cc81-117">**gacutil -i** \<*nome assembly*></span><span class="sxs-lookup"><span data-stu-id="6cc81-117">**gacutil -i** \<*assembly name*></span></span>  
  
     <span data-ttu-id="6cc81-118">In questo comando *nome assembly* è il nome dell'assembly da installare nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="6cc81-118">In this command, *assembly name* is the name of the assembly to install in the global assembly cache.</span></span>  
  
 <span data-ttu-id="6cc81-119">L'esempio seguente consente di installare un assembly con nome file `hello.dll` nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="6cc81-119">The following example installs an assembly with the file name `hello.dll` into the global assembly cache.</span></span>  
  
```  
gacutil -i hello.dll  
```  
  
 <span data-ttu-id="6cc81-120">Per altre informazioni, vedere [Strumento Global Assembly Cache (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span><span class="sxs-lookup"><span data-stu-id="6cc81-120">For more information, see [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span>  
  
### <a name="to-use-an-installshield-limited-edition-project"></a><span data-ttu-id="6cc81-121">Per usare un progetto InstallShield Limited Edition</span><span class="sxs-lookup"><span data-stu-id="6cc81-121">To use an InstallShield Limited Edition Project</span></span>  
  
1.  <span data-ttu-id="6cc81-122">Aggiungere un pacchetto di installazione e distribuzione alla soluzione aprendo il menu di scelta rapida per la soluzione e scegliendo **Aggiungi**, **Nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="6cc81-122">Add a setup and deployment package to your solution by opening the shortcut menu for your solution, and then choosing **Add**, **New Project**.</span></span>  
  
2.  <span data-ttu-id="6cc81-123">Nella finestra di dialogo **Aggiungi nuovo progetto** nella cartella **Installato** scegliere **Altri tipi di progetto**, **Installazione e distribuzione**, **InstallShield Limited Edition** e assegnare un nome al progetto.</span><span class="sxs-lookup"><span data-stu-id="6cc81-123">In the **Add New Project** dialog box, in the **Installed** folder, choose **Other Project Types**,  **Setup and Deployment**, **InstallShield Limited Edition**, and give your project a name.</span></span> <span data-ttu-id="6cc81-124">(Se richiesto, scaricare, installare e attivare InstallShield.)</span><span class="sxs-lookup"><span data-stu-id="6cc81-124">(If prompted, download, install, and activate InstallShield.)</span></span>  
  
3.  <span data-ttu-id="6cc81-125">Eseguire la configurazione generale del progetto di installazione e di distribuzione usando Project Assistant in **Esplora soluzioni** oppure scegliendo i passaggi secondari dei passaggi numerati in **Esplora soluzioni**. Configurare l'installazione nello stesso modo in cui viene configurata quando non vengono aggiunti assembly nella Global Assembly Cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="6cc81-125">Perform the general configuration of your setup and deployment project either by using the Project Assistant in **Solution Explorer**, or by choosing the substeps of the numbered steps in the **Solution Explorer**.Configure your setup as you would if you were not adding assemblies to the GAC.</span></span>  
  
4.  <span data-ttu-id="6cc81-126">Per avviare il processo di aggiunta di un assembly nella GAC, scegliere **File** nel passaggio **Specifica dati applicazione** in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="6cc81-126">To begin the process of adding an assembly to the GAC, choose **Files**, which is under the **Specify Application Data** step in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="6cc81-127">Nel riquadro **Cartelle computer di destinazione** aprire il menu di scelta rapida per **Computer di destinazione**, quindi scegliere **Mostra cartella predefinita**, **[GlobalAssemblyCache]**.</span><span class="sxs-lookup"><span data-stu-id="6cc81-127">In the **Destination computer's folders** pane, open the shortcut menu for **Destination Computer**, and then choose **Show Predefined Folder**, **[GlobalAssemblyCache]**.</span></span>  
  
6.  <span data-ttu-id="6cc81-128">Per ogni progetto nella soluzione che contiene un assembly che si desidera installare nella Global Assembly Cache:</span><span class="sxs-lookup"><span data-stu-id="6cc81-128">For each project in the solution that contains an assembly that you want to install in the global assembly cache:</span></span>  
  
    1.  <span data-ttu-id="6cc81-129">Nel riquadro **Cartelle computer di origine** scegliere il progetto.</span><span class="sxs-lookup"><span data-stu-id="6cc81-129">In the **Source computer's folders** pane, choose the project.</span></span>  
  
    2.  <span data-ttu-id="6cc81-130">Nel riquadro **Cartelle computer di destinazione** scegliere **[GlobalAssemblyCache]**.</span><span class="sxs-lookup"><span data-stu-id="6cc81-130">In the **Destination computer's folders** pane, choose **[GlobalAssemblyCache]**.</span></span>  
  
    3.  <span data-ttu-id="6cc81-131">Nel riquadro **File computer di origine** scegliere **Output primario da** *<nome_progetto>*.</span><span class="sxs-lookup"><span data-stu-id="6cc81-131">In the **Source computer's files** pane, choose **Primary output from** *<project_name>*.</span></span>  
  
    4.  <span data-ttu-id="6cc81-132">Trascinare il file nel passaggio c al riquadro di **File computer di destinazione** oppure usare i comandi **Copia** e **Incolla** dal menu di scelta rapida del file.</span><span class="sxs-lookup"><span data-stu-id="6cc81-132">Drag the file in step c to the **Destination computer's files** pane (or use the **Copy** and **Paste** commands from the file's shortcut menu).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cc81-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cc81-133">See Also</span></span>  
 [<span data-ttu-id="6cc81-134">Uso di assembly e della Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="6cc81-134">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="6cc81-135">Procedura: Rimuovere un assembly dalla Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="6cc81-135">How to: Remove an Assembly from the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 [<span data-ttu-id="6cc81-136">Gacutil.exe (strumento Global Assembly Cache)</span><span class="sxs-lookup"><span data-stu-id="6cc81-136">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
 [<span data-ttu-id="6cc81-137">Procedura: Firmare un assembly con un nome sicuro</span><span class="sxs-lookup"><span data-stu-id="6cc81-137">How to: Sign an Assembly with a Strong Name</span></span>](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="6cc81-138">Distribuzione con Windows Installer</span><span class="sxs-lookup"><span data-stu-id="6cc81-138">Windows Installer Deployment</span></span>](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)
