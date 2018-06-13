---
title: 'Procedura: visualizzare più righe nel controllo TextBox Windows Form'
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
ms.openlocfilehash: c826a519d8be05430eb6e2434209424514347b5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538567"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>Procedura: visualizzare più righe nel controllo TextBox Windows Form
Per impostazione predefinita, Windows Form <xref:System.Windows.Forms.TextBox> controllo Visualizza una singola riga di testo e non visualizzare le barre di scorrimento. Se il testo è maggiore dello spazio disponibile, è visibile solo una parte del testo. È possibile modificare questo comportamento predefinito impostando il <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, e <xref:System.Windows.Forms.TextBox.ScrollBars%2A> proprietà sui valori appropriati.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>Per visualizzare un ritorno a capo nel controllo TextBox  
  
-   Per visualizzare un ritorno a capo in una multi-riga di <xref:System.Windows.Forms.TextBox>, utilizzare il <xref:System.Environment.NewLine%2A> proprietà.  
  
     Tenere presente che l'interpretazione dei caratteri di escape (\\) è specifico del linguaggio. Visual Basic utilizza `Chr$(13) & Chr$(10)` per la combinazione di caratteri ritorno a capo restituiti e avanzamento riga.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>Per visualizzare più righe nel controllo TextBox  
  
1.  Impostare la proprietà <xref:System.Windows.Forms.TextBox.Multiline%2A> su `true`. Se <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> è `true` (impostazione predefinita), il testo nel controllo verrà quindi visualizzati come uno o più paragrafi; in caso contrario, verrà visualizzato un elenco, in cui alcune righe potrebbero essere ritagliata in base al bordo del controllo.  
  
2.  Impostare la proprietà <xref:System.Windows.Forms.TextBox.ScrollBars%2A> su un valore appropriato.  
  
    |Valore|Descrizione|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|Utilizzare questo valore se il testo sarà un paragrafo che adatta quasi sempre il controllo. L'utente può utilizzare il puntatore del mouse per spostarsi all'interno del controllo se il testo è troppo lungo da visualizzare in una sola volta.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|Utilizzare questo valore se si desidera visualizzare un elenco di righe, alcuni dei quali può essere più lungo rispetto alla larghezza del <xref:System.Windows.Forms.TextBox> controllo.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|Utilizzare questo valore se l'elenco può essere più lungo rispetto all'altezza del controllo.|  
  
3.  Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> su un valore appropriato.  
  
    |Valore|Descrizione|  
    |-----------|-----------------|  
    |`false`|Il testo del controllo non automaticamente inclusi, in modo che verrà scorrere verso destra fino a quando non viene raggiunta un'interruzione di riga. Utilizzare questo valore se si sceglie <xref:System.Windows.Forms.ScrollBars.Horizontal> barre di scorrimento o <xref:System.Windows.Forms.ScrollBars.Both>sopra.|  
    |`true` (impostazione predefinita)|Non verrà visualizzata la barra di scorrimento orizzontale. Utilizzare questo valore se si sceglie <xref:System.Windows.Forms.ScrollBars.Vertical> barre di scorrimento o <xref:System.Windows.Forms.ScrollBars.None>precedente, per visualizzare uno o più paragrafi.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.TextBox>  
 [Cenni preliminari sul controllo TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Procedura: Creare una casella di testo in sola lettura](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [Procedura: Inserire virgolette in una stringa](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Procedura: Selezionare testo nel controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Controllo TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
