---
title: 'Procedura: impostare il testo visualizzato da un controllo Windows Form utilizzando la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], setting caption
- Windows Forms, setting the text displayed
ms.assetid: 9d18e0e0-f17f-4074-837d-e67ceeeaa89d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b6d49466e5dd25bbe9e97262d68f2c3fb2f8ba1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer"></a><span data-ttu-id="446c7-102">Procedura: impostare il testo visualizzato da un controllo Windows Form utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="446c7-102">How to: Set the Text Displayed by a Windows Forms Control Using the Designer</span></span>
<span data-ttu-id="446c7-103">Controlli Windows Form in genere visualizzano il testo che è correlato alla funzione principale del controllo.</span><span class="sxs-lookup"><span data-stu-id="446c7-103">Windows Forms controls typically display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="446c7-104">Ad esempio, un <xref:System.Windows.Forms.Button> controllo Visualizza in genere una didascalia indicante l'azione da eseguire quando si fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="446c7-104">For example, a <xref:System.Windows.Forms.Button> control typically displays a caption that indicates what action will be performed when the button is clicked.</span></span> <span data-ttu-id="446c7-105">Per tutti i controlli, il testo può essere impostato o restituito mediante la proprietà <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="446c7-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="446c7-106">È possibile modificare il tipo di carattere usando la proprietà <xref:System.Windows.Forms.Control.Font%2A>.</span><span class="sxs-lookup"><span data-stu-id="446c7-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
### <a name="to-set-the-text-and-font-with-the-designer"></a><span data-ttu-id="446c7-107">Per impostare il testo e il tipo di carattere con la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="446c7-107">To set the text and font with the designer</span></span>  
  
1.  <span data-ttu-id="446c7-108">Nella finestra Proprietà impostare la <xref:System.Windows.Forms.Control.Text%2A> proprietà del controllo su una stringa appropriata.</span><span class="sxs-lookup"><span data-stu-id="446c7-108">In the Properties window, set the <xref:System.Windows.Forms.Control.Text%2A> property of the control to an appropriate string.</span></span>  
  
     <span data-ttu-id="446c7-109">Per creare un tasto di scelta rapida sottolineato, includere una e commerciale (&) prima della lettera che sarà il tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="446c7-109">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>  
  
2.  <span data-ttu-id="446c7-110">Nella finestra Proprietà fare clic sul pulsante con puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.Control.Font%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="446c7-110">In the Properties window, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>  
  
     <span data-ttu-id="446c7-111">Selezionare il tipo di carattere, lo stile del carattere, dimensioni, effetti (ad esempio barrato o sottolineato) e script che si desidera, nella finestra di dialogo tipo di carattere standard.</span><span class="sxs-lookup"><span data-stu-id="446c7-111">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="446c7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="446c7-112">See Also</span></span>  
 [<span data-ttu-id="446c7-113">Procedura: Impostare il testo visualizzato da un controllo Windows Form</span><span class="sxs-lookup"><span data-stu-id="446c7-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="446c7-114">Uso di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="446c7-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="446c7-115">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="446c7-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
