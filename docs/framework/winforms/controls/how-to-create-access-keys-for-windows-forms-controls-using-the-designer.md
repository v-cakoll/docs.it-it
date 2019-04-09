---
title: 'Procedura: Creare tasti di scelta per i controlli Windows Forms usando la finestra di progettazione'
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
ms.openlocfilehash: 900a955173c28c7b86fce73e418561ed437719c4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216925"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>Procedura: Creare tasti di scelta per i controlli Windows Forms usando la finestra di progettazione
Un' *chiave di accesso* è un carattere di sottolineato nel testo di un menu, voce di menu o l'etichetta di un controllo, ad esempio un pulsante. Consente all'utente di "fare clic su" un pulsante premendo il tasto ALT in combinazione con la chiave di accesso predefinite. Ad esempio, se un pulsante viene eseguita una procedura per stampare un form e pertanto relativo `Text` proprietà è impostata su "Stampa", aggiungendo una e commerciale (&) prima della lettera "P", la lettera "P" per essere sottolineati nel testo del pulsante in fase di esecuzione. L'utente può eseguire il comando associato al pulsante premendo ALT + P. Non è possibile avere una chiave di accesso per un controllo che non può ricevere lo stato attivo.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-an-access-key-for-a-control"></a>Per creare una chiave di accesso per un controllo  
  
1.  Nel **delle proprietà** impostare nella finestra di `Text` proprietà in una stringa che include una e commerciale (&) alla lettera che sarà la chiave di accesso. Ad esempio, per impostare la lettera "P" come chiave di accesso, digitare **conf** nella griglia.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Button>
- [Procedura: Rispondere alla selezione dei pulsanti Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Impostare il testo visualizzato da un controllo di Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
