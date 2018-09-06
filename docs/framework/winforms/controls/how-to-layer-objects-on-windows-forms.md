---
title: 'Procedura: disporre oggetti su più livelli in Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
ms.openlocfilehash: d67d9b204c316dce5f3818496d791ed4c1b352f2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43875970"
---
# <a name="how-to-layer-objects-on-windows-forms"></a>Procedura: disporre oggetti su più livelli in Windows Form
Quando si crea un'interfaccia utente complessa, o di lavoro con un form MDI (interfaccia), spesso si desidera sia form e controlli figlio per creare più complesse interfacce utente (UI) di livello. Per spostare e tenere traccia di controlli e finestre all'interno del contesto di un gruppo, è modificare l'ordine z. *Ordine Z* è disposizione visiva di controlli in un form lungo l'asse z del form (profondità). La finestra nella parte superiore dello z-order si sovrappone a tutte le altre finestre. Tutte le altre finestre si sovrappongono la finestra nella parte inferiore dello z-order.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-layer-controls-at-design-time"></a>Per i controlli dei livelli in fase di progettazione  
  
1.  Selezionare un controllo che si desidera di livello.  
  
2.  Nel **formato** dal menu **ordine**, quindi fare clic su **porta in primo piano** o **porta in secondo piano**.  
  
### <a name="to-layer-controls-programmatically"></a>Per i controlli dei livelli a livello di codice  
  
-   Usare la <xref:System.Windows.Forms.Control.BringToFront%2A> e <xref:System.Windows.Forms.Control.SendToBack%2A> metodi per modificare l'ordine z dei controlli.  
  
     Ad esempio, se un <xref:System.Windows.Forms.TextBox> controllo `txtFirstName`, si trova di sotto di un altro controllo e si desidera venga in primo piano, usare il codice seguente:  
  
    ```vb  
    txtFirstName.BringToFront()  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  Supporta Windows Form *contenimento di controlli*. Contenimento dei controlli prevede l'inserimento di un numero di controlli all'interno di un controllo contenitore, ad esempio un numero di <xref:System.Windows.Forms.RadioButton> controlli all'interno di un <xref:System.Windows.Forms.GroupBox> controllo. È quindi possibile livellare i controlli all'interno del controllo che lo contiene. Spostando la casella di gruppo consente di spostare i controlli, perché sono contenuti all'interno.  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli Windows Form](../../../../docs/framework/winforms/controls/index.md)  
 [Disposizione di controlli in Windows Form](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Controlli Windows Form per funzione](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
