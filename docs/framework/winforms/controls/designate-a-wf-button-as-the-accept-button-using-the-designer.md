---
title: 'Procedura: designare un pulsante Windows Form come pulsante di conferma utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: aade1b6e988fc4b43f7ad9cfb58382302c875d37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527043"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="35433-102">Procedura: designare un pulsante Windows Form come pulsante di conferma utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="35433-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="35433-103">In qualsiasi forma di Windows, è possibile designare un <xref:System.Windows.Forms.Button> controllo pulsante di conferma, noto anche come pulsante predefinito.</span><span class="sxs-lookup"><span data-stu-id="35433-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="35433-104">Ogni volta che l'utente preme il tasto INVIO, viene scelto il pulsante predefinito indipendentemente da quale altro controllo nel form ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="35433-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="35433-105">Le eccezioni si verifica se il controllo con lo stato attivo è un altro pulsante, in tal caso, verrà fatto clic sul pulsante con lo stato attivo, o una casella di testo o un controllo personalizzato che intercetta il tasto INVIO.</span><span class="sxs-lookup"><span data-stu-id="35433-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35433-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="35433-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="35433-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="35433-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="35433-108">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="35433-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="35433-109">Per designare il pulsante di conferma</span><span class="sxs-lookup"><span data-stu-id="35433-109">To designate the accept button</span></span>  
  
1.  <span data-ttu-id="35433-110">Selezionare il form in cui risiede il pulsante.</span><span class="sxs-lookup"><span data-stu-id="35433-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="35433-111">Nel **proprietà** finestra, imposta la proprietà <xref:System.Windows.Forms.Form.AcceptButton%2A> proprietà per il <xref:System.Windows.Forms.Button> nome del controllo.</span><span class="sxs-lookup"><span data-stu-id="35433-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35433-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35433-112">See Also</span></span>  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [<span data-ttu-id="35433-113">Panoramica sul controllo Button</span><span class="sxs-lookup"><span data-stu-id="35433-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="35433-114">Modalità di selezione di un controllo Button di Windows Form</span><span class="sxs-lookup"><span data-stu-id="35433-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="35433-115">Procedura: Rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="35433-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="35433-116">Procedura: Designare un pulsante Windows Form come pulsante Annulla usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="35433-116">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [<span data-ttu-id="35433-117">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="35433-117">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
