---
title: DataGrid
description: Informazioni sul modo in cui il controllo DataGrid consente di visualizzare e modificare i dati da origini diverse, ad esempio un database, una query LINQ o qualsiasi altra origine dati associabile.
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid column types [WPF]
- DataGrid scenarios [WPF]
- DataGrid control [WPF]
- controls [WPF], DataGrid
- DataGrid [WPF], common tasks for
- DataGrid [WPF], customizing the appearance of
- DataGrid columns [WPF], using
ms.assetid: bf89ea63-79b6-422b-bc9f-0485ad803216
ms.openlocfilehash: 3db49c12fcb363ef7f99e5c69beae09ab05addcf
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168313"
---
# <a name="datagrid"></a>DataGrid
Il <xref:System.Windows.Controls.DataGrid> controllo consente di visualizzare e modificare i dati da molte origini diverse, ad esempio da un database SQL, da una query LINQ o da qualsiasi altra origine dati associabile. Per altre informazioni, vedere [Cenni preliminari sulle origini del binding](../data/binding-sources-overview.md).  
  
 Le colonne possono visualizzare testo, controlli, ad esempio <xref:System.Windows.Controls.ComboBox> o qualsiasi altro contenuto WPF, ad esempio immagini, pulsanti o qualsiasi contenuto contenuto in un modello. È possibile usare un oggetto <xref:System.Windows.Controls.DataGridTemplateColumn> per visualizzare i dati definiti in un modello. Nella tabella seguente sono elencati i tipi di colonna forniti per impostazione predefinita.  
  
|Tipo di colonna generato|Tipo di dati|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid>è possibile personalizzare l'aspetto, ad esempio il tipo di carattere, il colore e le dimensioni della cella. <xref:System.Windows.Controls.DataGrid>supporta tutte le funzionalità di applicazione di stili e modelli di altri controlli WPF. <xref:System.Windows.Controls.DataGrid>include inoltre comportamenti predefiniti e personalizzabili per la modifica, l'ordinamento e la convalida.  
  
 Nella tabella seguente sono elencate alcune delle attività comuni per <xref:System.Windows.Controls.DataGrid> e la relativa modalità di esecuzione. Visualizzando l'API correlata, è possibile trovare altre informazioni e codice di esempio.  
  
|Scenario|Approccio|  
|--------------|--------------|  
|Colori di sfondo alternativi|Impostare la <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> proprietà su 2 o più, quindi assegnare un oggetto <xref:System.Windows.Media.Brush> alle <xref:System.Windows.Controls.DataGrid.RowBackground%2A> proprietà e <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> .|  
|Definire il comportamento di selezione delle celle e delle righe|Impostare le proprietà <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> e <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>.|  
|Personalizzare l'aspetto visivo di intestazioni, celle e righe|Applicare un nuovo oggetto <xref:System.Windows.Style> alle <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A> proprietà,, <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A> <xref:System.Windows.Controls.DataGrid.CellStyle%2A> o <xref:System.Windows.Controls.DataGrid.RowStyle%2A> .|  
|Imposta opzioni di ridimensionamento|Impostare le <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> proprietà,, <xref:System.Windows.FrameworkElement.MinHeight%2A> ,, <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A> o <xref:System.Windows.FrameworkElement.MinWidth%2A> . Per ulteriori informazioni, vedere [Opzioni di ridimensionamento nel controllo DataGrid](sizing-options-in-the-datagrid-control.md).|  
|Accedi agli elementi selezionati|Controllare la <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> proprietà per ottenere le celle selezionate e la <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> proprietà per ottenere le righe selezionate. Per altre informazioni, vedere <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Personalizzare le interazioni dell'utente finale|Impostare le <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A> <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A> proprietà,, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A> ,, <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A> <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A> e <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> .|  
|Annulla o modifica colonne generate automaticamente|Gestire l' <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> evento.|  
|Blocca una colonna|Impostare la <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> proprietà su 1 e spostare la colonna nella posizione più a sinistra impostando la <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> proprietà su 0.|  
|Utilizzare i dati XML come origine dati|Associare l'oggetto alla <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.DataGrid> query XPath che rappresenta la raccolta di elementi. Creare ogni colonna in <xref:System.Windows.Controls.DataGrid> . Associare ogni colonna impostando XPath sull'associazione alla query che ottiene la proprietà nell'origine dell'elemento. Per un esempio, vedere <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Procedura dettagliata: Visualizzare i dati di un database di SQL Server in un controllo DataGrid](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Viene descritto come configurare un nuovo progetto WPF, aggiungere un elemento Entity Framework, impostare l'origine e visualizzare i dati in un oggetto <xref:System.Windows.Controls.DataGrid> .|  
|[Procedura: Aggiungere dettagli di riga a un controllo DataGrid](how-to-add-row-details-to-a-datagrid-control.md)|Viene descritto come creare dettagli di riga per un oggetto <xref:System.Windows.Controls.DataGrid> .|  
|[Procedura: Implementare la convalida con il controllo DataGrid](how-to-implement-validation-with-the-datagrid-control.md)|Viene descritto come convalidare i valori in <xref:System.Windows.Controls.DataGrid> celle e righe e visualizzare il feedback di convalida.|  
|[Comportamento predefinito di tastiera e mouse nel controllo DataGrid](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Viene descritto come interagire con il <xref:System.Windows.Controls.DataGrid> controllo utilizzando la tastiera e il mouse.|  
|[Procedura: Raggruppare, ordinare e filtrare dati nel controllo DataGrid](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Viene descritto come visualizzare i dati in un <xref:System.Windows.Controls.DataGrid> in modi diversi raggruppando, ordinando e filtrando i dati.|  
|[Opzioni di ridimensionamento nel controllo DataGrid](sizing-options-in-the-datagrid-control.md)|Viene descritto come controllare il ridimensionamento assoluto e automatico in <xref:System.Windows.Controls.DataGrid> .|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataGrid>
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md)
- [Controlli](index.md)
- [Modello di contenuto WPF](wpf-content-model.md)
