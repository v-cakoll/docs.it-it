---
title: 'Procedura: Impostare gli attributi dei caratteri per il controllo RichTextBox Windows Form'
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
ms.openlocfilehash: 7c4c9362bb5a32bd8d5afc2b1edeb935d505fd19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a>Procedura: Impostare gli attributi dei caratteri per il controllo RichTextBox Windows Form
Windows Form <xref:System.Windows.Forms.RichTextBox> controllo è disponibili numerose opzioni per la formattazione del testo visualizzato. È possibile apportare i caratteri selezionati in grassetto, corsivo o sottolineato utilizzando il <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> proprietà. Questa proprietà può essere usata anche per modificare le dimensioni e il carattere tipografico dei caratteri selezionati. Il <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> proprietà consente di modificare il colore dei caratteri selezionati.  
  
### <a name="to-change-the-appearance-of-characters"></a>Per modificare l'aspetto dei caratteri  
  
1.  Impostare il <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> proprietà per un tipo di carattere appropriato.  
  
     Per consentire agli utenti di impostare la famiglia di caratteri, dimensioni e tipo di carattere in un'applicazione, in genere viene utilizzata la <xref:System.Windows.Forms.FontDialog> componente. Per informazioni generali, vedere [Cenni preliminari sul componente FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md).  
  
2.  Impostare il <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> proprietà su un colore appropriato.  
  
     Per consentire agli utenti di impostare il colore in un'applicazione, in genere viene utilizzata la <xref:System.Windows.Forms.ColorDialog> componente. Per informazioni generali, vedere [Cenni preliminari sul componente ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md).  
  
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
    >  Queste proprietà vengono applicate solo al testo selezionato oppure, se non è stato selezionato alcun testo, al testo digitato nella posizione corrente del punto di inserimento. Per informazioni sulla selezione di testo a livello di codice, vedere <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.RichTextBox>  
 [Controllo RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
