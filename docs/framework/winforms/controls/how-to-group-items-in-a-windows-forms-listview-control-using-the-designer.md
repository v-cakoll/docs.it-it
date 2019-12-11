---
title: 'Procedura: raggruppare elementi in un controllo ListView Windows Form utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 03958109d4daa3fc369660de66973bb659e29c60
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960173"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Procedura: raggruppare elementi in un controllo ListView Windows Form utilizzando la finestra di progettazione

La funzionalità di raggruppamento del controllo <xref:System.Windows.Forms.ListView> consente di visualizzare set correlati di elementi in gruppi. Questi gruppi sono separati sullo schermo da intestazioni di gruppo orizzontali che contengono i titoli del gruppo. È possibile utilizzare i gruppi di <xref:System.Windows.Forms.ListView> per semplificare l'esplorazione degli elenchi di grandi dimensioni raggruppando gli elementi in ordine alfabetico, per data o per qualsiasi altro raggruppamento logico. Nell'immagine seguente vengono illustrati alcuni elementi raggruppati:

![Numeri separati in gruppi dispari e uniformi.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.ListView>. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).

Per abilitare il raggruppamento, è innanzitutto necessario creare uno o più oggetti <xref:System.Windows.Forms.ListViewGroup> nella finestra di progettazione o a livello di codice. Una volta definito un gruppo, è possibile assegnarvi elementi.

## <a name="to-add-or-remove-groups-in-the-designer"></a>Per aggiungere o rimuovere gruppi nella finestra di progettazione

1. Nella finestra **Proprietà** fare clic sui **puntini** di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.ListView.Groups%2A>.

     Viene visualizzato l' **Editor della raccolta ListView** .

2. Per aggiungere un gruppo, fare clic sul pulsante **Aggiungi** . È quindi possibile impostare le proprietà del nuovo gruppo, ad esempio le proprietà <xref:System.Windows.Forms.ListViewGroup.Header%2A> e <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>. Per rimuovere un gruppo, selezionarlo e fare clic sul pulsante **Rimuovi** .

## <a name="to-assign-items-to-groups-in-the-designer"></a>Per assegnare elementi a gruppi nella finestra di progettazione

1. Nella finestra **Proprietà** fare clic sui **puntini** di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.ListView.Items%2A>.

     Viene visualizzato l' **Editor della raccolta ListViewItem** .

2. Per aggiungere un nuovo elemento, fare clic sul pulsante **Aggiungi** . È quindi possibile impostare le proprietà del nuovo elemento, ad esempio le proprietà <xref:System.Windows.Forms.ListViewItem.Text%2A> e <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.

3. Selezionare la proprietà <xref:System.Windows.Forms.ListViewItem.Group%2A> e scegliere un gruppo dall'elenco a discesa.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [Controllo ListView](listview-control-windows-forms.md)
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
