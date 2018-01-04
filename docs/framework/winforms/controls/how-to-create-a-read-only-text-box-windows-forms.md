---
title: 'Procedura: creare una casella di testo in sola lettura (Windows Form)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 264ef1a7c1f121f889d57dcb0e36e216610418fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
