---
title: 'Procedura: visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3964551ba2eec0980541e95a7db20ef057a1dd61
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="edceb-102">Procedura: visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="edceb-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="edceb-103">Quando si sviluppano e si distribuiscono i controlli, si consiglia di tali controlli siano visibili nel **Scegli elementi della casella degli strumenti** nella finestra di dialogo viene visualizzata quando si fa clic su di **della casella degli strumenti** e selezionare  **Scegli elementi**.</span><span class="sxs-lookup"><span data-stu-id="edceb-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="edceb-104">È possibile abilitare il controllo venga visualizzato nella finestra di dialogo mediante la procedura di registrazione AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="edceb-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="edceb-105">Per visualizzare il controllo nella finestra di dialogo Scegli elementi della casella degli strumenti</span><span class="sxs-lookup"><span data-stu-id="edceb-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
-   <span data-ttu-id="edceb-106">Installare l'assembly di controllo per global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="edceb-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="edceb-107">Per ulteriori informazioni, vedere [procedura: installare un Assembly nella Global Assembly Cache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="edceb-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="edceb-108">oppure</span><span class="sxs-lookup"><span data-stu-id="edceb-108">-or-</span></span>  
  
-   <span data-ttu-id="edceb-109">Registrare il controllo e i relativi assembly in fase di progettazione associato utilizzando la procedura di registrazione AssemblyFoldersEx.</span><span class="sxs-lookup"><span data-stu-id="edceb-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="edceb-110">AssemblyFoldersEx è un percorso del Registro di sistema in cui archiviare i percorsi per ogni versione di framework che supportano i fornitori di terze parti.</span><span class="sxs-lookup"><span data-stu-id="edceb-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="edceb-111">Risoluzione in fase di progettazione è possibile esaminare in questo percorso del Registro di sistema per individuare gli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="edceb-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="edceb-112">Lo script del Registro di sistema può specificare i controlli che si desidera visualizzare nella casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="edceb-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="edceb-113">Per ulteriori informazioni, vedere [la distribuzione di un controllo personalizzato e gli assembly in fase di progettazione (Visual Studio 2013)](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span><span class="sxs-lookup"><span data-stu-id="edceb-113">For more information, see [Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edceb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edceb-114">See Also</span></span>  
 [<span data-ttu-id="edceb-115">Finestra di dialogo Scegli elementi della Casella degli strumenti (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="edceb-115">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="edceb-116">Distribuzione di un controllo personalizzato e gli assembly in fase di progettazione (Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="edceb-116">Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)</span></span>](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)  
 [<span data-ttu-id="edceb-117">Sviluppo di controlli Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="edceb-117">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="edceb-118">Procedura: Installare un assembly nella Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="edceb-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [<span data-ttu-id="edceb-119">Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="edceb-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
