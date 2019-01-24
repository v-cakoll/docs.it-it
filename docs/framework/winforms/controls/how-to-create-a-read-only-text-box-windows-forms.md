---
title: 'Procedura: Creare una casella di testo di sola lettura (Windows Form)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 89d331f6c7fad5880aff031eb808199292e493a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670342"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Procedura: Creare una casella di testo di sola lettura (Windows Form)
È possibile trasformare una casella di testo modificabile di Windows Form in un controllo di sola lettura. Ad esempio, la casella di testo venga visualizzato un valore che in genere viene modificato, ma potrebbe non essere al momento, a causa dello stato dell'applicazione.  
  
### <a name="to-create-a-read-only-text-box"></a>Per creare una casella di testo di sola lettura  
  
1.  Impostare il <xref:System.Windows.Forms.TextBox> del controllo <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> proprietà `true`. Con la proprietà è impostata su `true`, gli utenti possono ancora scorrere ed evidenziare il testo in una casella di testo non sono consentite modifiche. Oggetto **copia** comando è funzionale in una casella di testo, ma **Taglia** e **Incolla** comandi non sono.  
  
    > [!NOTE]
    >  Il <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> proprietà influisce solo sull'interazione dell'utente in fase di esecuzione. È possibile modificare contenuto della casella di testo a livello di codice in fase di esecuzione, modificando il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà della casella di testo.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.TextBox>
- [Cenni preliminari sul controllo TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: Inserire virgolette in una stringa](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: Selezionare il testo nel controllo TextBox Windows Form](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Procedura: Visualizzare più righe nel controllo TextBox Windows Form](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
