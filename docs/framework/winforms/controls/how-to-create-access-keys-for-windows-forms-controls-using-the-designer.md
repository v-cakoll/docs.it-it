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
ms.openlocfilehash: 01bed04483702ba2e62162b675aa1138bc1b0e01
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039514"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>Procedura: Creare tasti di scelta per i controlli Windows Forms usando la finestra di progettazione
Una *chiave di accesso* è un carattere sottolineato nel testo di un menu, di una voce di menu o dell'etichetta di un controllo, ad esempio un pulsante. Consente all'utente di fare clic su un pulsante premendo ALT in combinazione con il tasto di accesso predefinito. Se, ad esempio, un pulsante esegue una procedura per stampare un form e pertanto la `Text` relativa proprietà è impostata su "stampa", l'aggiunta di una e commerciale (&) prima della lettera "p" causa la sottolineatura della lettera "p" nel testo del pulsante in fase di esecuzione. L'utente può eseguire il comando associato al pulsante premendo ALT + P. Non è possibile avere una chiave di accesso per un controllo che non può ricevere lo stato attivo.

## <a name="to-create-an-access-key-for-a-control"></a>Per creare una chiave di accesso per un controllo

1. Nella finestra **Proprietà** impostare la `Text` proprietà su una stringa che include una e commerciale (&) prima della lettera che sarà il tasto di accesso. Per impostare, ad esempio, la lettera "P" come chiave di accesso, digitare **& stampa** nella griglia.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Button>
- [Procedura: Rispondi a Windows Forms clic sui pulsanti](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Imposta il testo visualizzato da un controllo Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
