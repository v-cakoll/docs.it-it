---
title: 'Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: 079b4121c3f9e5c55e003b089f85cd08a5bae5d2
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2019
ms.locfileid: "56304414"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form usando la finestra di progettazione

> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 È possibile visualizzare i dati nei moduli di Windows <xref:System.Windows.Forms.DataGrid> controllo in tabelle e colonne creando <xref:System.Windows.Forms.DataGridTableStyle> oggetti e ad aggiungerle nel <xref:System.Windows.Forms.GridTableStylesCollection> oggetto, accessibile tramite il <xref:System.Windows.Forms.DataGrid> del controllo <xref:System.Windows.Forms.DataGrid.TableStyles%2A> proprietà. Ogni stile tabella viene visualizzato il contenuto di qualsiasi tabella dati specificata nel <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà del <xref:System.Windows.Forms.DataGridTableStyle>. Per impostazione predefinita, uno stile di tabella senza gli stili di colonna specificati visualizzerà tutte le colonne all'interno della tabella di dati. È possibile limitare le colonne della tabella vengono visualizzati aggiungendo <xref:System.Windows.Forms.DataGridColumnStyle> gli oggetti per il <xref:System.Windows.Forms.GridColumnStylesCollection>, accessibile tramite il <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> proprietà della ognuno <xref:System.Windows.Forms.DataGridTableStyle>.  
  
 Nelle procedure seguenti è richiesto un **applicazione di Windows** progetto con un modulo che contiene un <xref:System.Windows.Forms.DataGrid> controllo. Per informazioni su come configurare un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). Per impostazione predefinita in Visual Studio 2005, il <xref:System.Windows.Forms.DataGrid> controllo non è nel **casella degli strumenti**. Per informazioni su come aggiungerlo, vedere [come: Aggiungere elementi alla casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Per aggiungere una tabella al controllo DataGrid nella finestra di progettazione  
  
1.  Per visualizzare i dati nella tabella, è innanzitutto necessario associare il <xref:System.Windows.Forms.DataGrid> controllo a un set di dati. Per altre informazioni, vedere [Procedura: Associare il controllo DataGrid di Windows Form a un'origine dati tramite la finestra di progettazione](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).  
  
2.  Selezionare il <xref:System.Windows.Forms.DataGrid> del controllo <xref:System.Windows.Forms.DataGrid.TableStyles%2A> proprietà nella finestra Proprietà, quindi fare clic sul pulsante con puntini di sospensione (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto a la proprietà da visualizzare il **raccolta DataGridTableStyle**.  
  
3.  Nell'editor della raccolta, fare clic su **Add** per inserire uno stile di tabella.  
  
4.  Fare clic su **OK** per chiudere l'editor della raccolta e quindi riaprirlo facendo clic sul pulsante con puntini di sospensione accanto al <xref:System.Windows.Forms.DataGrid.TableStyles%2A> proprietà.  
  
     Quando si riapre l'editor della raccolta, tutte le tabelle di dati associate al controllo verranno visualizzato nell'elenco a discesa per il <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà dello stile di tabella.  
  
5.  Nel **membri** finestra dell'editor della raccolta, scegliere lo stile di tabella.  
  
6.  Nel **delle proprietà** finestra dell'editor della raccolta, selezionare il <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> valore per la tabella che si desidera visualizzare.  
  
### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Per aggiungere una colonna per il controllo DataGrid nella finestra di progettazione  
  
1.  Nel **membri** finestra di **raccolta DataGridTableStyle**, selezionare lo stile tabella appropriata. Nel **delle proprietà** finestra dell'editor della raccolta, selezionare la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> insieme e quindi fare clic sul pulsante con puntini di sospensione (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) accanto alla proprietà per visualizzare il **raccolta DataGridColumnStyle**.  
  
2.  Nell'editor della raccolta, fare clic su **Add** per inserire uno stile colonna o fare clic sulla freccia in giù accanto a **Add** per specificare un tipo di colonna.  
  
     Nella casella di riepilogo a discesa, è possibile selezionare i <xref:System.Windows.Forms.DataGridTextBoxColumn> o <xref:System.Windows.Forms.DataGridBoolColumn> tipo.  
  
3.  Fare clic su OK per chiudere la **raccolta DataGridColumnStyle**, quindi aprirlo facendo clic sul pulsante con puntini di sospensione accanto al <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> proprietà.  
  
     Quando si riapre l'editor della raccolta, tutte le colonne di dati della tabella di dati associati verranno visualizzati nell'elenco a discesa per il <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> proprietà dello stile di colonna.  
  
4.  Nel **membri** finestra dell'editor della raccolta, scegliere lo stile della colonna.  
  
5.  Nel **delle proprietà** finestra dell'editor della raccolta, selezionare il <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> valore per la colonna che si desidera visualizzare.  
  
## <a name="see-also"></a>Vedere anche
- [Controllo DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
