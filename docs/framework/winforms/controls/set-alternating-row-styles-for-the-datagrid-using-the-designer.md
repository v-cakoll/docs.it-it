---
title: 'Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: 1be746d4cce36344e034692a0e2e8e6a9e9320d5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040432"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Forms usando la finestra di progettazione

I dati tabulari vengono spesso presentati in un formato di tipo Ledger, in cui le righe alternate hanno colori di sfondo diversi. Questo formato permette agli utenti di individuare più facilmente le celle di ogni riga, soprattutto nelle tabelle estese in larghezza con molte colonne.

Con il controllo <xref:System.Windows.Forms.DataGridView>, è possibile specificare informazioni di stile complete per le righe alterne. È possibile utilizzare le caratteristiche di stile, ad esempio il colore di primo piano e il tipo di carattere, oltre al colore di sfondo, per distinguere le righe alternate. Per ulteriori informazioni, vedere la pagina relativa agli [stili delle celle nel controllo DataGridView Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.DataGridView> modulo contenente un controllo. Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).


### <a name="define-styles-for-alternating-rows"></a>Definire gli stili per le righe alternate

1. Selezionare il <xref:System.Windows.Forms.DataGridView> controllo nella finestra di progettazione.

2. Nella finestra **Proprietà** fare clic sul pulsante con i puntini di sospensione (![il pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> proprietà.

3. Nella finestra di dialogo **Generatore CellStyle** , definire lo stile impostando le proprietà e usare il riquadro di **Anteprima** per confermare le scelte effettuate. Gli stili specificati vengono usati per tutte le altre righe visualizzate nel controllo, a partire dal secondo.

4. Per definire gli stili per le righe rimanenti, ripetere i passaggi 2 e <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 3 usando la proprietà.

    > [!NOTE]
    > Le celle vengono visualizzate utilizzando gli stili ereditati da più proprietà. Per ulteriori informazioni sull'ereditarietà dello stile, vedere la pagina relativa agli [stili delle celle nel controllo DataGridView Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Formattazione e stile di base nel controllo DataGridView di Windows Form](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Uso della finestra di progettazione con il controllo DataGridView di Windows Form](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [Procedura: Creare un progetto di Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Procedura: Aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md)
