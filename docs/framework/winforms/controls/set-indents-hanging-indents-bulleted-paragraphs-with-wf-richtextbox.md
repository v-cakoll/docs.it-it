---
title: 'Procedura: Impostare rientri, rientri sporgenti e paragrafi puntati con il controllo RichTextBox di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
ms.openlocfilehash: ad5dd1cc3839fbe29d39f6ab38b0e865e7b0a335
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492423"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="a13c4-102">Procedura: Impostare rientri, rientri sporgenti e paragrafi puntati con il controllo RichTextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a13c4-102">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="a13c4-103">I moduli di Windows <xref:System.Windows.Forms.RichTextBox> controllo è disponibili numerose opzioni per la formattazione del testo visualizzato.</span><span class="sxs-lookup"><span data-stu-id="a13c4-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="a13c4-104">È possibile formattare i paragrafi selezionati come elenchi puntati impostando il <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="a13c4-104">You can format selected paragraphs as bulleted lists by setting the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="a13c4-105">È anche possibile usare la <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, e <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> proprietà per impostare il rientro dei paragrafi rispetto a sinistra e bordi a destra del controllo e il bordo sinistro di altre righe di testo.</span><span class="sxs-lookup"><span data-stu-id="a13c4-105">You can also use the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, and <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> properties to set the indentation of paragraphs relative to the left and right edges of the control, and the left edge of other lines of text.</span></span>  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a><span data-ttu-id="a13c4-106">Per formattare un paragrafo come elenco puntato</span><span class="sxs-lookup"><span data-stu-id="a13c4-106">To format a paragraph as a bulleted list</span></span>  
  
1.  <span data-ttu-id="a13c4-107">Impostare la proprietà <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="a13c4-107">Set the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property to `true`.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a><span data-ttu-id="a13c4-108">Per impostare il rientro di un paragrafo</span><span class="sxs-lookup"><span data-stu-id="a13c4-108">To indent a paragraph</span></span>  
  
1.  <span data-ttu-id="a13c4-109">Impostare il <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> proprietà in un intero che rappresenta la distanza in pixel tra il bordo sinistro del controllo e il bordo sinistro del testo.</span><span class="sxs-lookup"><span data-stu-id="a13c4-109">Set the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> property to an integer representing the distance in pixels between the left edge of the control and the left edge of the text.</span></span>  
  
2.  <span data-ttu-id="a13c4-110">Impostare il <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> proprietà in un intero che rappresenta la distanza in pixel tra il bordo sinistro della prima riga del testo nel paragrafo e il bordo sinistro delle righe successive nello stesso paragrafo.</span><span class="sxs-lookup"><span data-stu-id="a13c4-110">Set the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property to an integer representing the distance in pixels between the left edge of the first line of text in the paragraph and the left edge of subsequent lines in the same paragraph.</span></span> <span data-ttu-id="a13c4-111">Il valore della <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> proprietà si applica solo alle righe in un paragrafo che sono stato eseguito il wrapping sotto la prima riga.</span><span class="sxs-lookup"><span data-stu-id="a13c4-111">The value of the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property only applies to lines in a paragraph that have wrapped below the first line.</span></span>  
  
3.  <span data-ttu-id="a13c4-112">Impostare il <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> proprietà in un intero che rappresenta la distanza in pixel tra il bordo destro del controllo e il bordo destro del testo.</span><span class="sxs-lookup"><span data-stu-id="a13c4-112">Set the <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> property to an integer representing the distance in pixels between the right edge of the control and the right edge of the text.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="a13c4-113">Tutte queste proprietà vengono applicate a qualsiasi paragrafo contenente il testo selezionato, oltre che al testo digitato dopo il punto di inserimento corrente.</span><span class="sxs-lookup"><span data-stu-id="a13c4-113">All these properties affect any paragraphs that contain selected text, and also the text that is typed after the current insertion point.</span></span> <span data-ttu-id="a13c4-114">Ad esempio, quando un utente seleziona una parola all'interno di un paragrafo e ne regola il rientro, le nuove impostazioni verranno applicate all'intero paragrafo contenente tale parola, nonché agli eventuali paragrafi immessi successivamente dopo il paragrafo selezionato.</span><span class="sxs-lookup"><span data-stu-id="a13c4-114">For example, when a user selects a word within a paragraph and then adjusts the indentation, the new settings will apply to the entire paragraph that contains that word, and also to any paragraphs subsequently entered after the selected paragraph.</span></span> <span data-ttu-id="a13c4-115">Per informazioni sulla selezione di testo a livello di codice, vedere <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="a13c4-115">For information about selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13c4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a13c4-116">See also</span></span>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="a13c4-117">Controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a13c4-117">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)
- [<span data-ttu-id="a13c4-118">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="a13c4-118">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
