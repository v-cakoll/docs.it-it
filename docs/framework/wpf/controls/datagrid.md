---
title: DataGrid
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
ms.openlocfilehash: dda712d58a4ff956de074ecd416402ba0aece5f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197152"
---
# <a name="datagrid"></a>DataGrid
Il <xref:System.Windows.Controls.DataGrid> controllo consente di visualizzare e modificare i dati da molte origini diverse, ad esempio da un database SQL, query LINQ o qualsiasi altra origine dati associabili. Per altre informazioni, vedere [Cenni preliminari sulle origini del binding](../data/binding-sources-overview.md).  
  
 Le colonne possono visualizzare testo, controlli, ad esempio un <xref:System.Windows.Controls.ComboBox>, o qualsiasi altro contenuto WPF, ad esempio immagini, pulsanti o qualsiasi contenuto presente in un modello. È possibile usare un <xref:System.Windows.Controls.DataGridTemplateColumn> per visualizzare i dati definiti in un modello. Nella tabella seguente elenca i tipi di colonna vengono forniti per impostazione predefinita.  
  
|Tipo di colonna generato|Tipo di dati|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid> può essere personalizzato nell'aspetto, quali celle carattere, colore e dimensioni. <xref:System.Windows.Controls.DataGrid> supporta tutte le funzionalità di stili e modelli di altri controlli WPF. <xref:System.Windows.Controls.DataGrid> include anche i comportamenti predefiniti e personalizzabili per la modifica, l'ordinamento e la convalida.  
  
 Nella tabella seguente sono elencate alcune delle attività comuni per <xref:System.Windows.Controls.DataGrid> e su come eseguire queste attività. Visualizzando la API correlato, è possibile trovare altre informazioni e codice di esempio.  
  
|Scenario|Approccio|  
|--------------|--------------|  
|Alternanza di colori di sfondo|Impostare il <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> proprietà a 2 o più e quindi assegnare un <xref:System.Windows.Media.Brush> per il <xref:System.Windows.Controls.DataGrid.RowBackground%2A> e <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> proprietà.|  
|Definire il comportamento di selezione di celle e righe|Impostare le proprietà <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> e <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>.|  
|Personalizzare l'aspetto visivo di intestazioni, le celle e righe|Applicare un nuovo <xref:System.Windows.Style> per il <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>, <xref:System.Windows.Controls.DataGrid.CellStyle%2A>, o <xref:System.Windows.Controls.DataGrid.RowStyle%2A> proprietà.|  
|Set di opzioni di ridimensionamento|Impostare il <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, o <xref:System.Windows.FrameworkElement.MinWidth%2A> proprietà. Per altre informazioni, vedere [opzioni di ridimensionamento nel controllo DataGrid](sizing-options-in-the-datagrid-control.md).|  
|Accedere agli elementi selezionati|Verificare i <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> proprietà da ottenere le celle selezionate e <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> proprietà da ottenere le righe selezionate. Per altre informazioni, vedere <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Personalizzare le interazioni dell'utente finale|Impostare il <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>, <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A>, e <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> proprietà.|  
|Annullare o modificare le colonne generate automaticamente|Gestire il <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> evento.|  
|Bloccare una colonna|Impostare il <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> proprietà su 1 e spostare la colonna nella posizione più a sinistra mediante l'impostazione di <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> proprietà su 0.|  
|Utilizzo di dati XML come origine dati|Associare il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> nella <xref:System.Windows.Controls.DataGrid> alla query XPath che rappresenta la raccolta di elementi. Creare ogni colonna di <xref:System.Windows.Controls.DataGrid>. Associare ogni colonna impostando il XPath dell'associazione alla query che ottiene la proprietà sull'origine dell'elemento. Per un esempio, vedere <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Procedura dettagliata: Visualizzare i dati da un Database SQL Server in un controllo DataGrid](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Viene descritto come configurare un nuovo progetto WPF, aggiungere un elemento Entity Framework, impostare l'origine e visualizzare i dati in un <xref:System.Windows.Controls.DataGrid>.|  
|[Procedura: Aggiungere i dettagli della riga a un controllo DataGrid](how-to-add-row-details-to-a-datagrid-control.md)|Viene descritto come creare i dettagli delle righe per un <xref:System.Windows.Controls.DataGrid>.|  
|[Procedura: Implementare la convalida con il controllo DataGrid](how-to-implement-validation-with-the-datagrid-control.md)|Viene descritto come convalidare i valori in <xref:System.Windows.Controls.DataGrid> celle e righe e i suggerimenti di convalida visualizzato.|  
|[Comportamento predefinito di tastiera e mouse nel controllo DataGrid](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Viene descritto come interagire con il <xref:System.Windows.Controls.DataGrid> controllo usando la tastiera e mouse.|  
|[Procedura: Raggruppare, ordinare e filtrare dati nel controllo DataGrid](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Viene descritto come visualizzare i dati in un <xref:System.Windows.Controls.DataGrid> in modi diversi per il raggruppamento, ordinamento e filtro dei dati.|  
|[Opzioni di ridimensionamento nel controllo DataGrid](sizing-options-in-the-datagrid-control.md)|Viene descritto come controllare il ridimensionamento automatico e assoluto nel <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataGrid>
- [Applicazione di stili e modelli](styling-and-templating.md)
- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Panoramica sui modelli di dati](../data/data-templating-overview.md)
- [Controlli](index.md)
- [Modello di contenuto WPF](wpf-content-model.md)
