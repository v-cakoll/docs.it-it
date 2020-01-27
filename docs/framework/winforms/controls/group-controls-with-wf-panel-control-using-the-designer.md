---
title: Raggruppare i controlli con il controllo Panel usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 927aeb5b51bc1ac4e22a45e487b49424b4e67b71
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745647"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="da70f-102">Procedura: raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="da70f-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="da70f-103">Per raggruppare altri controlli, vengono usati Windows Forms controlli <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="da70f-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="da70f-104">Esistono tre motivi per raggruppare i controlli.</span><span class="sxs-lookup"><span data-stu-id="da70f-104">There are three reasons to group controls.</span></span> <span data-ttu-id="da70f-105">Uno è il raggruppamento visivo di elementi del form correlati per un'interfaccia utente chiara; un altro è il raggruppamento programmatico di pulsanti di opzione, ad esempio. l'ultimo consiste nello trasferire i controlli come unità in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="da70f-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>

## <a name="to-create-a-group-of-controls"></a><span data-ttu-id="da70f-106">Per creare un gruppo di controlli</span><span class="sxs-lookup"><span data-stu-id="da70f-106">To create a group of controls</span></span>

1. <span data-ttu-id="da70f-107">Trascinare un controllo <xref:System.Windows.Forms.Panel> dalla scheda **Windows Forms** della casella degli strumenti in un form.</span><span class="sxs-lookup"><span data-stu-id="da70f-107">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>

2. <span data-ttu-id="da70f-108">Aggiungere altri controlli al pannello, disegnando ognuno all'interno del pannello.</span><span class="sxs-lookup"><span data-stu-id="da70f-108">Add other controls to the panel, drawing each inside the panel.</span></span>

     <span data-ttu-id="da70f-109">Se si dispone di controlli esistenti che si desidera includere in un pannello, è possibile selezionare tutti i controlli, tagliarli negli Appunti, selezionare il controllo <xref:System.Windows.Forms.Panel> e quindi incollarli nel pannello.</span><span class="sxs-lookup"><span data-stu-id="da70f-109">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="da70f-110">È anche possibile trascinarli nel pannello.</span><span class="sxs-lookup"><span data-stu-id="da70f-110">You can also drag them into the panel.</span></span>

3. <span data-ttu-id="da70f-111">Opzionale Se si desidera aggiungere un bordo a un pannello, impostarne la proprietà <xref:System.Windows.Forms.BorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="da70f-111">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="da70f-112">Sono disponibili tre opzioni: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>e <xref:System.Windows.Forms.BorderStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="da70f-112">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>

## <a name="see-also"></a><span data-ttu-id="da70f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da70f-113">See also</span></span>

- [<span data-ttu-id="da70f-114">Controllo Panel</span><span class="sxs-lookup"><span data-stu-id="da70f-114">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="da70f-115">Panoramica sul controllo Panel</span><span class="sxs-lookup"><span data-stu-id="da70f-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="da70f-116">Procedura: Impostare lo sfondo di un controllo Panel</span><span class="sxs-lookup"><span data-stu-id="da70f-116">How to: Set the Background of a Panel</span></span>](how-to-set-the-background-of-a-windows-forms-panel.md)
