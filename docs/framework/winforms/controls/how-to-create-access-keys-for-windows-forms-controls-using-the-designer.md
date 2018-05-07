---
title: 'Procedura: creare tasti di scelta per i controlli di Windows Form utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 023973e7fa4ab1e8b802d8c7cd8abef8201ed720
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>Procedura: creare tasti di scelta per i controlli di Windows Form utilizzando la finestra di progettazione
Un *chiave di accesso* è un carattere di sottolineato nel testo dell'etichetta di un controllo, ad esempio un pulsante, voce di menu o un menu. Consente all'utente di "fare clic su" un pulsante da premendo il tasto ALT in combinazione con la chiave di accesso predefinito. Ad esempio, se un pulsante viene eseguita una procedura per stampare un form e pertanto il relativo `Text` proprietà è impostata su "Stampa", aggiungendo una e commerciale (&) prima della lettera "P", la lettera "P" essere sottolineati nel testo del pulsante in fase di esecuzione. L'utente può eseguire il comando associato al pulsante premendo ALT + P. È possibile avere una chiave di accesso per un controllo che non può ricevere lo stato attivo.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-access-key-for-a-control"></a>Per creare una chiave di accesso per un controllo  
  
1.  Nel **proprietà** finestra, impostare il `Text` proprietà in una stringa che include una e commerciale (&) prima della lettera che verrà utilizzato come chiave di accesso. Ad esempio, per impostare la lettera "P" come tasto di scelta rapida, digitare **& stampa** nella griglia.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Button>  
 [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Procedura: Impostare il testo visualizzato da un controllo Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
