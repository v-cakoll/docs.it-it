---
title: Aggiungere colonne al controllo ListView utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 627f8627aac861877a05c13def07427199807754
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744616"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>Procedura: aggiungere colonne al controllo ListView Windows Form utilizzando la finestra di progettazione

Il controllo Windows Forms <xref:System.Windows.Forms.ListView> può visualizzare più colonne per ogni elemento dell'elenco nella visualizzazione **Dettagli** . È possibile utilizzare le colonne per visualizzare diversi tipi di informazioni su ogni elemento dell'elenco. Ad esempio, un elenco di file potrebbe visualizzare il nome del file, il tipo di file, le dimensioni e la data dell'Ultima modifica del file. Per informazioni sul popolamento delle colonne una volta create, vedere [procedura: visualizzare elementi secondari nelle colonne con il controllo ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.ListView>. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-columns-in-the-designer"></a>Per aggiungere colonne nella finestra di progettazione

1. Nella finestra **Proprietà** impostare la proprietà <xref:System.Windows.Forms.ListView.View%2A> del controllo su <xref:System.Windows.Forms.View.Details>.

2. Nella finestra **Proprietà** fare clic sul pulsante con i **puntini** di sospensione (![pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.ListView.Columns%2A>.

     Viene visualizzato l' **Editor della raccolta ColumnHeader** .

3. Usare il pulsante **Aggiungi** per aggiungere nuove colonne. È quindi possibile selezionare l'intestazione di colonna e impostarne il testo (la didascalia della colonna), l'allineamento del testo e la larghezza.

## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Procedura: Visualizzare elementi secondari nelle colonne con il controllo ListView di Windows Form](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Procedura: Visualizzare icone per il controllo ListView di Windows Form](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
