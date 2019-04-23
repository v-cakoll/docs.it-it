---
title: 'Procedura: Visualizzare più righe nel controllo TextBox di Windows Forms'
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
ms.openlocfilehash: 47404f02a753fe143dd573bdf73143416872af9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324188"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>Procedura: Visualizzare più righe nel controllo TextBox di Windows Forms
Per impostazione predefinita, i moduli di Windows <xref:System.Windows.Forms.TextBox> controllo Visualizza una singola riga di testo e non sono visualizzate le barre di scorrimento. Se il testo è maggiore dello spazio disponibile, è visibile solo una parte del testo. È possibile modificare questo comportamento predefinito impostando la <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, e <xref:System.Windows.Forms.TextBox.ScrollBars%2A> proprietà sui valori appropriati.  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>Per visualizzare un ritorno a capo nel controllo TextBox  
  
-   Per visualizzare un ritorno a capo in un multilinea <xref:System.Windows.Forms.TextBox>, usare il <xref:System.Environment.NewLine%2A> proprietà.  
  
     Tenere presente che l'interpretazione dei caratteri di escape (\\) è specifico del linguaggio. Visual Basic Usa `Chr$(13) & Chr$(10)` per la combinazione di caratteri ritorno a capo return e avanzamento riga.  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>Per visualizzare più righe nel controllo TextBox  
  
1. Impostare la proprietà <xref:System.Windows.Forms.TextBox.Multiline%2A> su `true`. Se <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> è `true` (impostazione predefinita), quindi il testo nel controllo verrà visualizzato come uno o più paragrafi; in caso contrario, verrà visualizzato un elenco, in cui alcune righe potrebbero essere ritagliata in base al bordo del controllo.  
  
2. Impostare la proprietà <xref:System.Windows.Forms.TextBox.ScrollBars%2A> su un valore appropriato.  
  
    |Value|Descrizione|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|Utilizzare questo valore se il testo sarà un paragrafo che si adatta quasi sempre il controllo. L'utente può usare il puntatore del mouse per spostarsi all'interno del controllo se il testo è troppo lungo da visualizzare in una sola volta.|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|Utilizzare questo valore se si desidera visualizzare un elenco di righe, alcuni dei quali può essere più lungo rispetto alla larghezza del <xref:System.Windows.Forms.TextBox> controllo.|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|Utilizzare questo valore se l'elenco potrebbe essere più lungo dell'altezza del controllo.|  
  
3. Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> su un valore appropriato.  
  
    |Value|Descrizione|  
    |-----------|-----------------|  
    |`false`|Testo nel controllo non verrà automaticamente racchiusi, in modo che scorre verso destra fino a quando non viene raggiunta un'interruzione di riga. Utilizzare questo valore se si è scelto <xref:System.Windows.Forms.ScrollBars.Horizontal> barre di scorrimento o <xref:System.Windows.Forms.ScrollBars.Both>sopra.|  
    |`true` (impostazione predefinita)|Non verrà visualizzata la barra di scorrimento orizzontale. Utilizzare questo valore se si è scelto <xref:System.Windows.Forms.ScrollBars.Vertical> barre di scorrimento o <xref:System.Windows.Forms.ScrollBars.None>precedente, per visualizzare uno o più paragrafi.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- [Cenni preliminari sul controllo TextBox](textbox-control-overview-windows-forms.md)
- [Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo di sola lettura](how-to-create-a-read-only-text-box-windows-forms.md)
- [Procedura: Inserire virgolette in una stringa](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: Selezionare il testo nel controllo TextBox Windows Form](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
