---
title: 'Procedura: visualizzare le barre di scorrimento nel controllo RichTextBox Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3b20c526b27eb185bf79eaf0ace47e5a9fded42a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>Procedura: visualizzare le barre di scorrimento nel controllo RichTextBox Windows Form
Per impostazione predefinita, Windows Form <xref:System.Windows.Forms.RichTextBox> controllo vengono visualizzate barre di scorrimento orizzontale e verticale in base alle esigenze. Esistono sette valori possibili per il <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> proprietà del <xref:System.Windows.Forms.RichTextBox> controllo, che sono descritte nella tabella seguente.  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>Per visualizzare le barre di scorrimento in un controllo RichTextBox  
  
1.  Impostare la proprietà <xref:System.Windows.Forms.RichTextBox.Multiline%2A> su `true`. Nessun tipo di barra di scorrimento, tra cui orizzontale, verrà visualizzato se il <xref:System.Windows.Forms.RichTextBox.Multiline%2A> è impostata su `false`.  
  
2.  Impostare il <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> proprietà su un valore appropriato per il <xref:System.Windows.Forms.RichTextBoxScrollBars> enumerazione.  
  
    |Valore|Descrizione|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (impostazione predefinita)|Consente di visualizzare le barre di scorrimento orizzontale o verticale, o entrambi, solo quando il testo supera la larghezza o la lunghezza del controllo.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|Non visualizza mai qualsiasi tipo di barra di scorrimento.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|Visualizza una barra solo quando il testo supera la larghezza del controllo di scorrimento orizzontale. (A questo scopo, il <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> proprietà deve essere impostata su `false`.)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|Visualizza una barra solo quando il testo supera l'altezza del controllo di scorrimento verticale.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|Viene visualizzata quando della barra di scorrimento orizzontale di <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> è impostata su `false`. La barra di scorrimento non è disponibile quando il testo supera la larghezza del controllo.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|Visualizza sempre una barra di scorrimento verticale. La barra di scorrimento non è disponibile quando il testo supera la lunghezza del controllo.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|Visualizza sempre una barra di scorrimento verticale. Viene visualizzata quando della barra di scorrimento orizzontale di <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> è impostata su `false`. Le barre di scorrimento non sono disponibili quando il testo supera la larghezza o la lunghezza del controllo.|  
  
3.  Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> su un valore appropriato.  
  
    |Valore|Descrizione|  
    |-----------|-----------------|  
    |`false`|Il testo del controllo non viene regolato automaticamente in base alla larghezza del controllo, in modo che verrà scorrere verso destra fino a quando non viene raggiunta un'interruzione di riga. Utilizzare questo valore se si sceglie di barre di scorrimento orizzontale o entrambi, in precedenza.|  
    |`true` (impostazione predefinita)|Il testo del controllo viene regolato automaticamente in base alla larghezza del controllo. Non verrà visualizzata la barra di scorrimento orizzontale. Utilizzare questo valore se si sceglie le barre di scorrimento verticale sopra, per visualizzare uno o più paragrafi.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.RichTextBoxScrollBars>  
 <xref:System.Windows.Forms.RichTextBox>  
 [Controllo RichTextBox](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
