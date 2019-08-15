---
title: 'Procedura: Aggiungere colonne al controllo ListView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: e82fbcf63047873ebc6e5c40b8b9fbeb14a672e5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038176"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>Procedura: Aggiungere colonne al controllo ListView di Windows Forms usando la finestra di progettazione

Il controllo <xref:System.Windows.Forms.ListView> Windows Forms può visualizzare più colonne per ogni elemento dell'elenco nella visualizzazione **Dettagli** . È possibile utilizzare le colonne per visualizzare diversi tipi di informazioni su ogni elemento dell'elenco. Ad esempio, un elenco di file potrebbe visualizzare il nome del file, il tipo di file, le dimensioni e la data dell'Ultima modifica del file. Per informazioni sul popolamento delle colonne una volta create, vedere [procedura: Visualizza gli elementi secondari nelle colonne con il controllo](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)ListView Windows Forms.

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.ListView> modulo contenente un controllo. Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).


### <a name="to-add-columns-in-the-designer"></a>Per aggiungere colonne nella finestra di progettazione

1. Nella finestra **Proprietà** impostare la <xref:System.Windows.Forms.ListView.View%2A> proprietà del controllo su <xref:System.Windows.Forms.View.Details>.

2. Nella finestra **Proprietà** fare clic sul pulsante con i puntini di sospensione (![il pulsante con i puntini di sospensione (...) nella finestra proprietà <xref:System.Windows.Forms.ListView.Columns%2A> di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà.

     Viene visualizzato l' **Editor della raccolta ColumnHeader** .

3. Usare il pulsante **Aggiungi** per aggiungere nuove colonne. È quindi possibile selezionare l'intestazione di colonna e impostarne il testo (la didascalia della colonna), l'allineamento del testo e la larghezza.

## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Procedura: Visualizzare gli elementi secondari nelle colonne con il controllo ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Procedura: Visualizzare le icone per il controllo ListView Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
