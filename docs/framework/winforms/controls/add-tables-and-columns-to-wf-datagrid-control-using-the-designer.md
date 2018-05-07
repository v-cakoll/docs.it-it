---
title: 'Procedura: aggiungere tabelle e colonne nel controllo DataGrid Windows Form mediante la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: 4b29a3040415cce8fad27abf9bf46aa3d3e14b4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Procedura: aggiungere tabelle e colonne nel controllo DataGrid Windows Form mediante la finestra di progettazione
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 È possibile visualizzare i dati in Windows Form <xref:System.Windows.Forms.DataGrid> controllo in tabelle e colonne creando <xref:System.Windows.Forms.DataGridTableStyle> oggetti e aggiungendoli al <xref:System.Windows.Forms.GridTableStylesCollection> oggetto, che è possibile accedere mediante il <xref:System.Windows.Forms.DataGrid> del controllo <xref:System.Windows.Forms.DataGrid.TableStyles%2A> proprietà. Ogni stile tabella viene visualizzato il contenuto di qualsiasi tabella di dati specificata nella <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà del <xref:System.Windows.Forms.DataGridTableStyle>. Per impostazione predefinita, uno stile tabella senza gli stili di colonna specificati visualizzerà tutte le colonne all'interno della tabella di dati. È possibile limitare le colonne della tabella vengono visualizzati aggiungendo <xref:System.Windows.Forms.DataGridColumnStyle> oggetti per il <xref:System.Windows.Forms.GridColumnStylesCollection>, cui si accede mediante la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> proprietà di ogni <xref:System.Windows.Forms.DataGridTableStyle>.  
  
 Le procedure seguenti richiedono un **applicazione Windows** progetto con un modulo che contiene un <xref:System.Windows.Forms.DataGrid> controllo. Per informazioni su come configurare questo tipo di progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). Per impostazione predefinita in [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> controllo non sarà il **della casella degli strumenti**. Per informazioni su come aggiungerlo, vedere [procedura: aggiungere elementi alla casella degli strumenti](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Per aggiungere una tabella per il controllo DataGrid nella finestra di progettazione  
  
1.  Per visualizzare i dati nella tabella, è innanzitutto necessario associare il <xref:System.Windows.Forms.DataGrid> controllo a un set di dati. Per ulteriori informazioni, vedere [procedura: associare il controllo DataGrid Windows Form a un'origine dati usando la finestra di progettazione](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).  
  
2.  Selezionare il <xref:System.Windows.Forms.DataGrid> del controllo <xref:System.Windows.Forms.DataGrid.TableStyles%2A> proprietà nella finestra Proprietà, quindi fare clic sul pulsante con puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto a la proprietà per visualizzare il **raccolta DataGridTableStyle**.  
  
3.  Nell'editor della raccolta, fare clic su **Aggiungi** per inserire uno stile di tabella.  
  
4.  Fare clic su **OK** per chiudere l'editor della raccolta, quindi riaprirlo facendo clic sul pulsante con i puntini di sospensione accanto al <xref:System.Windows.Forms.DataGrid.TableStyles%2A> proprietà.  
  
     Quando si riapre l'editor della raccolta, tutte le tabelle dati associate al controllo verranno visualizzato nell'elenco a discesa per la <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà dello stile di tabella.  
  
5.  Nel **membri** finestra dell'editor della raccolta, selezionare lo stile di tabella.  
  
6.  Nel **proprietà** casella dell'editor della raccolta, selezionare il <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> valore per la tabella che si desidera visualizzare.  
  
### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Per aggiungere una colonna al controllo DataGrid nella finestra di progettazione  
  
1.  Nel **membri** casella della finestra il **raccolta DataGridTableStyle**, selezionare lo stile tabella appropriata. Nel **proprietà** casella dell'editor della raccolta, selezionare il <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> insieme e quindi fare clic sul pulsante con puntini di sospensione (![schermata VisualStudioEllipsesButton] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) accanto alla proprietà per visualizzare il **raccolta DataGridColumnStyle**.  
  
2.  Nell'editor della raccolta, fare clic su **Aggiungi** per inserire uno stile di colonna o fare clic sulla freccia rivolta verso il basso accanto a **Aggiungi** per specificare un tipo di colonna.  
  
     Nella casella di riepilogo a discesa, è possibile selezionare il <xref:System.Windows.Forms.DataGridTextBoxColumn> o <xref:System.Windows.Forms.DataGridBoolColumn> tipo.  
  
3.  Fare clic su OK per chiudere la **raccolta DataGridColumnStyle**e quindi riaprirlo facendo clic sul pulsante con i puntini di sospensione accanto al <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> proprietà.  
  
     Quando si riapre l'editor della raccolta, le colonne di dati nella tabella dati associata verranno visualizzata nell'elenco a discesa per la <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> proprietà dello stile di colonna.  
  
4.  Nel **membri** finestra dell'editor della raccolta, selezionare lo stile di colonna.  
  
5.  Nel **proprietà** casella dell'editor della raccolta, selezionare il <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> valore per la colonna che si desidera visualizzare.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
