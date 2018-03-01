---
title: Cenni preliminari sul controllo RichTextBox (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d6ed04ab478cc6c20d88ec97934f5e45528558c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="richtextbox-control-overview-windows-forms"></a>Cenni preliminari sul controllo RichTextBox (Windows Form)
Windows Form <xref:System.Windows.Forms.RichTextBox> controllo viene utilizzato per la visualizzazione, l'immissione e la modifica del testo con formattazione. Il <xref:System.Windows.Forms.RichTextBox> controllo esegue tutto il <xref:System.Windows.Forms.TextBox> dal controllo, ma può anche visualizzare i tipi di carattere, colori e collegamenti; caricare testo e immagini incorporate da un file; e trovare i caratteri specificati. Il <xref:System.Windows.Forms.RichTextBox> controllo viene in genere utilizzato per fornire funzionalità simili alle applicazioni di elaborazione di testi, ad esempio Microsoft Word di visualizzazione e modifica di testo. Come il <xref:System.Windows.Forms.TextBox> (controllo), il <xref:System.Windows.Forms.RichTextBox> controllo può visualizzare le barre di scorrimento; ma a differenza di <xref:System.Windows.Forms.TextBox> controllo, l'impostazione predefinita è per visualizzare le barre di scorrimento orizzontali e verticali in base alle necessità, e include impostazioni aggiuntive barra di scorrimento.  
  
## <a name="working-with-the-richtextbox-control"></a>Utilizzo del controllo RichTextBox  
 Come con la <xref:System.Windows.Forms.TextBox> , il testo visualizzato per impostare controllo, il <xref:System.Windows.Forms.RichTextBox.Text%2A> proprietà. Il <xref:System.Windows.Forms.RichTextBox> controllo è disponibili varie proprietà per formattare il testo. Per informazioni dettagliate su queste proprietà, vedere [Procedura: Impostare gli attributi dei caratteri per il controllo RichTextBox Windows Form](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) e [Procedura: Impostare rientri, rientri sporgenti e paragrafi puntati con il controllo RichTextBox Windows Form](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md). Per modificare i file, il <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> e <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> metodi è possono visualizzare e scrivere diversi formati di file, inclusi testo normale, testo normale Unicode e formato RTF (Rich Text). I formati di file possibili sono elencati <xref:System.Windows.Forms.RichTextBoxStreamType>. È possibile utilizzare il <xref:System.Windows.Forms.RichTextBox.Find%2A> metodo per trovare stringhe di testo o caratteri specifici.  
  
 È inoltre possibile utilizzare un <xref:System.Windows.Forms.RichTextBox> controllo per i collegamenti ipertestuali impostando il <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> proprietà `true` e la scrittura di codice per gestire il <xref:System.Windows.Forms.RichTextBox.LinkClicked> evento. Per altre informazioni, vedere [Procedura: Visualizzare collegamenti ipertestuali con il controllo RichTextBox Windows Form](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md). È possibile impedire che l'utente modifica totale o parziale del testo nel controllo impostando il <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> proprietà `true`.  
  
 È possibile annullare e ripristinare la maggior parte delle operazioni di modifica in un <xref:System.Windows.Forms.RichTextBox> controllo chiamando la <xref:System.Windows.Forms.TextBoxBase.Undo%2A> e <xref:System.Windows.Forms.RichTextBox.Redo%2A> metodi. Il <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> metodo consente di determinare se l'ultima operazione annullata dall'utente possa essere riapplicata al controllo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.RichTextBox>  
 [Controllo RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Cenni preliminari sul controllo TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
