---
title: 'Procedura: Creare le chiavi di accesso per i controlli Windows Form'
ms.date: 03/30/2017
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
ms.openlocfilehash: 1bfbd2c6cd8aae410dfed506437bc85fbcb1d311
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597853"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>Procedura: Creare le chiavi di accesso per i controlli Windows Form
Un' *chiave di accesso* è un carattere di sottolineato nel testo di un menu, voce di menu o l'etichetta di un controllo, ad esempio un pulsante. Con una chiave di accesso, l'utente può "fare clic su" un pulsante premendo il tasto ALT in combinazione con la chiave di accesso predefinite. Ad esempio, se un pulsante viene eseguita una procedura per stampare un form e pertanto relativo `Text` proprietà è impostata su "Stampa", aggiungendo una e commerciale prima che la lettera "P", la lettera "P" per essere sottolineati nel testo del pulsante in fase di esecuzione. L'utente può eseguire il comando associato al pulsante premendo ALT + P. Non è possibile avere una chiave di accesso per un controllo che non può ricevere lo stato attivo.  
  
### <a name="to-create-an-access-key-for-a-control"></a>Per creare una chiave di accesso per un controllo  
  
1.  Impostare il `Text` proprietà in una stringa che include una e commerciale (&) alla lettera che sarà lo scelta rapida.  
  
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
    >  Per includere una e commerciale in un titolo senza creare una chiave di accesso, inserire due caratteri e commerciale (& &). Una singola e commerciale verrà visualizzata nella didascalia e nessun carattere sottolineato.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.Button>
- [Procedura: Rispondere alle selezioni dei pulsanti di Windows Form](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Impostare il testo visualizzato dal controllo di un Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
