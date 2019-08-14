---
title: 'Procedura: Creare una casella di testo di sola lettura (Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 18d2f5ed2530957487ac25c3eb6240f8bc50a938
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971936"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Procedura: Creare una casella di testo di sola lettura (Windows Forms)

È possibile trasformare una casella di testo Windows Forms modificabile in un controllo di sola lettura. Ad esempio, nella casella di testo può essere visualizzato un valore che in genere è stato modificato, ma che potrebbe non essere attualmente, a causa dello stato dell'applicazione.

## <a name="to-create-a-read-only-text-box"></a>Per creare una casella di testo di sola lettura

1. Impostare la <xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> proprietà del controllo su `true`. Con la proprietà impostata su `true`, gli utenti possono ancora scorrere ed evidenziare il testo in una casella di testo senza consentire le modifiche. Un comando **Copy** è funzionante in una casella di testo, ma i comandi **taglia** e **Incolla** non lo sono.

    > [!NOTE]
    > La <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> proprietà influiscono solo sull'interazione dell'utente in fase di esecuzione. È comunque possibile modificare il contenuto della casella di testo a livello di codice in <xref:System.Windows.Forms.TextBox.Text%2A> fase di esecuzione modificando la proprietà della casella di testo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- [Cenni preliminari sul controllo TextBox](textbox-control-overview-windows-forms.md)
- [Procedura: Controllare il punto di inserimento in un controllo TextBox Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedura: Creare una casella di testo password con il controllo TextBox Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: Inserire le virgolette in una stringa](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: Selezionare testo nel controllo TextBox Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Procedura: Visualizzare più righe nel controllo TextBox Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
