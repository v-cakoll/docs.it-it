---
title: Visualizzare più righe nel controllo TextBox
description: Informazioni su come visualizzare più righe nel controllo TextBox Windows Forms impostando le proprietà Multiline, WordWrap e ScrollBars.
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
ms.openlocfilehash: e40d720bcd56366f4f06bfe2e2d347aaf9aa9d6c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174471"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>Procedura: visualizzare più righe nel controllo TextBox Windows Form
Per impostazione predefinita, il <xref:System.Windows.Forms.TextBox> controllo Windows Forms Visualizza una sola riga di testo e non Visualizza le barre di scorrimento. Se il testo è più lungo dello spazio disponibile, solo parte del testo è visibile. È possibile modificare questo comportamento predefinito impostando le <xref:System.Windows.Forms.TextBox.Multiline%2A> <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> proprietà, e <xref:System.Windows.Forms.TextBox.ScrollBars%2A> su valori appropriati.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>Per visualizzare un ritorno a capo nel controllo TextBox  
  
- Per visualizzare un ritorno a capo in una riga a <xref:System.Windows.Forms.TextBox> più righe, utilizzare la <xref:System.Environment.NewLine%2A> Proprietà.  
  
     Tenere presente che l'interpretazione dei caratteri di escape ( \\ ) è specifica del linguaggio. Visual Basic utilizza `Chr$(13) & Chr$(10)` per la combinazione di caratteri di ritorno a capo e di avanzamento riga.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>Per visualizzare più righe nel controllo TextBox  
  
1. Impostare la proprietà <xref:System.Windows.Forms.TextBox.Multiline%2A> su `true`. Se <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> è `true` (impostazione predefinita), il testo nel controllo verrà visualizzato come uno o più paragrafi; in caso contrario, verrà visualizzato come elenco, in cui alcune righe possono essere ritagliate al bordo del controllo.  
  
2. Impostare la proprietà <xref:System.Windows.Forms.TextBox.ScrollBars%2A> su un valore appropriato.  
  
    |Valore|Descrizione|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|Utilizzare questo valore se il testo sarà un paragrafo che quasi sempre corrisponde al controllo. L'utente può utilizzare il puntatore del mouse per spostarsi all'interno del controllo se il testo è troppo lungo per essere visualizzato in una sola volta.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|Utilizzare questo valore se si desidera visualizzare un elenco di righe, alcune delle quali possono essere più lunghe della larghezza del <xref:System.Windows.Forms.TextBox> controllo.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|Utilizzare questo valore se l'elenco può essere più lungo dell'altezza del controllo.|  
  
3. Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> su un valore appropriato.  
  
    |Valore|Descrizione|  
    |-----------|-----------------|  
    |`false`|Il testo del controllo non verrà automaticamente incapsulato, quindi scorrerà verso destra fino a quando non viene raggiunta un'interruzioni di riga. Utilizzare questo valore se si scelgono le <xref:System.Windows.Forms.ScrollBars.Horizontal> barre <xref:System.Windows.Forms.ScrollBars.Both> di scorrimento o, sopra.|  
    |`true` (impostazione predefinita)|La barra di scorrimento orizzontale non verrà visualizzata. Utilizzare questo valore se si sceglie <xref:System.Windows.Forms.ScrollBars.Vertical> barre di scorrimento o <xref:System.Windows.Forms.ScrollBars.None> , sopra, per visualizzare uno o più paragrafi.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- [Cenni preliminari sul controllo TextBox](textbox-control-overview-windows-forms.md)
- [Procedura: controllare il punto di inserimento in un controllo TextBox Windows Form](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedura: creare una casella di testo Password con il controllo TextBox Windows Form](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: creare una casella di testo in sola lettura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedura: inserire virgolette in una stringa](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: selezionare testo nel controllo TextBox Windows Form](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
