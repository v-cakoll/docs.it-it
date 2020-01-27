---
title: Visualizzare più righe nel controllo TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: 61ea671c1e86fa8254bfc1b043a46f3b7aa6af1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728282"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>Procedura: visualizzare più righe nel controllo TextBox Windows Form
Per impostazione predefinita, il controllo Windows Forms <xref:System.Windows.Forms.TextBox> Visualizza una sola riga di testo e non Visualizza le barre di scorrimento. Se il testo è più lungo dello spazio disponibile, solo parte del testo è visibile. È possibile modificare questo comportamento predefinito impostando le proprietà <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>e <xref:System.Windows.Forms.TextBox.ScrollBars%2A> su valori appropriati.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>Per visualizzare un ritorno a capo nel controllo TextBox  
  
- Per visualizzare un ritorno a capo in una <xref:System.Windows.Forms.TextBox>a più righe, utilizzare la proprietà <xref:System.Environment.NewLine%2A>.  
  
     Tenere presente che l'interpretazione dei caratteri di escape (\\) è specifica del linguaggio. Visual Basic utilizza `Chr$(13) & Chr$(10)` per la combinazione di caratteri di ritorno a capo e di avanzamento riga.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>Per visualizzare più righe nel controllo TextBox  
  
1. Impostare la proprietà <xref:System.Windows.Forms.TextBox.Multiline%2A> su `true`. Se <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> è `true` (impostazione predefinita), il testo nel controllo verrà visualizzato come uno o più paragrafi; in caso contrario, verrà visualizzato come elenco, in cui alcune righe possono essere ritagliate al bordo del controllo.  
  
2. Impostare la proprietà <xref:System.Windows.Forms.TextBox.ScrollBars%2A> su un valore appropriato.  
  
    |Valore|Descrizione|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|Utilizzare questo valore se il testo sarà un paragrafo che quasi sempre corrisponde al controllo. L'utente può utilizzare il puntatore del mouse per spostarsi all'interno del controllo se il testo è troppo lungo per essere visualizzato in una sola volta.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|Utilizzare questo valore se si desidera visualizzare un elenco di righe, alcune delle quali possono essere più lunghe della larghezza del controllo <xref:System.Windows.Forms.TextBox>.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|Utilizzare questo valore se l'elenco può essere più lungo dell'altezza del controllo.|  
  
3. Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> su un valore appropriato.  
  
    |Valore|Descrizione|  
    |-----------|-----------------|  
    |`false`|Il testo del controllo non verrà automaticamente incapsulato, quindi scorrerà verso destra fino a quando non viene raggiunta un'interruzioni di riga. Utilizzare questo valore se si è scelto <xref:System.Windows.Forms.ScrollBars.Horizontal> barre di scorrimento o <xref:System.Windows.Forms.ScrollBars.Both>, sopra.|  
    |`true` (impostazione predefinita)|La barra di scorrimento orizzontale non verrà visualizzata. Utilizzare questo valore se si è scelto <xref:System.Windows.Forms.ScrollBars.Vertical> barre di scorrimento o <xref:System.Windows.Forms.ScrollBars.None>, sopra, per visualizzare uno o più paragrafi.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- [Cenni preliminari sul controllo TextBox](textbox-control-overview-windows-forms.md)
- [Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo in sola lettura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedura: Inserire virgolette in una stringa](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: Selezionare testo nel controllo TextBox di Windows Form](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
