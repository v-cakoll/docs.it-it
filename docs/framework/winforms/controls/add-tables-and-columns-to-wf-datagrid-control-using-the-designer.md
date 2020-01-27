---
title: Aggiungere tabelle e colonne al controllo DataGrid utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: fed7465fbe665b1945161653616e3a21640e0b2a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746258"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Procedura: aggiungere tabelle e colonne nel controllo DataGrid Windows Form mediante la finestra di progettazione

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

È possibile visualizzare i dati nel controllo <xref:System.Windows.Forms.DataGrid> Windows Forms nelle tabelle e nelle colonne creando <xref:System.Windows.Forms.DataGridTableStyle> oggetti e aggiungendoli all'oggetto <xref:System.Windows.Forms.GridTableStylesCollection>, a cui si accede tramite la proprietà <xref:System.Windows.Forms.DataGrid> del controllo <xref:System.Windows.Forms.DataGrid.TableStyles%2A>. In ogni stile di tabella viene visualizzato il contenuto di qualsiasi tabella dati specificata nella proprietà <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> della <xref:System.Windows.Forms.DataGridTableStyle>. Per impostazione predefinita, uno stile di tabella senza gli stili di colonna specificato visualizzerà tutte le colonne all'interno della tabella di dati. È possibile limitare le colonne presenti nella tabella aggiungendo <xref:System.Windows.Forms.DataGridColumnStyle> oggetti al <xref:System.Windows.Forms.GridColumnStylesCollection>, a cui si accede tramite la proprietà <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> di ogni <xref:System.Windows.Forms.DataGridTableStyle>.

Per le procedure riportate di seguito è necessario un progetto di **applicazione Windows** con un modulo che contenga un controllo <xref:System.Windows.Forms.DataGrid>. Per informazioni su come configurare tale progetto, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md). Per impostazione predefinita, in Visual Studio 2005 il controllo <xref:System.Windows.Forms.DataGrid> non è presente nella **casella degli strumenti**. Per informazioni sull'aggiunta, vedere [procedura: aggiungere elementi alla casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Per aggiungere una tabella al controllo DataGrid nella finestra di progettazione

1. Per visualizzare i dati nella tabella, è necessario innanzitutto associare il controllo <xref:System.Windows.Forms.DataGrid> a un set di dati. Per altre informazioni, vedere [procedura: associare il controllo DataGrid Windows Forms a un'origine dati usando la finestra di progettazione](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).

2. Selezionare la proprietà <xref:System.Windows.Forms.DataGrid.TableStyles%2A> del controllo <xref:System.Windows.Forms.DataGrid> nel Finestra Proprietà, quindi fare clic sul pulsante con i puntini di sospensione (![pulsante con i puntini di sospensione (...) nella Finestra Proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà per visualizzare l' **Editor della raccolta DataGridTableStyle**.

3. Nell'editor della raccolta fare clic su **Aggiungi** per inserire uno stile tabella.

4. Fare clic su **OK** per chiudere l'editor della raccolta, quindi riaprirlo facendo clic sul pulsante con i puntini di sospensione accanto alla proprietà <xref:System.Windows.Forms.DataGrid.TableStyles%2A>.

     Quando si riapre l'editor della raccolta, tutte le tabelle dati associato al controllo verranno visualizzate nell'elenco a discesa per la proprietà <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> dello stile della tabella.

5. Nella casella **membri** dell'editor della raccolta fare clic sullo stile della tabella.

6. Nella casella **Proprietà** dell'editor della raccolta selezionare il valore <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> per la tabella che si desidera visualizzare.

### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Per aggiungere una colonna al controllo DataGrid nella finestra di progettazione

1. Nella casella **membri** dell'editor della **raccolta DataGridTableStyle**Selezionare lo stile di tabella appropriato. Nella casella **Proprietà** dell'editor della raccolta, selezionare la raccolta di <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>, quindi fare clic sul pulsante con i puntini di sospensione (![pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà per visualizzare l' **Editor della raccolta DataGridColumnStyle**.

2. Nell'editor della raccolta fare clic su **Aggiungi** per inserire uno stile colonna oppure fare clic sulla freccia verso il basso accanto a **Aggiungi** per specificare un tipo di colonna.

     Nella casella di riepilogo a discesa è possibile selezionare il tipo <xref:System.Windows.Forms.DataGridTextBoxColumn> o <xref:System.Windows.Forms.DataGridBoolColumn>.

3. Fare clic su OK per chiudere l' **Editor della raccolta DataGridColumnStyle**, quindi riaprirlo facendo clic sul pulsante con i puntini di sospensione accanto alla proprietà <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>.

     Quando si riapre l'editor della raccolta, tutte le colonne di dati nella tabella dati associata verranno visualizzate nell'elenco a discesa per la proprietà <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> dello stile della colonna.

4. Nella casella **membri** dell'editor della raccolta fare clic sullo stile della colonna.

5. Nella casella **Proprietà** dell'editor della raccolta selezionare il valore <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> per la colonna che si desidera visualizzare.

## <a name="see-also"></a>Vedere anche

- [Controllo DataGrid](datagrid-control-windows-forms.md)
- [Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
