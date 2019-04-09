---
title: 'Procedura: Designare un pulsante Windows Forms come pulsante di conferma usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: ae7efdce1384b0089b41da155981d1aebbaa55a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201507"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="469a2-102">Procedura: Designare un pulsante Windows Forms come pulsante di conferma usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="469a2-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="469a2-103">In qualsiasi forma di Windows, è possibile designare un <xref:System.Windows.Forms.Button> controllo pulsante di conferma, noto anche come pulsante predefinito.</span><span class="sxs-lookup"><span data-stu-id="469a2-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="469a2-104">Ogni volta che l'utente preme il tasto INVIO, viene scelto il pulsante predefinito indipendentemente da quale altro controllo sul form ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="469a2-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="469a2-105">Le eccezioni a questo si verifica se il controllo con lo stato attivo è un altro pulsante, in tal caso, verrà fatto clic sul pulsante con lo stato attivo, o una casella di testo su più righe o un controllo personalizzato che intercetta il tasto INVIO.</span><span class="sxs-lookup"><span data-stu-id="469a2-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="469a2-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="469a2-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="469a2-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="469a2-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="469a2-108">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="469a2-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="469a2-109">Per designare il pulsante accept</span><span class="sxs-lookup"><span data-stu-id="469a2-109">To designate the accept button</span></span>  
  
1.  <span data-ttu-id="469a2-110">Selezionare il form in cui risiede il pulsante.</span><span class="sxs-lookup"><span data-stu-id="469a2-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="469a2-111">Nel **delle proprietà** finestra, impostare il modulo <xref:System.Windows.Forms.Form.AcceptButton%2A> proprietà per il <xref:System.Windows.Forms.Button> nome del controllo.</span><span class="sxs-lookup"><span data-stu-id="469a2-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="469a2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="469a2-112">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="469a2-113">Panoramica del controllo Button</span><span class="sxs-lookup"><span data-stu-id="469a2-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="469a2-114">Modalità di selezione di un controllo Button Windows Form</span><span class="sxs-lookup"><span data-stu-id="469a2-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="469a2-115">Procedura: Rispondere alla selezione dei pulsanti Windows Forms</span><span class="sxs-lookup"><span data-stu-id="469a2-115">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="469a2-116">Procedura: Designare un pulsante Windows Forms come pulsante di annullamento usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="469a2-116">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [<span data-ttu-id="469a2-117">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="469a2-117">Button Control</span></span>](button-control-windows-forms.md)
