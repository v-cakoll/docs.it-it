---
title: Aggiungere e rimuovere elementi con il controllo ListView usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: cab40c556d9e5d21ce15bcd3d4da367bc08f33ab
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732305"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>Procedura: aggiungere e rimuovere elementi nel controllo ListView Windows Form mediante la finestra di progettazione

Il processo di aggiunta di un elemento a un Windows Forms <xref:System.Windows.Forms.ListView> controllo è costituito principalmente dalla specifica dell'elemento e dall'assegnazione di proprietà. L'aggiunta o la rimozione di elementi elenco può essere eseguita in qualsiasi momento.

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.ListView>. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-or-remove-items-using-the-designer"></a>Per aggiungere o rimuovere elementi utilizzando la finestra di progettazione

1. Selezionare il controllo <xref:System.Windows.Forms.ListView>.

2. Nella finestra **Proprietà** fare clic sui **puntini** di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.ListView.Items%2A>.

     Viene visualizzato l' **Editor della raccolta ListViewItem** .

3. Per aggiungere un elemento, fare clic sul pulsante **Aggiungi** . È quindi possibile impostare le proprietà del nuovo elemento, ad esempio le proprietà <xref:System.Windows.Forms.ListView.Text%2A> e <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.

4. Per rimuovere un elemento, selezionarlo e fare clic sul pulsante **Rimuovi** .

## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: Aggiungere colonne al controllo ListView di Windows Form](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Procedura: Visualizzare elementi secondari nelle colonne con il controllo ListView di Windows Form](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Procedura: Visualizzare icone per il controllo ListView di Windows Form](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Procedura: Raggruppare elementi in un controllo ListView di Windows Form](how-to-group-items-in-a-windows-forms-listview-control.md)
