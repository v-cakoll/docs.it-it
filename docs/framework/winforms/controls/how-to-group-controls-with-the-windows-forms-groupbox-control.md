---
title: 'Procedura: raggruppare i controlli tramite il controllo GroupBox di Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 50d29de04b4e221105bb02e58de01344f13af69f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="22ca4-102">Procedura: raggruppare i controlli tramite il controllo GroupBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="22ca4-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="22ca4-103">Windows Form <xref:System.Windows.Forms.GroupBox> controlli vengono utilizzati per raggruppare altri controlli.</span><span class="sxs-lookup"><span data-stu-id="22ca4-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="22ca4-104">Vi sono tre motivi per i controlli di gruppo:</span><span class="sxs-lookup"><span data-stu-id="22ca4-104">There are three reasons to group controls:</span></span>  
  
-   <span data-ttu-id="22ca4-105">Per creare un raggruppamento visivo di elementi di form per un'interfaccia utente crittografato.</span><span class="sxs-lookup"><span data-stu-id="22ca4-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
-   <span data-ttu-id="22ca4-106">Per creare un gruppo a livello di codice (di pulsanti di opzione, ad esempio).</span><span class="sxs-lookup"><span data-stu-id="22ca4-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
-   <span data-ttu-id="22ca4-107">Per spostare i controlli in un'unità in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="22ca4-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="22ca4-108">Per creare un gruppo di controlli</span><span class="sxs-lookup"><span data-stu-id="22ca4-108">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="22ca4-109">Disegnare un <xref:System.Windows.Forms.GroupBox> controllo in un form.</span><span class="sxs-lookup"><span data-stu-id="22ca4-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="22ca4-110">Aggiungere altri controlli casella di gruppo, creando ciascun all'interno della casella di gruppo.</span><span class="sxs-lookup"><span data-stu-id="22ca4-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="22ca4-111">Se si dispone di controlli esistenti che si desidera inserire in una casella di gruppo, è possibile selezionare tutti i controlli, li tagliare negli Appunti, selezionare il <xref:System.Windows.Forms.GroupBox> controllare e incollarlo nella casella di gruppo.</span><span class="sxs-lookup"><span data-stu-id="22ca4-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="22ca4-112">È anche possibile trascinare i controlli nella casella di gruppo.</span><span class="sxs-lookup"><span data-stu-id="22ca4-112">You can also drag them into the group box.</span></span>  
  
3.  <span data-ttu-id="22ca4-113">Impostare il <xref:System.Windows.Forms.GroupBox.Text%2A> proprietà della casella di gruppo per una didascalia appropriata.</span><span class="sxs-lookup"><span data-stu-id="22ca4-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ca4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22ca4-114">See Also</span></span>  
 <xref:System.Windows.Forms.GroupBox>  
 [<span data-ttu-id="22ca4-115">Controllo GroupBox</span><span class="sxs-lookup"><span data-stu-id="22ca4-115">GroupBox Control</span></span>](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)
