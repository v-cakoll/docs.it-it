---
title: 'Procedura: creare una casella di testo in sola lettura'
description: Informazioni sulla trasformazione di una casella di testo Windows Forms modificabile in una casella di testo Windows Forms di sola lettura.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 5baa7c66d5f16560a4ea23861d563b099592957f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619364"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Procedura: creare una casella di testo in sola lettura (Windows Form)

È possibile trasformare una casella di testo Windows Forms modificabile in un controllo di sola lettura. Ad esempio, nella casella di testo può essere visualizzato un valore che in genere è stato modificato, ma che potrebbe non essere attualmente, a causa dello stato dell'applicazione.

## <a name="to-create-a-read-only-text-box"></a>Per creare una casella di testo di sola lettura

1. Impostare la <xref:System.Windows.Forms.TextBox> proprietà del controllo <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> su `true` . Con la proprietà impostata su `true` , gli utenti possono ancora scorrere ed evidenziare il testo in una casella di testo senza consentire le modifiche. Un comando **Copy** è funzionante in una casella di testo, ma i comandi **taglia** e **Incolla** non lo sono.

    > [!NOTE]
    > La <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> proprietà influiscono solo sull'interazione dell'utente in fase di esecuzione. È comunque possibile modificare il contenuto della casella di testo a livello di codice in fase di esecuzione modificando la <xref:System.Windows.Forms.TextBox.Text%2A> proprietà della casella di testo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TextBox>
- [Cenni preliminari sul controllo TextBox](textbox-control-overview-windows-forms.md)
- [Procedura: controllare il punto di inserimento in un controllo TextBox Windows Form](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Procedura: creare una casella di testo Password con il controllo TextBox Windows Form](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Procedura: inserire virgolette in una stringa](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Procedura: selezionare testo nel controllo TextBox Windows Form](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Procedura: visualizzare più righe nel controllo TextBox Windows Form](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Controllo TextBox](textbox-control-windows-forms.md)
