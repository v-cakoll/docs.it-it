---
title: Cenni preliminari sull'elemento Table
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb9edf0439c985af015d6badd11c026449a82f57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="table-overview"></a>Cenni preliminari sull'elemento Table
<xref:System.Windows.Documents.Table>è un elemento di livello di blocco che supporta la presentazione basata su griglia flusso del contenuto del documento. La flessibilità di questo elemento lo rende molto utile, ma al contempo ne complica la comprensione e l'uso corretto.  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
-   [Nozioni di base su Table](#table_basics)  
  
-   [Differenze tra Table e Grid](#table_vs_Grid)  
  
-   [Struttura di base di Table](#basic_table_structure)  
  
-   [Contenimento di Table](#table_containment)  
  
-   [Raggruppamenti di righe](#row_groupings)  
  
-   [Precedenza del rendering dello sfondo](#rendering_precedence)  
  
-   [Estensione su più righe o colonne](#spanning_rows_or_columns)  
  
-   [Compilazione di un elemento Table con codice](#building_a_table_with_code)  
  
-   [Argomenti correlati] 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a>Nozioni di base su Table  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a>Differenze tra Table e Grid  
 <xref:System.Windows.Documents.Table>e <xref:System.Windows.Controls.Grid> condividono alcune funzionalità comuni, ma ognuno è adatto per scenari diversi. Oggetto <xref:System.Windows.Documents.Table> è progettato per l'utilizzo all'interno del contenuto di flusso (vedere [Cenni preliminari sul documento flusso](../../../../docs/framework/wpf/advanced/flow-document-overview.md) per ulteriori informazioni sul contenuto di flusso). Gli elementi Grid sono particolarmente adatti all'interno di moduli (in generale in un qualsiasi punto all'esterno del contenuto dinamico). All'interno di un <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> supporta contenuti comportamenti flusso come impaginazione, riflusso di colonne e selezione del contenuto durante una <xref:System.Windows.Controls.Grid> non. A <xref:System.Windows.Controls.Grid> d'altra parte è più adatta all'esterno di un <xref:System.Windows.Documents.FlowDocument> per diversi motivi, tra cui <xref:System.Windows.Controls.Grid> aggiunge gli elementi basati su un indice di riga e colonna <xref:System.Windows.Documents.Table> non. Il <xref:System.Windows.Controls.Grid> elemento consente la sovrapposizione del contenuto figlio, che consente più di un elemento presente in un singolo "cella". <xref:System.Windows.Documents.Table>non supporta la sovrapposizione. Gli elementi figlio di un <xref:System.Windows.Controls.Grid> possono essere posizionati relative all'area della relativa "cella". <xref:System.Windows.Documents.Table>non supporta questa funzionalità. Infine, un <xref:System.Windows.Controls.Grid> richiede meno risorse di un <xref:System.Windows.Documents.Table> pertanto è consigliabile utilizzare un <xref:System.Windows.Controls.Grid> per migliorare le prestazioni.  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a>Struttura di base di Table  
 <xref:System.Windows.Documents.Table>fornisce una presentazione basata su griglia, costituito da colonne (rappresentato da <xref:System.Windows.Documents.TableColumn> elementi) e righe (rappresentati da <xref:System.Windows.Documents.TableRow> elementi). <xref:System.Windows.Documents.TableColumn>gli elementi non ospitano il contenuto. semplicemente definiscono le colonne e sulle caratteristiche di colonne. <xref:System.Windows.Documents.TableRow>gli elementi devono essere ospitati un <xref:System.Windows.Documents.TableRowGroup> elemento, che definisce un raggruppamento di righe per la tabella. <xref:System.Windows.Documents.TableCell>elementi che contengono il contenuto effettivo presentato dalla tabella, devono essere ospitati in un <xref:System.Windows.Documents.TableRow> elemento. <xref:System.Windows.Documents.TableCell>può contenere solo elementi che derivano da <xref:System.Windows.Documents.Block>.  Gli elementi figlio validi per un <xref:System.Windows.Documents.TableCell> includono.  
  
-   <xref:System.Windows.Documents.BlockUIContainer>  
  
-   <xref:System.Windows.Documents.List>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  <xref:System.Windows.Documents.TableCell>gli elementi non possono ospitare direttamente contenuto di testo. Per ulteriori informazioni sulle regole di contenimento per il flusso di elementi di contenuto quali <xref:System.Windows.Documents.TableCell>, vedere [Cenni preliminari sul documento flusso](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Table>è simile al <xref:System.Windows.Controls.Grid> elemento ma ha altre funzionalità e, pertanto, richiede un sovraccarico maggiore di risorse.  
  
 L'esempio seguente definisce una semplice tabella 2 x 3 con [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Screenshot: rendering di una tabella semplice](../../../../docs/framework/wpf/advanced/media/basictablerrender.png "BasicTablerRender")  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a>Contenimento di Table  
 <xref:System.Windows.Documents.Table>deriva la <xref:System.Windows.Documents.Block> elemento ed è conforme alle regole comuni per <xref:System.Windows.Documents.Block> gli elementi a livello.  Oggetto <xref:System.Windows.Documents.Table> elemento può essere contenuto da uno qualsiasi dei seguenti elementi:  
  
-   <xref:System.Windows.Documents.FlowDocument>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a>Raggruppamenti di righe  
 Il <xref:System.Windows.Documents.TableRowGroup> elemento fornisce un modo per raggruppare arbitrariamente le righe all'interno di una tabella, ogni riga in una tabella debba appartenere a un raggruppamento di righe.  Spesso, le righe appartenenti allo stesso gruppo condividono un intento comune ed è possibile usare uno stile comune per il gruppo.  Un uso tipico dei raggruppamenti di righe consiste nel separare le righe con scopi specifici, ad esempio le righe di titolo, intestazione e piè di pagina, dal contenuto principale della tabella.  
  
 L'esempio seguente usa [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] per definire una tabella con righe di intestazione e piè di pagina con stile.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Screenshot: gruppi di righe di tabella](../../../../docs/framework/wpf/advanced/media/table-rowgroups.png "Table_RowGroups")  
  
<a name="rendering_precedence"></a>   
### <a name="background-rendering-precedence"></a>Precedenza del rendering dello sfondo  
 Il rendering di elementi Table viene eseguito nell'ordine seguente (z order dal più basso al più alto). Quest'ordine non può essere modificato. Ad esempio, per questi elementi non esiste una proprietà "z order" che è possibile usare per l'override dell'ordine stabilito.  
  
1.  <xref:System.Windows.Documents.Table>  
  
2.  <xref:System.Windows.Documents.TableColumn>  
  
3.  <xref:System.Windows.Documents.TableRowGroup>  
  
4.  <xref:System.Windows.Documents.TableRow>  
  
5.  <xref:System.Windows.Documents.TableCell>  
  
 L'esempio seguente definisce i colori di sfondo per ogni elemento all'interno di una tabella.  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 La figura seguente illustra il rendering di questo esempio (visualizzazione dei soli colori di sfondo).  
  
 ![Screenshot: z order della tabella](../../../../docs/framework/wpf/advanced/media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a>Estensione su più righe o colonne  
 Le celle di tabella possono essere configurate per estendersi su più righe o colonne utilizzando la <xref:System.Windows.Documents.TableCell.RowSpan%2A> o <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> rispettivamente gli attributi.  
  
 L'esempio seguente definisce una cella che si estende su tre colonne.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Screenshot: cella che si estende su tutte e tre le colonne](../../../../docs/framework/wpf/advanced/media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a>Compilazione di un elemento Table con codice  
 Gli esempi seguenti mostrano come creare a livello di codice un <xref:System.Windows.Documents.Table> e popolarlo con contenuto. Il contenuto della tabella viene ripartito cinque righe (rappresentati da <xref:System.Windows.Documents.TableRow> gli oggetti contenuti un <xref:System.Windows.Documents.Table.RowGroups%2A> oggetto) e sei colonne (rappresentato da <xref:System.Windows.Documents.TableColumn> oggetti). Le righe vengono usate per scopi di presentazione diversi, ad esempio una riga è destinata a contenere il titolo dell'intera tabella, una riga di intestazione a descrivere le colonne di dati nella tabella e una riga di piè di pagina a fornire informazioni di riepilogo.  Si noti che i concetti di righe di "titolo", "intestazione" e "piè di pagina" non sono inerenti alla tabella, ma fanno semplicemente riferimento a righe con caratteristiche diverse. Le celle di tabella contengono il contenuto effettivo, che può essere costituito da testo, immagini o qualsiasi altro [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] elemento.  
  
 Prima di tutto, un <xref:System.Windows.Documents.FlowDocument> viene creato all'host di <xref:System.Windows.Documents.Table>e un nuovo <xref:System.Windows.Documents.Table> viene creato e aggiunto al contenuto del <xref:System.Windows.Documents.FlowDocument>.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 Successivamente, sei <xref:System.Windows.Documents.TableColumn> gli oggetti vengono creati e aggiunti alla tabella <xref:System.Windows.Documents.Table.Columns%2A> raccolta, con alcune formattazione applicata.  
  
> [!NOTE]
>  Si noti che la tabella <xref:System.Windows.Documents.Table.Columns%2A> insieme utilizza l'indicizzazione in base zero standard.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Viene quindi creata una riga del titolo che viene aggiunta alla tabella con l'applicazione di alcuni elementi di formattazione.  La riga del titolo può contenere una sola cella che si estende su tutte e sei le colonne della tabella.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Successivamente, viene creata e aggiunta alla tabella una riga di intestazione, per la quale vengono create celle in cui viene inserito contenuto.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 Successivamente, viene creata e aggiunta alla tabella una riga per i dati, per la quale vengono create celle in cui viene inserito contenuto.  La compilazione di questa riga è simile alla compilazione della riga di intestazione, con l'applicazione di una formattazione leggermente diversa.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 Infine, viene creata, aggiunta e formattata una riga di piè di pagina.  Analogamente alla riga del titolo, il piè di pagina contiene una sola cella che si estende su tutte e sei le colonne della tabella.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sui documenti dinamici](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [Definire un oggetto Table con XAML](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)  
 [Documenti in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Usare elementi di contenuto dinamico](../../../../docs/framework/wpf/advanced/how-to-use-flow-content-elements.md)
