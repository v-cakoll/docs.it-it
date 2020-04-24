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
ms.openlocfilehash: cdf4bfff8182b62d55f56b823c7ff129de4f9f1c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646124"
---
# <a name="datagrid"></a>DataGrid
Il <xref:System.Windows.Controls.DataGrid> controllo consente di visualizzare e modificare i dati da molte origini diverse, ad esempio da un database SQL, una query LINQ o qualsiasi altra origine dati associabile. Per altre informazioni, vedere [Cenni preliminari sulle origini del binding](../data/binding-sources-overview.md).  
  
 Le colonne possono visualizzare testo, <xref:System.Windows.Controls.ComboBox>controlli, ad esempio un oggetto , o qualsiasi altro contenuto WPFWPF, ad esempio immagini, pulsanti o qualsiasi contenuto contenuto in un modello. È possibile <xref:System.Windows.Controls.DataGridTemplateColumn> utilizzare un oggetto per visualizzare i dati definiti in un modello. Nella tabella seguente sono elencati i tipi di colonna forniti per impostazione predefinita.  
  
|Tipo di colonna generato|Tipo di dati|  
|---------------------------|---------------|  
|<xref:System.Windows.Controls.DataGridTextColumn>|<xref:System.String>|  
|<xref:System.Windows.Controls.DataGridCheckBoxColumn>|<xref:System.Boolean>|  
|<xref:System.Windows.Controls.DataGridComboBoxColumn>|<xref:System.Enum>|  
|<xref:System.Windows.Controls.DataGridHyperlinkColumn>|<xref:System.Uri>|  
  
 <xref:System.Windows.Controls.DataGrid>può essere personalizzato nell'aspetto, ad esempio il tipo di carattere della cella, il colore e la dimensione. <xref:System.Windows.Controls.DataGrid>supporta tutte le funzionalità di stili e modelli di altri controlli WPFWPF. <xref:System.Windows.Controls.DataGrid>include anche comportamenti predefiniti e personalizzabili per la modifica, l'ordinamento e la convalida.  
  
 Nella tabella seguente sono elencate <xref:System.Windows.Controls.DataGrid> alcune delle attività comuni per e come eseguirle. Visualizzando l'API correlata, è possibile trovare ulteriori informazioni e codice di esempio.  
  
|Scenario|Approccio|  
|--------------|--------------|  
|Colori di sfondo alternati|Impostare <xref:System.Windows.Controls.ItemsControl.AlternationIndex%2A> la proprietà su 2 o <xref:System.Windows.Media.Brush> più, quindi assegnare a alle proprietà <xref:System.Windows.Controls.DataGrid.RowBackground%2A> e <xref:System.Windows.Controls.DataGrid.AlternatingRowBackground%2A> .|  
|Definire il comportamento di selezione di celle e righe|Impostare le proprietà <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> e <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>.|  
|Personalizzare l'aspetto visivo di intestazioni, celle e righe|Applicare una <xref:System.Windows.Style> nuova <xref:System.Windows.Controls.DataGrid.ColumnHeaderStyle%2A> <xref:System.Windows.Controls.DataGrid.RowHeaderStyle%2A>alle <xref:System.Windows.Controls.DataGrid.CellStyle%2A>proprietà <xref:System.Windows.Controls.DataGrid.RowStyle%2A> , , o .|  
|Impostare le opzioni di ridimensionamento|Impostare <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A>le <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.Width%2A>proprietà <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MinWidth%2A> , , , o . Per ulteriori informazioni, vedere [Opzioni di ridimensionamento nel controllo DataGrid](sizing-options-in-the-datagrid-control.md).|  
|Accedere agli elementi selezionati|Controllare <xref:System.Windows.Controls.DataGrid.SelectedCells%2A> la proprietà per ottenere <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems%2A> le celle selezionate e la proprietà per ottenere le righe selezionate. Per altre informazioni, vedere <xref:System.Windows.Controls.DataGrid.SelectedCells%2A>.|  
|Personalizzare le interazioni con l'utente finale|Impostare <xref:System.Windows.Controls.DataGrid.CanUserAddRows%2A> <xref:System.Windows.Controls.DataGrid.CanUserDeleteRows%2A>le <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A> <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A>proprietà <xref:System.Windows.Controls.DataGrid.CanUserResizeRows%2A>, <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A> , , , e .|  
|Annullare o modificare le colonne generate automaticamente|Gestire <xref:System.Windows.Controls.DataGrid.AutoGeneratingColumn> l'evento.|  
|Bloccare una colonna|Impostare <xref:System.Windows.Controls.DataGrid.FrozenColumnCount%2A> la proprietà su 1 e spostare la <xref:System.Windows.Controls.DataGridColumn.DisplayIndex%2A> colonna nella posizione più a sinistra impostando la proprietà su 0.|  
|Usare i dati XML come origine datiUse XML data as the data source|Associare <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> l'oggetto <xref:System.Windows.Controls.DataGrid> alla query XPath che rappresenta la raccolta di elementi. Creare ogni colonna <xref:System.Windows.Controls.DataGrid>nel file . Associare ogni colonna impostando l'XPath nell'associazione alla query che ottiene la proprietà nell'origine dell'elemento. Per un esempio, vedere <xref:System.Windows.Controls.DataGridTextColumn>.|  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Procedura dettagliata: Visualizzazione di dati di un database di SQL Server in un controllo DataGrid](walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control.md)|Viene descritto come impostare un nuovo progetto WPF, aggiungere un elemento Entity Framework, impostare l'origine e visualizzare i dati in un <xref:System.Windows.Controls.DataGrid>oggetto .|  
|[Procedura: aggiungere dettagli di riga un controllo DataGrid](how-to-add-row-details-to-a-datagrid-control.md)|Viene descritto come creare i <xref:System.Windows.Controls.DataGrid>dettagli delle righe per un oggetto .|  
|[Procedura: Implementare la convalida con il controllo DataGrid](how-to-implement-validation-with-the-datagrid-control.md)|Viene descritto come convalidare i valori in <xref:System.Windows.Controls.DataGrid> celle e righe e visualizzare il feedback di convalida.|  
|[Comportamento predefinito di tastiera e mouse nel controllo DataGrid](default-keyboard-and-mouse-behavior-in-the-datagrid-control.md)|Viene descritto come interagire <xref:System.Windows.Controls.DataGrid> con il controllo utilizzando la tastiera e il mouse.|  
|[Procedura: Raggruppare, ordinare e filtrare dati nel controllo DataGrid](how-to-group-sort-and-filter-data-in-the-datagrid-control.md)|Viene descritto come visualizzare <xref:System.Windows.Controls.DataGrid> i dati in modi diversi raggruppando, ordinando e filtrando i dati.|  
|[Opzioni di ridimensionamento nel controllo DataGrid](sizing-options-in-the-datagrid-control.md)|Viene descritto come controllare il ridimensionamento <xref:System.Windows.Controls.DataGrid>assoluto e automatico nell'oggetto .|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataGrid>
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md)
- [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md)
- [Controlli](index.md)
- [Modello di contenuto WPF](wpf-content-model.md)
