---
title: 'Procedura: Controllo RichTextBox di visualizzare le barre di scorrimento in di Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 119cf736dfa7b8b8fce57b7e8fcb24dd09f01ce0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716491"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a>Procedura: Controllo RichTextBox di visualizzare le barre di scorrimento in di Windows Form
Per impostazione predefinita, i moduli di Windows <xref:System.Windows.Forms.RichTextBox> controllo vengono visualizzate le barre di scorrimento orizzontale e verticale in base alle esigenze. Vi sono sette i valori possibili per il <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> proprietà del <xref:System.Windows.Forms.RichTextBox> controllo, che sono descritte nella tabella seguente.  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a>Per visualizzare le barre di scorrimento in un controllo RichTextBox  
  
1.  Impostare la proprietà <xref:System.Windows.Forms.RichTextBox.Multiline%2A> su `true`. Non verrà visualizzato alcun tipo di barra di scorrimento, tra cui orizzontale, se il <xref:System.Windows.Forms.RichTextBox.Multiline%2A> è impostata su `false`.  
  
2.  Impostare il <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> proprietà su un valore appropriato del <xref:System.Windows.Forms.RichTextBoxScrollBars> enumerazione.  
  
    |Valore|Descrizione|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (impostazione predefinita)|Consente di visualizzare le barre di scorrimento orizzontale o verticale, o entrambi, solo quando il testo supera la larghezza o la lunghezza del controllo.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|Non viene mai visualizzata qualsiasi tipo di barra di scorrimento.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|Consente di visualizzare una barra solo quando il testo supera la larghezza del controllo di scorrimento orizzontale. (Per questo motivo, il <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> proprietà deve essere impostata su `false`.)|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|Consente di visualizzare una barra solo quando il testo supera l'altezza del controllo di scorrimento verticale.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|Quando delle barre di scorrimento orizzontale consente di visualizzare il <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> è impostata su `false`. La barra di scorrimento viene visualizzato in grigio se il testo non supera la larghezza del controllo.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|Viene visualizzato sempre una barra di scorrimento verticale. La barra di scorrimento viene visualizzato in grigio se il testo non supera la lunghezza del controllo.|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|Viene sempre visualizzata una barra di scorrimento verticale. Quando delle barre di scorrimento orizzontale consente di visualizzare il <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> è impostata su `false`. Quando il testo non supera la lunghezza del controllo o la larghezza vengono visualizzati in grigio le barre di scorrimento.|  
  
3.  Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> su un valore appropriato.  
  
    |Value|Descrizione|  
    |-----------|-----------------|  
    |`false`|Testo nel controllo non è regolato automaticamente per adattarsi alla larghezza del controllo, in modo che scorre verso destra fino a quando non viene raggiunta un'interruzione di riga. Utilizzare questo valore se si sceglie le barre di scorrimento orizzontale o entrambi, in precedenza.|  
    |`true` (impostazione predefinita)|Il testo del controllo viene regolato automaticamente per adattarsi alla larghezza del controllo. Non verrà visualizzata la barra di scorrimento orizzontale. Utilizzare questo valore se si sceglie le barre di scorrimento verticale sopra, per visualizzare uno o più paragrafi.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [Controllo RichTextBox](richtextbox-control-windows-forms.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
