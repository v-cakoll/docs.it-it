---
title: 'Procedura: Aggiungere tabelle e colonne al controllo DataGrid di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: d11c4f7e4cdfb597477bb99f38612ed648849f20
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040045"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Procedura: Aggiungere tabelle e colonne al controllo DataGrid di Windows Forms usando la finestra di progettazione

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

È possibile visualizzare i dati nel controllo <xref:System.Windows.Forms.DataGrid> Windows Forms in tabelle e colonne creando <xref:System.Windows.Forms.DataGridTableStyle> oggetti <xref:System.Windows.Forms.GridTableStylesCollection> e aggiungendoli all'oggetto <xref:System.Windows.Forms.DataGrid.TableStyles%2A> , a cui si accede tramite la <xref:System.Windows.Forms.DataGrid> proprietà del controllo. In ogni stile di tabella viene visualizzato il contenuto di qualsiasi tabella dati specificata <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> nella proprietà <xref:System.Windows.Forms.DataGridTableStyle>di. Per impostazione predefinita, uno stile di tabella senza gli stili di colonna specificato visualizzerà tutte le colonne all'interno della tabella di dati. È possibile limitare le colonne <xref:System.Windows.Forms.DataGridColumnStyle> presenti nella tabella aggiungendo oggetti all'oggetto <xref:System.Windows.Forms.GridColumnStylesCollection>, a cui si accede tramite la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> proprietà di ognuno <xref:System.Windows.Forms.DataGridTableStyle>di essi.

Le procedure riportate di seguito richiedono un progetto di **applicazione Windows** con <xref:System.Windows.Forms.DataGrid> un modulo che contiene un controllo. Per informazioni su come configurare tale progetto, vedere [procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md). Per impostazione predefinita, in Visual Studio 2005 <xref:System.Windows.Forms.DataGrid> il controllo non si trova nella **casella degli strumenti**. Per informazioni sull'aggiunta, vedere [procedura: Consente di aggiungere elementi alla](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))casella degli strumenti.

### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Per aggiungere una tabella al controllo DataGrid nella finestra di progettazione

1. Per visualizzare i dati nella tabella, è innanzitutto necessario associare il <xref:System.Windows.Forms.DataGrid> controllo a un set di dati. Per altre informazioni, vedere [Procedura: Associare il controllo DataGrid Windows Forms a un'origine dati utilizzando la finestra](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)di progettazione.

2. Selezionare la <xref:System.Windows.Forms.DataGrid> <xref:System.Windows.Forms.DataGrid.TableStyles%2A> proprietà del controllo nella finestra Proprietà, quindi![fare clic sul pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà per visualizzare **Editor della raccolta DataGridTableStyle**.

3. Nell'editor della raccolta fare clic su **Aggiungi** per inserire uno stile tabella.

4. Fare clic su **OK** per chiudere l'editor della raccolta, quindi riaprirlo facendo clic sul pulsante con i <xref:System.Windows.Forms.DataGrid.TableStyles%2A> puntini di sospensione accanto alla proprietà.

     Quando si riapre l'editor della raccolta, tutte le tabelle dati associato al controllo verranno visualizzate nell'elenco a discesa per la <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà dello stile della tabella.

5. Nella casella **membri** dell'editor della raccolta fare clic sullo stile della tabella.

6. Nella casella **Proprietà** dell'editor della raccolta selezionare il <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> valore della tabella che si desidera visualizzare.

### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Per aggiungere una colonna al controllo DataGrid nella finestra di progettazione

1. Nella casella **membri** dell'editor della **raccolta DataGridTableStyle**Selezionare lo stile di tabella appropriato. Nella casella **Proprietà** dell'editor della raccolta, selezionare la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> raccolta, quindi fare clic sul pulsante con i puntini di sospensione (![pulsante con i puntini di sospensione (...](./media/visual-studio-ellipsis-button.png)) nella finestra proprietà di Visual Studio.) accanto alla proprietà visualizzare l' **Editor della raccolta DataGridColumnStyle**.

2. Nell'editor della raccolta fare clic su **Aggiungi** per inserire uno stile colonna oppure fare clic sulla freccia verso il basso accanto a **Aggiungi** per specificare un tipo di colonna.

     Nella casella di riepilogo a discesa è possibile selezionare il <xref:System.Windows.Forms.DataGridTextBoxColumn> tipo o. <xref:System.Windows.Forms.DataGridBoolColumn>

3. Fare clic su OK per chiudere l' **Editor della raccolta DataGridColumnStyle**, quindi riaprirlo facendo clic sul pulsante con i <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> puntini di sospensione accanto alla proprietà.

     Quando si riapre l'editor della raccolta, tutte le colonne di dati nella tabella di dati associata verranno visualizzate nell'elenco a discesa per <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> la proprietà dello stile della colonna.

4. Nella casella **membri** dell'editor della raccolta fare clic sullo stile della colonna.

5. Nella casella **Proprietà** dell'editor della raccolta selezionare il <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> valore per la colonna che si desidera visualizzare.

## <a name="see-also"></a>Vedere anche

- [Controllo DataGrid](datagrid-control-windows-forms.md)
- [Procedura: Eliminare o nascondere colonne nel controllo Windows Forms DataGrid](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
