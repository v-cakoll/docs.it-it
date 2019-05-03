---
title: Cenni preliminari sul controllo RichTextBox (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
ms.openlocfilehash: 0827c1919597e9eb85bfa41721676008b76564d9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902499"
---
# <a name="richtextbox-control-overview-windows-forms"></a>Cenni preliminari sul controllo RichTextBox (Windows Form)
I moduli di Windows <xref:System.Windows.Forms.RichTextBox> controllo viene usato per visualizzare, immettere e modificare testo formattato. Il <xref:System.Windows.Forms.RichTextBox> offerte dal controllo di <xref:System.Windows.Forms.TextBox> del controllo, ma può anche visualizzare i tipi di carattere, colori e collegamenti, caricare testo e immagini incorporate da un file; e trovare caratteri specificati. Il <xref:System.Windows.Forms.RichTextBox> controllo viene in genere usato per fornire funzionalità simili alle applicazioni di elaborazione di testi, ad esempio Microsoft Word di visualizzazione e modifica di testo. Ad esempio la <xref:System.Windows.Forms.TextBox> (controllo), il <xref:System.Windows.Forms.RichTextBox> controllo può visualizzare le barre di scorrimento; ma a differenza di <xref:System.Windows.Forms.TextBox> (controllo), l'impostazione predefinita per visualizzare le barre di scorrimento orizzontale e verticale in base alle esigenze, e ha impostazioni aggiuntive.  
  
## <a name="working-with-the-richtextbox-control"></a>Utilizzo del controllo RichTextBox  
 Come con le <xref:System.Windows.Forms.TextBox> (controllo), il testo visualizzato è impostato il <xref:System.Windows.Forms.RichTextBox.Text%2A> proprietà. Il <xref:System.Windows.Forms.RichTextBox> controllo ha numerose proprietà per la formattazione del testo. Per informazioni dettagliate su queste proprietà, vedere [come: Impostare gli attributi dei caratteri per il Windows Form controllo RichTextBox](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) e [come: Impostare rientri, rientri sporgenti e paragrafi puntati con il controllo RichTextBox di Windows Form](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md). Modificare i file, il <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> e <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> metodi possono visualizzare e scrivere più formati di file, inclusi testo normale, testo normale Unicode e RTF (RICH Text Format). I formati di file possibili sono elencati <xref:System.Windows.Forms.RichTextBoxStreamType>. È possibile usare il <xref:System.Windows.Forms.RichTextBox.Find%2A> metodo per trovare le stringhe di testo o caratteri specifici.  
  
 È anche possibile usare una <xref:System.Windows.Forms.RichTextBox> controllo per i collegamenti ipertestuali, impostando il <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> proprietà `true` e la scrittura di codice per gestire il <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento. Per altre informazioni, vedere [Procedura: Controllo RichTextBox di visualizzare collegamenti ipertestuali con il Windows Form](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md). È possibile impedire che l'utente modifica totale o parziale del testo nel controllo impostando il <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> proprietà `true`.  
  
 È possibile annullare e ripristinare la maggior parte delle operazioni di modifica in un <xref:System.Windows.Forms.RichTextBox> controllo chiamando la <xref:System.Windows.Forms.TextBoxBase.Undo%2A> e <xref:System.Windows.Forms.RichTextBox.Redo%2A> metodi. Il <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> metodo consente di determinare se l'ultima operazione annullata dall'utente può essere riapplicata al controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RichTextBox>
- [Controllo RichTextBox](richtextbox-control-windows-forms.md)
- [Cenni preliminari sul controllo TextBox](textbox-control-overview-windows-forms.md)
