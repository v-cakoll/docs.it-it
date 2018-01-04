---
title: Finestre di dialogo in Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dialog boxes [Windows Forms], Windows Forms
- Windows Forms dialog boxes
- dialogs [Windows Forms], using in Windows Forms
ms.assetid: d43d022b-451b-490d-9386-dc79d98fbf8a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b8f493013744ffa7819d4cb554f794d9a591a371
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="dialog-boxes-in-windows-forms"></a><span data-ttu-id="9f387-102">Finestre di dialogo in Windows Form</span><span class="sxs-lookup"><span data-stu-id="9f387-102">Dialog Boxes in Windows Forms</span></span>
<span data-ttu-id="9f387-103">Le finestre di dialogo sono usate per interagire con l'utente e recuperare informazioni.</span><span class="sxs-lookup"><span data-stu-id="9f387-103">Dialog boxes are used to interact with the user and retrieve information.</span></span> <span data-ttu-id="9f387-104">Detto semplicemente, una finestra di dialogo è un form con la proprietà dell'enumerazione <xref:System.Windows.Forms.FormBorderStyle> impostata su `FixedDialog`.</span><span class="sxs-lookup"><span data-stu-id="9f387-104">In simple terms, a dialog box is a form with its <xref:System.Windows.Forms.FormBorderStyle> enumeration property set to `FixedDialog`.</span></span> <span data-ttu-id="9f387-105">È possibile creare finestre di dialogo personalizzate usando Progettazione Windows Form in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f387-105">You can construct your own custom dialog boxes by using the Windows Forms Designer in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="9f387-106">Per personalizzare le finestre di dialogo in base a esigenze specifiche, aggiungere controlli come `Label`, `Textbox` e `Button`.</span><span class="sxs-lookup"><span data-stu-id="9f387-106">Add controls such as `Label`, `Textbox`, and `Button` to customize dialog boxes to your specific needs.</span></span> <span data-ttu-id="9f387-107">Il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] include anche finestre di dialogo predefinite, ad esempio **Apri File** e finestre di messaggio, è possibile adattare le proprie applicazioni.</span><span class="sxs-lookup"><span data-stu-id="9f387-107">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] also includes predefined dialog boxes, such as **File Open** and message boxes, which you can adapt for your own applications.</span></span> <span data-ttu-id="9f387-108">Per ulteriori informazioni, vedere [componenti e controlli della finestra di dialogo](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9f387-108">For more information, see [Dialog-Box Controls and Components](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f387-109">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="9f387-109">In This Section</span></span>  
 [<span data-ttu-id="9f387-110">Procedura: Visualizzare le finestre di dialogo per Windows Form</span><span class="sxs-lookup"><span data-stu-id="9f387-110">How to: Display Dialog Boxes for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-display-dialog-boxes-for-windows-forms.md)  
 <span data-ttu-id="9f387-111">Fornisce indicazioni per la visualizzazione delle finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="9f387-111">Gives directions for showing dialog boxes.</span></span>  
  
-   <span data-ttu-id="9f387-112">[Procedura: recuperare informazioni in modo selettivo usando più proprietà finestra](http://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f387-112">[How to: Retrieve Dialog Box Information Selectively Using Multiple Properties](http://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9f387-113">[Procedura: recuperare informazioni dal Form padre di una finestra di dialogo](http://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f387-113">[How to: Retrieve Information from the Parent Form of a Dialog Box](http://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9f387-114">[Input dell'utente alle finestre di dialogo](http://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f387-114">[User Input to Dialog Boxes](http://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9f387-115">[Procedura: recuperare il risultato delle finestre di dialogo](http://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f387-115">[How to: Retrieve the Result for Dialog Boxes](http://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9f387-116">[Procedura dettagliata: Recupero di informazioni tramite oggetti finestra](http://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f387-116">[Walkthrough: Retrieving Dialog Box Information Collectively Using Objects](http://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9f387-117">[Procedura: chiudere finestre di dialogo e mantenere l'Input dell'utente](http://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f387-117">[How to: Close Dialog Boxes and Retain User Input](http://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9f387-118">[Procedura: creare finestre di dialogo in fase di progettazione](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f387-118">[How to: Create Dialog Boxes at Design Time](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9f387-119">[Procedura: visualizzare le finestre di messaggio](http://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9f387-119">[How to: Display Message Boxes](http://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9f387-120">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="9f387-120">Related Sections</span></span>  
 [<span data-ttu-id="9f387-121">Controlli e componenti della finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="9f387-121">Dialog-Box Controls and Components</span></span>](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 <span data-ttu-id="9f387-122">Elenca i controlli predefiniti della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="9f387-122">Lists the predefined dialog box controls.</span></span>  
  
 [<span data-ttu-id="9f387-123">Modifica dell'aspetto di Windows Form</span><span class="sxs-lookup"><span data-stu-id="9f387-123">Changing the Appearance of Windows Forms</span></span>](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)  
 <span data-ttu-id="9f387-124">Contiene collegamenti ad argomenti che spiegano come cambiare l'aspetto delle applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9f387-124">Contains links to topics that describe how to change the appearance of Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="9f387-125">Panoramica del controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="9f387-125">TabControl Control Overview</span></span>](../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="9f387-126">Spiega come incorporare il controllo Struttura a schede in una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="9f387-126">Explains how you incorporate the tab control into a dialog box.</span></span>
