---
title: Modalità di selezione di un controllo Button Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 39696be1286efa68fa70b698ba9623911c90e352
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536328"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="1e258-102">Modalità di selezione di un controllo Button Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e258-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="1e258-103">È possibile selezionare un pulsante Windows Form nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e258-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
-   <span data-ttu-id="1e258-104">Utilizzare il mouse per fare clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="1e258-104">Use a mouse to click the button.</span></span>  
  
-   <span data-ttu-id="1e258-105">Richiamare il pulsante <xref:System.Windows.Forms.Control.Click> evento nel codice.</span><span class="sxs-lookup"><span data-stu-id="1e258-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
-   <span data-ttu-id="1e258-106">Spostare lo stato attivo al pulsante premendo il tasto TAB e quindi scegliere il pulsante, premere la barra spaziatrice o INVIO.</span><span class="sxs-lookup"><span data-stu-id="1e258-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
-   <span data-ttu-id="1e258-107">Premere il tasto di scelta (ALT + lettera sottolineata) per il pulsante.</span><span class="sxs-lookup"><span data-stu-id="1e258-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="1e258-108">Per ulteriori informazioni sulle chiavi di accesso, vedere [procedura: creazione di chiavi per i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="1e258-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
-   <span data-ttu-id="1e258-109">Se il pulsante è il pulsante "accetta" del form, premendo INVIO sceglie il pulsante, anche se un altro controllo ha lo stato attivo, a meno che non sia di altro tipo di controllo è un altro pulsante, una casella di testo multilinea o un controllo personalizzato che intercetta il tasto INVIO.</span><span class="sxs-lookup"><span data-stu-id="1e258-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
-   <span data-ttu-id="1e258-110">Se il pulsante è il pulsante "Annulla" del modulo, premere ESC sceglie il pulsante, anche se un altro controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="1e258-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
-   <span data-ttu-id="1e258-111">Chiamare il <xref:System.Windows.Forms.Button.PerformClick%2A> metodo per selezionare il pulsante a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="1e258-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e258-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e258-112">See Also</span></span>  
 [<span data-ttu-id="1e258-113">Panoramica sul controllo Button</span><span class="sxs-lookup"><span data-stu-id="1e258-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="1e258-114">Procedura: Rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e258-114">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="1e258-115">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="1e258-115">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
