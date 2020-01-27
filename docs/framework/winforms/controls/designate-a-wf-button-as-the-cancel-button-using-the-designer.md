---
title: Designare un pulsante come pulsante Annulla utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: 95d1139b6e339055f944ad0b0967a6d91283d49e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746059"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="a71de-102">Procedura: designare un pulsante Windows Form come pulsante Annulla utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="a71de-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="a71de-103">In qualsiasi Windows Form è possibile designare un controllo <xref:System.Windows.Forms.Button> come pulsante Annulla.</span><span class="sxs-lookup"><span data-stu-id="a71de-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="a71de-104">Quando l'utente preme il tasto ESC, viene fatto clic su un pulsante Annulla, indipendentemente da quale altro controllo nel form abbia lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="a71de-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="a71de-105">Un pulsante di questo tipo è in genere programmato per consentire all'utente di uscire rapidamente da un'operazione senza eseguire il commit in alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="a71de-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>

## <a name="to-designate-the-cancel-button"></a><span data-ttu-id="a71de-106">Per impostare il pulsante Annulla</span><span class="sxs-lookup"><span data-stu-id="a71de-106">To designate the cancel button</span></span>

1. <span data-ttu-id="a71de-107">Selezionare il form in cui si trova il pulsante.</span><span class="sxs-lookup"><span data-stu-id="a71de-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="a71de-108">Nella finestra **Proprietà** impostare la proprietà <xref:System.Windows.Forms.Form.CancelButton%2A> del modulo sul nome del controllo <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="a71de-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="a71de-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a71de-109">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="a71de-110">Panoramica sul controllo Button</span><span class="sxs-lookup"><span data-stu-id="a71de-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="a71de-111">Modalità di selezione di un controllo Button di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a71de-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="a71de-112">Procedura: Rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a71de-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="a71de-113">Procedura: Designare un pulsante Windows Form come pulsante di conferma usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="a71de-113">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [<span data-ttu-id="a71de-114">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="a71de-114">Button Control</span></span>](button-control-windows-forms.md)
