---
title: Panoramica del controllo RichTextBox
ms.date: 03/30/2017
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
ms.openlocfilehash: 0d40967d97622b23e9dcb07e861f190327e6baba
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742402"
---
# <a name="richtextbox-control-overview-windows-forms"></a>Cenni preliminari sul controllo RichTextBox (Windows Form)
Il controllo Windows Forms <xref:System.Windows.Forms.RichTextBox> viene utilizzato per visualizzare, immettere e modificare il testo con la formattazione. Il controllo <xref:System.Windows.Forms.RichTextBox> esegue tutte le operazioni del controllo <xref:System.Windows.Forms.TextBox>, ma può anche visualizzare i tipi di carattere, i colori e i collegamenti; carica il testo e le immagini incorporate da un file; e trovano i caratteri specificati. Il controllo <xref:System.Windows.Forms.RichTextBox> viene in genere usato per fornire funzionalità di visualizzazione e manipolazione del testo simili alle applicazioni di elaborazione di Word, ad esempio Microsoft Word. Analogamente al controllo <xref:System.Windows.Forms.TextBox>, il controllo <xref:System.Windows.Forms.RichTextBox> può visualizzare le barre di scorrimento; Tuttavia, a differenza del controllo <xref:System.Windows.Forms.TextBox>, l'impostazione predefinita prevede la visualizzazione di barre di scorrimento orizzontali e verticali in base alle esigenze e di altre impostazioni della barra di scorrimento.  
  
## <a name="working-with-the-richtextbox-control"></a>Utilizzo del controllo RichTextBox  
 Come per il controllo <xref:System.Windows.Forms.TextBox>, il testo visualizzato viene impostato dalla proprietà <xref:System.Windows.Forms.RichTextBox.Text%2A>. Il controllo <xref:System.Windows.Forms.RichTextBox> dispone di numerose proprietà per formattare il testo. Per informazioni dettagliate su queste proprietà, vedere [Procedura: Impostare gli attributi dei caratteri per il controllo RichTextBox Windows Form](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) e [Procedura: Impostare rientri, rientri sporgenti e paragrafi puntati con il controllo RichTextBox Windows Form](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md). Per modificare i file, i metodi <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> e <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> possono visualizzare e scrivere più formati di file, tra cui testo normale, testo normale Unicode e RTF (Rich Text Format). I formati di file possibili sono elencati in <xref:System.Windows.Forms.RichTextBoxStreamType>. È possibile usare il metodo <xref:System.Windows.Forms.RichTextBox.Find%2A> per trovare stringhe di testo o caratteri specifici.  
  
 È anche possibile usare un controllo <xref:System.Windows.Forms.RichTextBox> per i collegamenti di tipo Web impostando la proprietà <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> su `true` e scrivendo codice per gestire l'evento <xref:System.Windows.Forms.RichTextBox.LinkClicked>. Per altre informazioni, vedere [Procedura: Visualizzare collegamenti ipertestuali con il controllo RichTextBox Windows Form](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md). È possibile impedire all'utente di modificare parte o tutto il testo nel controllo impostando la proprietà <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> su `true`.  
  
 È possibile annullare e ripetere la maggior parte delle operazioni di modifica in un controllo <xref:System.Windows.Forms.RichTextBox> chiamando i metodi <xref:System.Windows.Forms.TextBoxBase.Undo%2A> e <xref:System.Windows.Forms.RichTextBox.Redo%2A>. Il <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> metodo consente di determinare se l'ultima operazione annullata dall'utente può essere riapplicata al controllo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RichTextBox>
- [Controllo RichTextBox](richtextbox-control-windows-forms.md)
- [Cenni preliminari sul controllo TextBox](textbox-control-overview-windows-forms.md)
