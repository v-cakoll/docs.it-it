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
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a>Procedura: Impostare gli attributi dei caratteri per il controllo RichTextBox Windows Form
Il controllo Windows Forms <xref:System.Windows.Forms.RichTextBox> dispone di numerose opzioni per la formattazione del testo visualizzato. È possibile rendere i caratteri selezionati in grassetto, sottolineato o corsivo usando la proprietà <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>. Questa proprietà può essere usata anche per modificare le dimensioni e il carattere tipografico dei caratteri selezionati. Il <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> proprietà consente di modificare il colore dei caratteri selezionati.  
  
### <a name="to-change-the-appearance-of-characters"></a>Per modificare l'aspetto dei caratteri  
  
1. Impostare la proprietà <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> su un tipo di carattere appropriato.  
  
     Per consentire agli utenti di impostare la famiglia di caratteri, le dimensioni e il carattere tipografico in un'applicazione, si usa in genere il componente <xref:System.Windows.Forms.FontDialog>. Per informazioni generali, vedere [Cenni preliminari sul componente FontDialog](fontdialog-component-overview-windows-forms.md).  
  
2. Impostare la proprietà <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> su un colore appropriato.  
  
     Per consentire agli utenti di impostare il colore in un'applicazione, si usa in genere il componente <xref:System.Windows.Forms.ColorDialog>. Per informazioni generali, vedere [Cenni preliminari sul componente ColorDialog](colordialog-component-overview-windows-forms.md).  
  
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
    > Queste proprietà vengono applicate solo al testo selezionato oppure, se non è stato selezionato alcun testo, al testo digitato nella posizione corrente del punto di inserimento. Per informazioni sulla selezione di testo a livello di codice, vedere <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RichTextBox>
- [Controllo RichTextBox](richtextbox-control-windows-forms.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
