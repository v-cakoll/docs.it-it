---
title: Designare un pulsante come pulsante accetta utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 27a5de51f8c5b2c84cc205e09ac1a2179c315752
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746071"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="3bdeb-102">Procedura: designare un pulsante Windows Form come pulsante di conferma utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="3bdeb-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="3bdeb-103">In qualsiasi Windows Form è possibile designare un controllo <xref:System.Windows.Forms.Button> come pulsante accetta, noto anche come pulsante predefinito.</span><span class="sxs-lookup"><span data-stu-id="3bdeb-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="3bdeb-104">Ogni volta che l'utente preme il tasto invio, viene fatto clic sul pulsante predefinito, indipendentemente da quale altro controllo nel form abbia lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="3bdeb-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="3bdeb-105">Le eccezioni a questo si verificano quando il controllo con lo stato attivo è un altro pulsante, in tal caso verrà fatto clic sul pulsante con lo stato attivo o su una casella di testo a più righe o un controllo personalizzato che intrappola il tasto INVIO.</span><span class="sxs-lookup"><span data-stu-id="3bdeb-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>

## <a name="to-designate-the-accept-button"></a><span data-ttu-id="3bdeb-106">Per impostare il pulsante accetta</span><span class="sxs-lookup"><span data-stu-id="3bdeb-106">To designate the accept button</span></span>

1. <span data-ttu-id="3bdeb-107">Selezionare il form in cui si trova il pulsante.</span><span class="sxs-lookup"><span data-stu-id="3bdeb-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="3bdeb-108">Nella finestra **Proprietà** impostare la proprietà <xref:System.Windows.Forms.Form.AcceptButton%2A> del modulo sul nome del controllo <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="3bdeb-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="3bdeb-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bdeb-109">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="3bdeb-110">Panoramica sul controllo Button</span><span class="sxs-lookup"><span data-stu-id="3bdeb-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="3bdeb-111">Modalità di selezione di un controllo Button di Windows Form</span><span class="sxs-lookup"><span data-stu-id="3bdeb-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="3bdeb-112">Procedura: Rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="3bdeb-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="3bdeb-113">Procedura: Designare un pulsante Windows Form come pulsante Annulla usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="3bdeb-113">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [<span data-ttu-id="3bdeb-114">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="3bdeb-114">Button Control</span></span>](button-control-windows-forms.md)
