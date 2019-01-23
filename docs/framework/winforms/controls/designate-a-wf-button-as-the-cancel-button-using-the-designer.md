---
title: 'Procedura: Designare un pulsante di Windows Form come pulsante Annulla usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: 9d11528d7d7fed13f531faeb09f38c4564f970be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520477"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="899a5-102">Procedura: Designare un pulsante di Windows Form come pulsante Annulla usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="899a5-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="899a5-103">In qualsiasi forma di Windows, è possibile designare un <xref:System.Windows.Forms.Button> controllo pulsante di annullamento.</span><span class="sxs-lookup"><span data-stu-id="899a5-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="899a5-104">Ogni volta che l'utente preme il tasto ESC, indipendentemente da quale altro controllo sul form ha lo stato attivo, viene scelto un pulsante Annulla.</span><span class="sxs-lookup"><span data-stu-id="899a5-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="899a5-105">Il pulsante di annullamento viene in genere programmate per consentire all'utente di abbandonare un'operazione senza il commit di alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="899a5-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="899a5-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="899a5-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="899a5-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="899a5-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="899a5-108">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="899a5-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="899a5-109">Per designare il pulsante Annulla</span><span class="sxs-lookup"><span data-stu-id="899a5-109">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="899a5-110">Selezionare il form in cui risiede il pulsante.</span><span class="sxs-lookup"><span data-stu-id="899a5-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="899a5-111">Nel **delle proprietà** finestra, impostare il modulo <xref:System.Windows.Forms.Form.CancelButton%2A> proprietà per il <xref:System.Windows.Forms.Button> nome del controllo.</span><span class="sxs-lookup"><span data-stu-id="899a5-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="899a5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="899a5-112">See also</span></span>
- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="899a5-113">Panoramica sul controllo Button</span><span class="sxs-lookup"><span data-stu-id="899a5-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [<span data-ttu-id="899a5-114">Modalità di selezione di un controllo Button di Windows Form</span><span class="sxs-lookup"><span data-stu-id="899a5-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="899a5-115">Procedura: Rispondere alle selezioni dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="899a5-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="899a5-116">Procedura: Designare un pulsante di Windows Form come pulsante di conferma usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="899a5-116">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [<span data-ttu-id="899a5-117">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="899a5-117">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
