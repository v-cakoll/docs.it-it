---
title: 'Procedura: Impostare il testo visualizzato da un Windows Form mediante la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
ms.openlocfilehash: 4d3f12bd2606e40b5ceeef716d8f5d264bc46622
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707378"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="a646f-102">Procedura: Impostare il testo visualizzato da un Windows Form mediante la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="a646f-102">How to: Set the Text Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="a646f-103">Controlli Windows Form in genere visualizzano il testo è correlato alla funzione principale del controllo.</span><span class="sxs-lookup"><span data-stu-id="a646f-103">Windows Forms controls typically display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="a646f-104">Ad esempio, un <xref:System.Windows.Forms.Button> controllo Visualizza in genere una didascalia indicante l'azione che verrà eseguita quando si fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="a646f-104">For example, a <xref:System.Windows.Forms.Button> control typically displays a caption that indicates what action will be performed when the button is clicked.</span></span> <span data-ttu-id="a646f-105">Per tutti i controlli, il testo può essere impostato o restituito mediante la proprietà <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="a646f-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="a646f-106">È possibile modificare il tipo di carattere usando la proprietà <xref:System.Windows.Forms.Control.Font%2A>.</span><span class="sxs-lookup"><span data-stu-id="a646f-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a><span data-ttu-id="a646f-107">Per impostare il testo e il tipo di carattere con la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="a646f-107">To set the text and font with the designer</span></span>  
  
1.  <span data-ttu-id="a646f-108">Nella finestra Proprietà impostare il <xref:System.Windows.Forms.Control.Text%2A> proprietà del controllo da una stringa appropriata.</span><span class="sxs-lookup"><span data-stu-id="a646f-108">In the Properties window, set the <xref:System.Windows.Forms.Control.Text%2A> property of the control to an appropriate string.</span></span>  
  
     <span data-ttu-id="a646f-109">Per creare un tasto di scelta rapida sottolineato, includere una e commerciale (&) alla lettera che sarà il tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="a646f-109">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>  
  
2.  <span data-ttu-id="a646f-110">Nella finestra Proprietà, fare clic sul pulsante con puntini di sospensione (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.Control.Font%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="a646f-110">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
     <span data-ttu-id="a646f-111">Nella finestra di dialogo tipo di carattere standard, selezionare il tipo di carattere, lo stile del carattere, dimensioni, effetti (ad esempio barrato o carattere di sottolineatura) e script che si desidera.</span><span class="sxs-lookup"><span data-stu-id="a646f-111">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a646f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a646f-112">See also</span></span>
- [<span data-ttu-id="a646f-113">Procedura: Impostare il testo visualizzato dal controllo di un Windows Form</span><span class="sxs-lookup"><span data-stu-id="a646f-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="a646f-114">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="a646f-114">Using Fonts and Text</span></span>](../advanced/using-fonts-and-text.md)
- [<span data-ttu-id="a646f-115">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="a646f-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
