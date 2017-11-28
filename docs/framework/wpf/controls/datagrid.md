---
title: DataGrid
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGrid column types [WPF]
- DataGrid scenarios [WPF]
- DataGrid control [WPF]
- controls [WPF], DataGrid
- DataGrid [WPF], common tasks for
- DataGrid [WPF], customizing the appearance of
- DataGrid columns [WPF], using
ms.assetid: bf89ea63-79b6-422b-bc9f-0485ad803216
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63eb1b7aec0c65192f67035fc7bc624fa1d2ae81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="datagrid"></a>DataGrid
Il <xref:System.Windows.Controls.DataGrid> controllo consente di visualizzare e modificare i dati da molte origini diverse, ad esempio da un database SQL, query LINQ o qualsiasi altra origine dati associabili. Per altre informazioni, vedere [Cenni preliminari sulle origini del binding](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
 Le colonne è possono visualizzare il testo, controlli, ad esempio un <xref:System.Windows.Controls.ComboBox>, o qualsiasi altro contenuto WPF, quali immagini, pulsanti o qualsiasi contenuto presente in un modello. È possibile utilizzare un <xref:System.Windows.Controls.DataGridTemplateColumn> per visualizzare i dati definiti in un modello. Nella tabella seguente sono elencati i tipi di colonna che vengono forniti per impostazione predefinita.  
  
|Tipo di colonna generata|Tipo di dati|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid>è possibile personalizzare l'aspetto, ad esempio celle carattere, colore e dimensioni. <xref:System.Windows.Controls.DataGrid>supporta tutte le funzionalità di stili e modelli di altri controlli WPF. <xref:System.Windows.Controls.DataGrid>include anche i comportamenti predefiniti e personalizzabili per la modifica, l'ordinamento e la convalida.  
  
 Nella tabella seguente sono elencate alcune delle attività comuni per <xref:System.Windows.Controls.DataGrid> e viene descritto come eseguirle. Visualizzando l'API correlata, è possibile trovare ulteriori informazioni e codice di esempio.  
  
|Scenario|Approccio|  
|--------------|--------------|  
|Colori di sfondo alternativi|Impostare il <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> proprietà a 2 o più e quindi assegnare un <xref:System.Windows.Media.Brush> per il <xref:System.Windows.Controls.DataGrid.RowBackground%2A> e <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> proprietà.|  
|Definire il comportamento di selezione di celle e righe|Impostare le proprietà <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> e <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>.|  
|Personalizzare l'aspetto visivo delle intestazioni di celle e righe|Applicare un nuovo <xref:System.Windows.Style> per il <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.CellStyle%2A>, o <xref:System.Windows.Controls.DataGrid.RowStyle%2A> proprietà.|  
|Impostare opzioni di ridimensionamento|Impostare il <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, o <xref:System.Windows.FrameworkElement.MinWidth%2A> proprietà. Per ulteriori informazioni, vedere [opzioni di ridimensionamento nel controllo DataGrid](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md).|  
|Accedere agli elementi selezionati|Controllare il <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> proprietà da ottenere le celle selezionate e <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> proprietà da ottenere le righe selezionate. Per altre informazioni, vedere <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Personalizzare le interazioni dell'utente finale|Impostare il <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A>, e <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> proprietà.|  
|Annullare o modificare le colonne generate automaticamente|Gestire il <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> evento.|  
|Bloccare una colonna|Impostare il <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> proprietà su 1 e spostare la colonna nella posizione più a sinistra mediante l'impostazione di <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> proprietà su 0.|  
|Utilizzare i dati XML come origine dati|Associare il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> sul <xref:System.Windows.Controls.DataGrid> alla query XPath che rappresenta la raccolta di elementi. Creare ogni colonna di <xref:System.Windows.Controls.DataGrid>. Associare ogni colonna impostando XPath nell'associazione per la query che ottiene la proprietà sull'origine dell'elemento. Per un esempio, vedere <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Procedura dettagliata: Visualizzazione di dati di un database di SQL Server in un controllo DataGrid](../../../../docs/framework/wpf/controls/walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Viene descritto come configurare un nuovo progetto WPF, aggiungere un elemento Entity Framework, impostare l'origine e visualizzare i dati in un <xref:System.Windows.Controls.DataGrid>.|  
|[Procedura: Aggiungere dettagli di riga un controllo DataGrid](../../../../docs/framework/wpf/controls/how-to-add-row-details-to-a-datagrid-control.md)|Viene descritto come creare i dettagli delle righe per un <xref:System.Windows.Controls.DataGrid>.|  
|[Procedura: Implementare la convalida con il controllo DataGrid](../../../../docs/framework/wpf/controls/how-to-implement-validation-with-the-datagrid-control.md)|Viene descritto come convalidare i valori in <xref:System.Windows.Controls.DataGrid> celle e righe e i suggerimenti di convalida visualizzato.|  
|[Comportamento predefinito di tastiera e mouse nel controllo DataGrid](../../../../docs/framework/wpf/controls/default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Viene descritto come interagire con il <xref:System.Windows.Controls.DataGrid> controllo usando la tastiera e mouse.|  
|[Procedura: Raggruppare, ordinare e filtrare dati nel controllo DataGrid](../../../../docs/framework/wpf/controls/how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Viene descritto come visualizzare i dati in un <xref:System.Windows.Controls.DataGrid> in modi diversi per il raggruppamento, ordinamento e filtro dei dati.|  
|[Opzioni di ridimensionamento nel controllo DataGrid](../../../../docs/framework/wpf/controls/sizing-options-in-the-datagrid-control.md)|Viene descritto come controllare il ridimensionamento automatico e assoluto nel <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.DataGrid>  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Panoramica sui modelli di dati](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [Controlli](../../../../docs/framework/wpf/controls/index.md)  
 [Modello di contenuto WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md)
