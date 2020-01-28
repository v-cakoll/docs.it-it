---
title: 'Procedura: creare una casella di testo in sola lettura'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 17ae9524009c687cd62fb315f842e188e120ac68
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731267"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Procedura: creare una casella di testo in sola lettura (Windows Form)

È possibile trasformare una casella di testo Windows Forms modificabile in un controllo di sola lettura. Ad esempio, nella casella di testo può essere visualizzato un valore che in genere è stato modificato, ma che potrebbe non essere attualmente, a causa dello stato dell'applicazione.

## <a name="to-create-a-read-only-text-box"></a>Per creare una casella di testo di sola lettura

1. Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> del controllo <xref:System.Windows.Forms.TextBox> su `true`. Con la proprietà impostata su `true`, gli utenti possono ancora scorrere ed evidenziare il testo in una casella di testo senza consentire le modifiche. Un comando **Copy** è funzionante in una casella di testo, ma i comandi **taglia** e **Incolla** non lo sono.

    > [!NOTE]
    > La proprietà <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> influiscono solo sull'interazione dell'utente in fase di esecuzione. È comunque possibile modificare il contenuto della casella di testo a livello di codice in fase di esecuzione modificando la proprietà <xref:System.Windows.Forms.TextBox.Text%2A> della casella di testo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- [Cenni preliminari sul controllo TextBox](textbox-control-overview-windows-forms.md)
- [Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: Inserire virgolette in una stringa](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: Selezionare testo nel controllo TextBox di Windows Form](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Procedura: Visualizzare più righe nel controllo TextBox di Windows Form](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
