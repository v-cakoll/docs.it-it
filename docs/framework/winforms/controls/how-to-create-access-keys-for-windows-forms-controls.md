---
title: 'Procedura: creare tasti di scelta per i controlli Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: af4cbcc5dacc4f9a0b5312b67838479bf6817228
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>Procedura: creare tasti di scelta per i controlli Windows Form
Un *chiave di accesso* è un carattere di sottolineato nel testo dell'etichetta di un controllo, ad esempio un pulsante, voce di menu o un menu. Con una chiave di accesso, l'utente può "fare clic su" un pulsante da premendo il tasto ALT in combinazione con la chiave di accesso predefinito. Ad esempio, se un pulsante viene eseguita una procedura per stampare un form e pertanto il relativo `Text` proprietà è impostata su "Print", aggiungendo una e commerciale prima della lettera "P", la lettera "P" essere sottolineati nel testo del pulsante in fase di esecuzione. L'utente può eseguire il comando associato al pulsante premendo ALT + P. È possibile avere una chiave di accesso per un controllo che non può ricevere lo stato attivo.  
  
### <a name="to-create-an-access-key-for-a-control"></a>Per creare una chiave di accesso per un controllo  
  
1.  Impostare il `Text` proprietà in una stringa che include una e commerciale (&) prima della lettera che sarà il collegamento.  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  Per includere una e commerciale in una didascalia senza creare una chiave di accesso, inserire due caratteri e commerciale (& &). Una singola e commerciale viene visualizzata nella barra del titolo e nessun carattere sottolineato.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Button>  
 [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Procedura: Impostare il testo visualizzato da un controllo Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
