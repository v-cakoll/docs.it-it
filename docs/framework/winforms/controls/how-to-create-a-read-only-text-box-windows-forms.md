---
title: 'Procedura: creare una casella di testo in sola lettura (Windows Form)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 06e03f67bd1f084b30bce85c3d81ad7b8c97a1b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Procedura: creare una casella di testo in sola lettura (Windows Form)
È possibile trasformare una casella di testo modificabile Windows Form in un controllo di sola lettura. Ad esempio, la casella di testo potrebbe visualizzare un valore che viene modificato in genere, ma potrebbe non essere al momento, a causa dello stato dell'applicazione.  
  
### <a name="to-create-a-read-only-text-box"></a>Per creare una casella di testo di sola lettura  
  
1.  Impostare il <xref:System.Windows.Forms.TextBox> del controllo <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> proprietà `true`. Con la proprietà impostata su `true`, gli utenti possono comunque scorrere ed evidenziare il testo in una casella di testo non sono consentite modifiche. Oggetto **copia** comando è funzionale in una casella di testo, ma **Taglia** e **Incolla** comandi non sono.  
  
    > [!NOTE]
    >  Il <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> proprietà influisce solo sull'interazione dell'utente in fase di esecuzione. È possibile modificare contenuto casella di testo a livello di codice in fase di esecuzione, modificando il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà della casella di testo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.TextBox>  
 [Cenni preliminari sul controllo TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [Procedura: Inserire virgolette in una stringa](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [Procedura: Selezionare testo nel controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [Procedura: Visualizzare più righe nel controllo TextBox di Windows Form](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [Controllo TextBox](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
