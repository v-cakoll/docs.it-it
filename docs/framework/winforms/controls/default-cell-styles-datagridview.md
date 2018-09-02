---
title: 'Procedura: impostare formati di dati e stili di cella predefiniti per il controllo DataGridView di Windows Form utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: adee6ab283fb7e2fe9bbfcda78c9692621407e9e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416988"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: impostare formati di dati e stili di cella predefiniti per il controllo DataGridView di Windows Form utilizzando la finestra di progettazione
Il <xref:System.Windows.Forms.DataGridView> controllo consente di specificare gli stili di cella predefiniti e formati di dati per l'intero controllo, per colonne specifiche, per le intestazioni di riga e colonna e per le righe per creare un effetto del libro mastro alterne della cella. Gli stili predefiniti impostati per l'intero controllo vengono sostituiti dagli stili predefiniti impostati per le colonne e righe alterne. Inoltre, gli stili impostati nel codice per le singole righe e celle sostituiranno gli stili predefiniti.  
  
 Per altre informazioni sugli stili di cella, vedere [stili della cella nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md). Per impostare gli stili per le righe alterne, vedere [procedura: impostare stili di righe alterne per il Windows Forms DataGridView controllo usando la finestra di progettazione](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md).  
  
 È anche possibile impostare gli stili utilizzando il <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> proprietà influiscono su tutte le righe che verranno aggiunti al controllo. Per altre informazioni sul modello di riga, vedere [procedura: usare il modello di riga per personalizzare le righe nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md).  
  
 Nelle procedure seguenti è richiesto un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto di applicazione Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>Per impostare gli stili predefiniti per tutte le celle nel controllo  
  
1.  Selezionare il <xref:System.Windows.Forms.DataGridView> controllo nella finestra di progettazione.  
  
2.  Nel **delle proprietà** finestra, fare clic sul pulsante con puntini di sospensione (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> proprietà. Il **Generatore CellStyle** verrà visualizzata la finestra di dialogo.  
  
3.  Definire lo stile, impostando le proprietà, usando il **Preview** riquadro per confermare le scelte effettuate.  
  
> [!NOTE]
>  Se gli stili di visualizzazione sono abilitati, intestazioni di riga e colonna (tranne che per il <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) vengono automaticamente uno stile che riflette il tema corrente, viene sottoposto a override il <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> e <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> i valori delle proprietà.  
>   
>  È possibile impostare gli stili di cella per la selezione multipla <xref:System.Windows.Forms.DataGridView> controlla usando la finestra di progettazione, ma solo se hanno valori identici per la proprietà di stile della cella da modificare. Se gli stili delle celle sono diversi per la proprietà, il **delle proprietà** windows del **Generatore CellStyle** nella finestra di dialogo sarà vuota.  
  
### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>Per impostare gli stili predefiniti per le celle nelle singole colonne  
  
1.  Fare doppio clic il <xref:System.Windows.Forms.DataGridView> controllare nella finestra di progettazione e scegliere **Modifica colonne**.  
  
2.  Selezionare una colonna dal **colonne selezionate** elenco.  
  
3.  Nel **le proprietà delle colonne** griglia, fare clic sul pulsante con puntini di sospensione (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> proprietà. Il **Generatore CellStyle** verrà visualizzata la finestra di dialogo.  
  
4.  Definire lo stile, impostando le proprietà, usando il **Preview** riquadro per confermare le scelte effettuate.  
  
### <a name="to-format-data-in-cells"></a>Per formattare i dati nelle celle  
  
1.  Usare una delle procedure precedenti per visualizzare un **Generatore CellStyle** nella finestra di dialogo correlate a una proprietà di stile di cella predefinito.  
  
2.  Nel **Generatore CellStyle** finestra di dialogo fare clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> proprietà. Il **stringa di formato** verrà visualizzata la finestra di dialogo.  
  
3.  Selezionare un tipo di formato, quindi modificare i dettagli del tipo (ad esempio, il numero di posizioni decimali da visualizzare), usando il **esempio** casella per confermare le scelte effettuate.  
  
4.  Se si desidera associare il <xref:System.Windows.Forms.DataGridView> controllo a un'origine dati che potrebbe contenere valori null, inserire il **valore Null** casella di testo. Questo valore viene visualizzato quando il valore della cella è uguale a un riferimento null (`Nothing` in Visual Basic) o <xref:System.DBNull.Value?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>  
 [Stili delle celle nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Form usando la finestra di progettazione](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 [Procedura: creare un progetto di applicazione Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Procedura: Aggiungere controlli a un Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
