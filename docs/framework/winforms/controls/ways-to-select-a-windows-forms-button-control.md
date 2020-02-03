---
title: Modalità di selezione di un controllo Button
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 145166d182f1ec51068ab3e0c23c12b471b69231
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740011"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="556a0-102">Modalità di selezione di un controllo Button Windows Form</span><span class="sxs-lookup"><span data-stu-id="556a0-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="556a0-103">È possibile selezionare un pulsante Windows Forms nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="556a0-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
- <span data-ttu-id="556a0-104">Utilizzare un mouse per fare clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="556a0-104">Use a mouse to click the button.</span></span>  
  
- <span data-ttu-id="556a0-105">Richiama l'evento <xref:System.Windows.Forms.Control.Click> del pulsante nel codice.</span><span class="sxs-lookup"><span data-stu-id="556a0-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
- <span data-ttu-id="556a0-106">Spostare lo stato attivo sul pulsante premendo il tasto TAB, quindi scegliere il pulsante premendo la barra SPAZIAtrice o invio.</span><span class="sxs-lookup"><span data-stu-id="556a0-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
- <span data-ttu-id="556a0-107">Premere il tasto di accesso (ALT + la lettera sottolineata) per il pulsante.</span><span class="sxs-lookup"><span data-stu-id="556a0-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="556a0-108">Per altre informazioni sulle chiavi di accesso, vedere [procedura: creare chiavi di accesso per controlli Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="556a0-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
- <span data-ttu-id="556a0-109">Se il pulsante è il pulsante "Accetto" del modulo, premendo invio viene scelto il pulsante, anche se un altro controllo ha lo stato attivo, ad eccezione del fatto che un altro controllo è un altro pulsante, una casella di testo a più righe o un controllo personalizzato che intrappola il tasto INVIO.</span><span class="sxs-lookup"><span data-stu-id="556a0-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
- <span data-ttu-id="556a0-110">Se il pulsante è il pulsante "Annulla" del modulo, premendo ESC viene scelto il pulsante anche se un altro controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="556a0-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
- <span data-ttu-id="556a0-111">Chiamare il metodo <xref:System.Windows.Forms.Button.PerformClick%2A> per selezionare il pulsante a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="556a0-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="556a0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="556a0-112">See also</span></span>

- [<span data-ttu-id="556a0-113">Panoramica sul controllo Button</span><span class="sxs-lookup"><span data-stu-id="556a0-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="556a0-114">Procedura: Rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="556a0-114">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="556a0-115">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="556a0-115">Button Control</span></span>](button-control-windows-forms.md)
