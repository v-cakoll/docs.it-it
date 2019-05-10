---
title: Modalità di selezione di un controllo Button Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: e511b0d7bcac725ed477678ab4c865f5337e658d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64584950"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="5f9a7-102">Modalità di selezione di un controllo Button Windows Form</span><span class="sxs-lookup"><span data-stu-id="5f9a7-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="5f9a7-103">È possibile selezionare un pulsante Windows Form nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f9a7-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
- <span data-ttu-id="5f9a7-104">Consente di fare clic sul pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="5f9a7-104">Use a mouse to click the button.</span></span>  
  
- <span data-ttu-id="5f9a7-105">Richiamo del pulsante <xref:System.Windows.Forms.Control.Click> evento nel codice.</span><span class="sxs-lookup"><span data-stu-id="5f9a7-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
- <span data-ttu-id="5f9a7-106">Spostare lo stato attivo al pulsante premendo il tasto TAB e quindi scegliere il pulsante premendo la barra spaziatrice o INVIO.</span><span class="sxs-lookup"><span data-stu-id="5f9a7-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
- <span data-ttu-id="5f9a7-107">Premere il tasto di scelta (ALT + lettera sottolineata) per il pulsante.</span><span class="sxs-lookup"><span data-stu-id="5f9a7-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="5f9a7-108">Per altre informazioni sulle chiavi di accesso, vedere [come: Creare le chiavi di accesso per i controlli di Windows Form](how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="5f9a7-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
- <span data-ttu-id="5f9a7-109">Se il pulsante è il pulsante "accept" del form, premendo INVIO sceglie il pulsante, anche se un altro controllo ha lo stato attivo, a meno che quest ' è un altro pulsante, una casella di testo su più righe o un controllo personalizzato che intercetta il tasto INVIO.</span><span class="sxs-lookup"><span data-stu-id="5f9a7-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
- <span data-ttu-id="5f9a7-110">Se il pulsante è il pulsante "Annulla" del form, il tasto ESC sceglie il pulsante, anche se un altro controllo ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="5f9a7-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
- <span data-ttu-id="5f9a7-111">Chiamare il <xref:System.Windows.Forms.Button.PerformClick%2A> metodo per selezionare il pulsante a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="5f9a7-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f9a7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f9a7-112">See also</span></span>

- [<span data-ttu-id="5f9a7-113">Panoramica sul controllo Button</span><span class="sxs-lookup"><span data-stu-id="5f9a7-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="5f9a7-114">Procedura: Rispondere alle selezioni dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5f9a7-114">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="5f9a7-115">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="5f9a7-115">Button Control</span></span>](button-control-windows-forms.md)
