---
title: Visualizzare le barre di scorrimento nel controllo RichTextBox
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 2185b572ef20765043d3df3dbfd8bf5b21cfac28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745558"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>Procedura: visualizzare le barre di scorrimento nel controllo RichTextBox Windows Form
Per impostazione predefinita, il controllo Windows Forms <xref:System.Windows.Forms.RichTextBox> Visualizza le barre di scorrimento orizzontale e verticale in base alle esigenze. Sono disponibili sette valori possibili per la proprietà <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> del controllo <xref:System.Windows.Forms.RichTextBox>, descritti nella tabella seguente.  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>Per visualizzare le barre di scorrimento in un controllo RichTextBox  
  
1. Impostare la proprietà <xref:System.Windows.Forms.RichTextBox.Multiline%2A> su `true`. Nessun tipo di barra di scorrimento, incluso orizzontale, verrà visualizzato se la proprietà <xref:System.Windows.Forms.RichTextBox.Multiline%2A> è impostata su `false`.  
  
2. Impostare la proprietà <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> su un valore appropriato dell'enumerazione <xref:System.Windows.Forms.RichTextBoxScrollBars>.  
  
    |Valore|Descrizione|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (impostazione predefinita)|Visualizza barre di scorrimento orizzontali o verticali, o entrambe, solo quando il testo supera la larghezza o la lunghezza del controllo.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|Non visualizza mai alcun tipo di barra di scorrimento.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|Consente di visualizzare una barra di scorrimento orizzontale solo quando il testo supera la larghezza del controllo. Per eseguire questa operazione, è necessario impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> su `false`.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|Consente di visualizzare una barra di scorrimento verticale solo quando il testo supera l'altezza del controllo.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|Visualizza una barra di scorrimento orizzontale quando la proprietà <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> è impostata su `false`. La barra di scorrimento viene visualizzata in grigio quando il testo non supera la larghezza del controllo.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|Visualizza sempre una barra di scorrimento verticale. La barra di scorrimento viene visualizzata in grigio quando il testo non supera la lunghezza del controllo.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|Viene sempre visualizzata una barra di scorrimento verticale. Visualizza una barra di scorrimento orizzontale quando la proprietà <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> è impostata su `false`. Le barre di scorrimento vengono visualizzate in grigio quando il testo non supera la larghezza o la lunghezza del controllo.|  
  
3. Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> su un valore appropriato.  
  
    |Valore|Descrizione|  
    |-----------|-----------------|  
    |`false`|Il testo nel controllo non viene regolato automaticamente per adattarsi alla larghezza del controllo, quindi scorre verso destra fino a quando non viene raggiunta un'interruzioni di riga. Utilizzare questo valore se si scelgono le barre di scorrimento orizzontali o entrambe, sopra.|  
    |`true` (impostazione predefinita)|Il testo nel controllo viene regolato automaticamente per adattarsi alla larghezza del controllo. La barra di scorrimento orizzontale non verrà visualizzata. Utilizzare questo valore se si scelgono barre di scorrimento verticali o nessuno, sopra, per visualizzare uno o più paragrafi.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [Controllo RichTextBox](richtextbox-control-windows-forms.md)
- [Controlli da utilizzare in Windows Form](controls-to-use-on-windows-forms.md)
