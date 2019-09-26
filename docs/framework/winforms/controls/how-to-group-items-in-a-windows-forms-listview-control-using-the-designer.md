---
title: 'Procedura: Raggruppare elementi in un controllo ListView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: b63bcd9e5e357db350cc2987e09af84eb58bdcff
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "69039404"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a>Procedura: Raggruppare elementi in un controllo ListView di Windows Forms usando la finestra di progettazione

La funzionalità di raggruppamento del <xref:System.Windows.Forms.ListView> controllo consente di visualizzare set correlati di elementi in gruppi. Questi gruppi sono separati sullo schermo da intestazioni di gruppo orizzontali che contengono i titoli del gruppo. È possibile utilizzare <xref:System.Windows.Forms.ListView> i gruppi per semplificare l'esplorazione degli elenchi di grandi dimensioni raggruppando gli elementi in ordine alfabetico, per data o per qualsiasi altro raggruppamento logico. Nell'immagine seguente vengono illustrati alcuni elementi raggruppati:

![Numeri separati in gruppi dispari e uniformi.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.ListView> modulo contenente un controllo. Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).

Per abilitare il raggruppamento, è innanzitutto necessario creare uno o più <xref:System.Windows.Forms.ListViewGroup> oggetti nella finestra di progettazione o a livello di codice. Una volta definito un gruppo, è possibile assegnarvi elementi.

> [!NOTE]
> <xref:System.Windows.Forms.ListView>i gruppi sono disponibili solo [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] in quando l'applicazione chiama <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> il metodo. Nei sistemi operativi precedenti, qualsiasi codice correlato ai gruppi non ha alcun effetto e i gruppi non verranno visualizzati. Per altre informazioni, vedere <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.

## <a name="to-add-or-remove-groups-in-the-designer"></a>Per aggiungere o rimuovere gruppi nella finestra di progettazione

1. Nella finestra **Proprietà** fare clic sui **puntini** di![sospensione (il pulsante con i puntini di sospensione (...)](./media/visual-studio-ellipsis-button.png)nel pulsante finestra proprietà di Visual <xref:System.Windows.Forms.ListView.Groups%2A> Studio.) accanto alla proprietà.

     Viene visualizzato l' **Editor della raccolta ListView** .

2. Per aggiungere un gruppo, fare clic sul pulsante **Aggiungi** . È quindi possibile impostare le proprietà del nuovo gruppo, ad esempio le <xref:System.Windows.Forms.ListViewGroup.Header%2A> proprietà <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> e. Per rimuovere un gruppo, selezionarlo e fare clic sul pulsante **Rimuovi** .

## <a name="to-assign-items-to-groups-in-the-designer"></a>Per assegnare elementi a gruppi nella finestra di progettazione

1. Nella finestra **Proprietà** fare clic sui **puntini** di![sospensione (il pulsante con i puntini di sospensione (...)](./media/visual-studio-ellipsis-button.png)nel pulsante finestra proprietà di Visual <xref:System.Windows.Forms.ListView.Items%2A> Studio.) accanto alla proprietà.

     Viene visualizzato l' **Editor della raccolta ListViewItem** .

2. Per aggiungere un nuovo elemento, fare clic sul pulsante **Aggiungi** . È quindi possibile impostare le proprietà del nuovo elemento, ad esempio le <xref:System.Windows.Forms.ListViewItem.Text%2A> proprietà <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> e.

3. Selezionare la <xref:System.Windows.Forms.ListViewItem.Group%2A> proprietà e scegliere un gruppo dall'elenco a discesa.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [Controllo ListView](listview-control-windows-forms.md)
- [Panoramica del controllo ListView](listview-control-overview-windows-forms.md)
- [Procedura: Aggiungere e rimuovere elementi con il controllo ListView Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
