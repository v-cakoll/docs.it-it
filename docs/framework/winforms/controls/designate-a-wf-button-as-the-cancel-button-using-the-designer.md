---
title: 'Procedura: designare un pulsante Windows Form come pulsante Annulla utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: faffeafc0cbe67c3b40297144ec85acd94956da9
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44080826"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="fe43b-102">Procedura: designare un pulsante Windows Form come pulsante Annulla utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="fe43b-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="fe43b-103">In qualsiasi forma di Windows, è possibile designare un <xref:System.Windows.Forms.Button> controllo pulsante di annullamento.</span><span class="sxs-lookup"><span data-stu-id="fe43b-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="fe43b-104">Ogni volta che l'utente preme il tasto ESC, indipendentemente da quale altro controllo sul form ha lo stato attivo, viene scelto un pulsante Annulla.</span><span class="sxs-lookup"><span data-stu-id="fe43b-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="fe43b-105">Il pulsante di annullamento viene in genere programmate per consentire all'utente di abbandonare un'operazione senza il commit di alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="fe43b-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe43b-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="fe43b-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fe43b-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="fe43b-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fe43b-108">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="fe43b-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="fe43b-109">Per designare il pulsante Annulla</span><span class="sxs-lookup"><span data-stu-id="fe43b-109">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="fe43b-110">Selezionare il form in cui risiede il pulsante.</span><span class="sxs-lookup"><span data-stu-id="fe43b-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="fe43b-111">Nel **delle proprietà** finestra, impostare il modulo <xref:System.Windows.Forms.Form.CancelButton%2A> proprietà per il <xref:System.Windows.Forms.Button> nome del controllo.</span><span class="sxs-lookup"><span data-stu-id="fe43b-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe43b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe43b-112">See Also</span></span>  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [<span data-ttu-id="fe43b-113">Panoramica sul controllo Button</span><span class="sxs-lookup"><span data-stu-id="fe43b-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="fe43b-114">Modalità di selezione di un controllo Button di Windows Form</span><span class="sxs-lookup"><span data-stu-id="fe43b-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="fe43b-115">Procedura: Rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="fe43b-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="fe43b-116">Procedura: Designare un pulsante Windows Form come pulsante di conferma usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="fe43b-116">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [<span data-ttu-id="fe43b-117">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="fe43b-117">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
