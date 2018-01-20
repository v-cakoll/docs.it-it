---
title: 'Procedura: impostare formati di dati e stili di cella predefiniti per il controllo DataGridView di Windows Form utilizzando la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65f876742526d13093a852e99f4e6a069c3fba47
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: impostare formati di dati e stili di cella predefiniti per il controllo DataGridView di Windows Form utilizzando la finestra di progettazione
Il <xref:System.Windows.Forms.DataGridView> controllo consente di specificare gli stili di cella predefiniti e formati di dati per l'intero controllo, per colonne specifiche, per le intestazioni di riga e colonna e per le righe per creare un effetto registro alterne. Gli stili predefiniti impostati per l'intero controllo vengono sostituiti dagli stili predefiniti impostati per le colonne e righe alterne. Inoltre, gli stili impostati nel codice per le singole righe e le celle sostituiranno gli stili predefiniti.  
  
 Per ulteriori informazioni sugli stili di cella, vedere [stili della cella nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md). Per impostare gli stili per le righe alterne, vedere [procedura: impostare stili di righe alterne per il controllo Windows Form DataGridView usando la finestra di progettazione](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md).  
  
 È inoltre possibile impostare gli stili utilizzando il <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> proprietà per controllare tutte le righe che verranno aggiunti al controllo. Per ulteriori informazioni sul modello di riga, vedere [procedura: utilizzare il modello di riga per personalizzare le righe nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md).  
  
 Le procedure seguenti richiedono un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo. Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>Per impostare gli stili predefiniti per tutte le celle nel controllo  
  
1.  Selezionare il <xref:System.Windows.Forms.DataGridView> controllo nella finestra di progettazione.  
  
2.  Nel **proprietà** finestra, fare clic sul pulsante con i puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, o <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> proprietà. Il **Generatore CellStyle** viene visualizzata la finestra di dialogo.  
  
3.  Definire lo stile impostando le proprietà, utilizzando il **anteprima** riquadro per confermare le scelte.  
  
> [!NOTE]
>  Se sono abilitati gli stili di visualizzazione, le intestazioni di riga e colonna (ad eccezione del <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) viene automaticamente applicato uno stile dal tema corrente, si esegue l'override di <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> e <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> i valori delle proprietà.  
>   
>  È possibile impostare gli stili di cella per la selezione multipla <xref:System.Windows.Forms.DataGridView> controlla utilizzando la finestra di progettazione, ma solo se hanno valori identici per la proprietà di stile di cella che si desidera modificare. Se uno o più stili differiscono per la proprietà, il **proprietà** windows del **Generatore CellStyle** la finestra di dialogo sarà vuota.  
  
### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>Per impostare gli stili predefiniti per le celle nelle singole colonne  
  
1.  Fare doppio clic su di <xref:System.Windows.Forms.DataGridView> controllare nella finestra di progettazione e scegliere **Modifica colonne**.  
  
2.  Selezionare una colonna dal **colonne selezionate** elenco.  
  
3.  Nel **proprietà colonna** griglia, fare clic sul pulsante con i puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> proprietà. Il **Generatore CellStyle** viene visualizzata la finestra di dialogo.  
  
4.  Definire lo stile impostando le proprietà, utilizzando il **anteprima** riquadro per confermare le scelte.  
  
### <a name="to-format-data-in-cells"></a>Per formattare i dati delle celle  
  
1.  Utilizzare una delle procedure precedenti per visualizzare un **Generatore CellStyle** la finestra di dialogo correlate a una proprietà di stile di cella predefinito.  
  
2.  Nel **Generatore CellStyle** finestra di dialogo fare clic sul pulsante con i puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> proprietà. Il **stringa di formato** viene visualizzata la finestra di dialogo.  
  
3.  Selezionare un tipo di formato, quindi modificare i dettagli del tipo (ad esempio il numero di posizioni decimali da visualizzare), utilizzando il **esempio** casella per confermare le scelte.  
  
4.  Se si desidera associare il <xref:System.Windows.Forms.DataGridView> controllo a un'origine dati che è probabile che contengono valori null, compilare il **valore Null** casella di testo. Questo valore viene visualizzato quando il valore della cella è uguale a un riferimento null (`Nothing` in Visual Basic) o <xref:System.DBNull.Value?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>  
 [Stili delle celle nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Form usando la finestra di progettazione](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 [Procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Procedura: Aggiungere controlli a un Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
