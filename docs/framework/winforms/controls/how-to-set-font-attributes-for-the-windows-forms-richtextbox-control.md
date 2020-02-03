---
title: Impostare gli attributi del tipo di carattere per il controllo RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- .rtf files [Windows Forms], formatting in RichTextBox control
- fonts [Windows Forms], changing attributes in RichTextBox control
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting font attributes
- text [Windows Forms]
- text boxes [Windows Forms], formatting text
- formatting [Windows Forms]
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
ms.openlocfilehash: f27256c155223df576ee3c42e6bf65270c870b0f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744856"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a><span data-ttu-id="058a0-102">Procedura: Impostare gli attributi dei caratteri per il controllo RichTextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="058a0-102">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="058a0-103">Il controllo Windows Forms <xref:System.Windows.Forms.RichTextBox> dispone di numerose opzioni per la formattazione del testo visualizzato.</span><span class="sxs-lookup"><span data-stu-id="058a0-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="058a0-104">È possibile rendere i caratteri selezionati in grassetto, sottolineato o corsivo usando la proprietà <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>.</span><span class="sxs-lookup"><span data-stu-id="058a0-104">You can make the selected characters bold, underlined, or italic, using the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property.</span></span> <span data-ttu-id="058a0-105">Questa proprietà può essere usata anche per modificare le dimensioni e il carattere tipografico dei caratteri selezionati.</span><span class="sxs-lookup"><span data-stu-id="058a0-105">You can also use this property to change the size and typeface of the selected characters.</span></span> <span data-ttu-id="058a0-106">Il <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> proprietà consente di modificare il colore dei caratteri selezionati.</span><span class="sxs-lookup"><span data-stu-id="058a0-106">The <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property enables you to change the selected characters' color.</span></span>  
  
### <a name="to-change-the-appearance-of-characters"></a><span data-ttu-id="058a0-107">Per modificare l'aspetto dei caratteri</span><span class="sxs-lookup"><span data-stu-id="058a0-107">To change the appearance of characters</span></span>  
  
1. <span data-ttu-id="058a0-108">Impostare la proprietà <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> su un tipo di carattere appropriato.</span><span class="sxs-lookup"><span data-stu-id="058a0-108">Set the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property to an appropriate font.</span></span>  
  
     <span data-ttu-id="058a0-109">Per consentire agli utenti di impostare la famiglia di caratteri, le dimensioni e il carattere tipografico in un'applicazione, si usa in genere il componente <xref:System.Windows.Forms.FontDialog>.</span><span class="sxs-lookup"><span data-stu-id="058a0-109">To enable users to set the font family, size, and typeface in an application, you would typically use the <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="058a0-110">Per informazioni generali, vedere [Cenni preliminari sul componente FontDialog](fontdialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="058a0-110">For an overview, see [FontDialog Component Overview](fontdialog-component-overview-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="058a0-111">Impostare la proprietà <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> su un colore appropriato.</span><span class="sxs-lookup"><span data-stu-id="058a0-111">Set the <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property to an appropriate color.</span></span>  
  
     <span data-ttu-id="058a0-112">Per consentire agli utenti di impostare il colore in un'applicazione, si usa in genere il componente <xref:System.Windows.Forms.ColorDialog>.</span><span class="sxs-lookup"><span data-stu-id="058a0-112">To enable users to set the color in an application, you would typically use the <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="058a0-113">Per informazioni generali, vedere [Cenni preliminari sul componente ColorDialog](colordialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="058a0-113">For an overview, see [ColorDialog Component Overview](colordialog-component-overview-windows-forms.md).</span></span>  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="058a0-114">Queste proprietà vengono applicate solo al testo selezionato oppure, se non è stato selezionato alcun testo, al testo digitato nella posizione corrente del punto di inserimento.</span><span class="sxs-lookup"><span data-stu-id="058a0-114">These properties only affect selected text, or, if no text is selected, the text that is typed at the current location of the insertion point.</span></span> <span data-ttu-id="058a0-115">Per informazioni sulla selezione di testo a livello di codice, vedere <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="058a0-115">For information on selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="058a0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="058a0-116">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="058a0-117">Controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="058a0-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="058a0-118">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="058a0-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
