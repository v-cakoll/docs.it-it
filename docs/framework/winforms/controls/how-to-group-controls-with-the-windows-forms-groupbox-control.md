---
title: Controlli di gruppo con il controllo GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: bb7476c410d2802b5d32cc9842a778f290765e32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736659"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="84514-102">Procedura: raggruppare i controlli tramite il controllo GroupBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="84514-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="84514-103">Per raggruppare altri controlli, vengono usati Windows Forms controlli <xref:System.Windows.Forms.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="84514-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="84514-104">Esistono tre motivi per raggruppare i controlli:</span><span class="sxs-lookup"><span data-stu-id="84514-104">There are three reasons to group controls:</span></span>  
  
- <span data-ttu-id="84514-105">Per creare un raggruppamento visivo di elementi del form correlati per un'interfaccia utente chiara.</span><span class="sxs-lookup"><span data-stu-id="84514-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
- <span data-ttu-id="84514-106">Per creare un raggruppamento programmatico (ad esempio, di pulsanti di opzione).</span><span class="sxs-lookup"><span data-stu-id="84514-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
- <span data-ttu-id="84514-107">Per lo sviluppo di controlli come unità in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="84514-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="84514-108">Per creare un gruppo di controlli</span><span class="sxs-lookup"><span data-stu-id="84514-108">To create a group of controls</span></span>  
  
1. <span data-ttu-id="84514-109">Creare un controllo <xref:System.Windows.Forms.GroupBox> in un form.</span><span class="sxs-lookup"><span data-stu-id="84514-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="84514-110">Aggiungere altri controlli alla casella di gruppo, disegnando ognuno all'interno della casella di gruppo.</span><span class="sxs-lookup"><span data-stu-id="84514-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="84514-111">Se si dispone di controlli esistenti che si desidera racchiudere in una casella di gruppo, è possibile selezionare tutti i controlli, tagliarli negli Appunti, selezionare il controllo <xref:System.Windows.Forms.GroupBox> e quindi incollarli nella casella di gruppo.</span><span class="sxs-lookup"><span data-stu-id="84514-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="84514-112">È anche possibile trascinarli nella casella di gruppo.</span><span class="sxs-lookup"><span data-stu-id="84514-112">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="84514-113">Impostare la proprietà <xref:System.Windows.Forms.GroupBox.Text%2A> della casella di gruppo su una didascalia appropriata.</span><span class="sxs-lookup"><span data-stu-id="84514-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84514-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84514-114">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="84514-115">Controllo GroupBox</span><span class="sxs-lookup"><span data-stu-id="84514-115">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
