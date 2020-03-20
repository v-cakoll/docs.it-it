---
title: Cenni preliminari sull'elemento Table
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
ms.openlocfilehash: 4bd747cea43755116c56b16f1de9a6ffb59935ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187264"
---
# <a name="table-overview"></a>Cenni preliminari sull'elemento Table
<xref:System.Windows.Documents.Table>è un elemento a livello di blocco che supporta la presentazione basata su griglia del contenuto del documento Flow. La flessibilità di questo elemento lo rende molto utile, ma al contempo ne complica la comprensione e l'uso corretto.  
  
 In questo argomento sono contenute le sezioni seguenti.  
  
- [Nozioni di base su Table](#table_basics)  
  
- [Differenze tra Table e Grid](#table_vs_Grid)  
  
- [Struttura di base di Table](#basic_table_structure)  
  
- [Contenimento di Table](#table_containment)  
  
- [Raggruppamenti di righe](#row_groupings)  
  
- [Precedenza del rendering dello sfondo](#rendering_precedence)  
  
- [Estensione su più righe o colonne](#spanning_rows_or_columns)  
  
- [Compilazione di un elemento Table con codice](#building_a_table_with_code)  
  
- [Argomenti correlati]
  
<a name="table_basics"></a>
## <a name="table-basics"></a>Nozioni di base su Table  
  
<a name="table_vs_Grid"></a>
### <a name="how-is-table-different-then-grid"></a>Differenze tra Table e Grid  
 <xref:System.Windows.Documents.Table>e <xref:System.Windows.Controls.Grid> condividere alcune funzionalità comuni, ma ognuna è più adatta per scenari diversi. A <xref:System.Windows.Documents.Table> è progettato per l'uso all'interno del contenuto del flusso (vedere [Panoramica del documento](flow-document-overview.md) di flusso per altre informazioni sul contenuto del flusso). Gli elementi Grid sono particolarmente adatti all'interno di moduli (in generale in un qualsiasi punto all'esterno del contenuto dinamico). All'interno di un <xref:System.Windows.Documents.FlowDocument>oggetto , <xref:System.Windows.Documents.Table> supporta i comportamenti del contenuto del <xref:System.Windows.Controls.Grid> flusso, ad esempio l'impaginazione, la ridisposizione delle colonne e la selezione del contenuto, mentre a non lo fa. Un <xref:System.Windows.Controls.Grid> altro d'altra parte è <xref:System.Windows.Documents.FlowDocument> meglio utilizzato <xref:System.Windows.Controls.Grid> al di fuori di un <xref:System.Windows.Documents.Table> per molti motivi, tra cui aggiunge elementi in base a un indice di riga e colonna, non. L'elemento <xref:System.Windows.Controls.Grid> consente la stratificazione del contenuto figlio, consentendo l'esistenza di più elementi all'interno di una singola "cella". <xref:System.Windows.Documents.Table>non supporta la stratificazione. Gli elementi <xref:System.Windows.Controls.Grid> figlio di un oggetto possono essere posizionati in modo assoluto rispetto all'area dei relativi limiti di "cella". <xref:System.Windows.Documents.Table>non supporta questa funzione. Infine, <xref:System.Windows.Controls.Grid> un richiede meno <xref:System.Windows.Documents.Table> risorse quindi <xref:System.Windows.Controls.Grid> è consigliabile utilizzare un per migliorare le prestazioni.  
  
<a name="basic_table_structure"></a>
### <a name="basic-table-structure"></a>Struttura di base di Table  
 <xref:System.Windows.Documents.Table>fornisce una presentazione basata su griglia <xref:System.Windows.Documents.TableColumn> costituita da colonne <xref:System.Windows.Documents.TableRow> (rappresentate da elementi) e righe (rappresentate da elementi). <xref:System.Windows.Documents.TableColumn>gli elementi non ospitano contenuto; definiscono semplicemente le colonne e le caratteristiche delle colonne. <xref:System.Windows.Documents.TableRow>gli elementi devono essere <xref:System.Windows.Documents.TableRowGroup> ospitati in un elemento, che definisce un raggruppamento di righe per la tabella. <xref:System.Windows.Documents.TableCell>gli elementi, che contengono il contenuto effettivo che deve <xref:System.Windows.Documents.TableRow> essere presentato dalla tabella, devono essere ospitati in un elemento. <xref:System.Windows.Documents.TableCell>può contenere solo <xref:System.Windows.Documents.Block>elementi che derivano da .  Elementi figlio validi <xref:System.Windows.Documents.TableCell> per un'inclusione.  
  
- <xref:System.Windows.Documents.BlockUIContainer>  
  
- <xref:System.Windows.Documents.List>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
> <xref:System.Windows.Documents.TableCell>elementi non possono ospitare direttamente il contenuto di testo. Per ulteriori informazioni sulle regole di contenimento per gli elementi di contenuto del flusso, ad esempio <xref:System.Windows.Documents.TableCell>, vedere [Cenni preliminari](flow-document-overview.md)sul documento dinamico .  
  
> [!NOTE]
> <xref:System.Windows.Documents.Table>è simile <xref:System.Windows.Controls.Grid> all'elemento, ma ha più funzionalità e, pertanto, richiede un maggiore sovraccarico delle risorse.  
  
 L'esempio seguente definisce una semplice tabella 2 x 3 con XAML.  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Screenshot che mostra la modalità di rendering di una tabella di base.](./media/table-overview/basic-table-render-example.png)  
  
<a name="table_containment"></a>
### <a name="table-containment"></a>Contenimento di Table  
 <xref:System.Windows.Documents.Table>deriva dall'elemento <xref:System.Windows.Documents.Block> e aderisce alle <xref:System.Windows.Documents.Block> regole comuni per gli elementi di livello.  Un <xref:System.Windows.Documents.Table> elemento può essere contenuto in uno dei seguenti elementi:  
  
- <xref:System.Windows.Documents.FlowDocument>  
  
- <xref:System.Windows.Documents.TableCell>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Documents.Section>  
  
- <xref:System.Windows.Documents.Floater>  
  
- <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>
### <a name="row-groupings"></a>Raggruppamenti di righe  
 L'elemento <xref:System.Windows.Documents.TableRowGroup> fornisce un modo per raggruppare arbitrariamente le righe all'interno di una tabella; ogni riga di una tabella deve appartenere a un raggruppamento di righe.  Spesso, le righe appartenenti allo stesso gruppo condividono un intento comune ed è possibile usare uno stile comune per il gruppo.  Un uso tipico dei raggruppamenti di righe consiste nel separare le righe con scopi specifici, ad esempio le righe di titolo, intestazione e piè di pagina, dal contenuto principale della tabella.  
  
 L'esempio seguente usa XAML per definire una tabella con righe di intestazione e piè di pagina con stili.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Schermata: gruppi di righe di tabella](./media/table-rowgroups.png "Table_RowGroups")  
  
<a name="rendering_precedence"></a>
### <a name="background-rendering-precedence"></a>Precedenza del rendering dello sfondo  
 Il rendering di elementi Table viene eseguito nell'ordine seguente (z order dal più basso al più alto). Quest'ordine non può essere modificato. Ad esempio, per questi elementi non esiste una proprietà "z order" che è possibile usare per l'override dell'ordine stabilito.  
  
1. <xref:System.Windows.Documents.Table>  
  
2. <xref:System.Windows.Documents.TableColumn>  
  
3. <xref:System.Windows.Documents.TableRowGroup>  
  
4. <xref:System.Windows.Documents.TableRow>  
  
5. <xref:System.Windows.Documents.TableCell>  
  
 L'esempio seguente definisce i colori di sfondo per ogni elemento all'interno di una tabella.  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 La figura seguente illustra il rendering di questo esempio (visualizzazione dei soli colori di sfondo).  
  
 ![Schermata: Tabella z&#45;ordine](./media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>
### <a name="spanning-rows-or-columns"></a>Estensione su più righe o colonne  
 Le celle di tabella possono essere configurate <xref:System.Windows.Documents.TableCell.RowSpan%2A> <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> per estendersi su più righe o colonne utilizzando rispettivamente gli attributi o .  
  
 L'esempio seguente definisce una cella che si estende su tre colonne.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 La figura seguente illustra il rendering di questo esempio.  
  
 ![Schermata: cella che si estende su tutte e tre colonne](./media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>
## <a name="building-a-table-with-code"></a>Compilazione di un elemento Table con codice  
 Negli esempi seguenti viene illustrato <xref:System.Windows.Documents.Table> come creare un oggetto a livello di codice e popolarlo con contenuto. Il contenuto della tabella è suddiviso in cinque <xref:System.Windows.Documents.TableRow> righe (rappresentate da oggetti contenuti in un <xref:System.Windows.Documents.Table.RowGroups%2A> oggetto) e sei colonne (rappresentate da <xref:System.Windows.Documents.TableColumn> oggetti). Le righe vengono usate per scopi di presentazione diversi, ad esempio una riga è destinata a contenere il titolo dell'intera tabella, una riga di intestazione a descrivere le colonne di dati nella tabella e una riga di piè di pagina a fornire informazioni di riepilogo.  Si noti che i concetti di righe di "titolo", "intestazione" e "piè di pagina" non sono inerenti alla tabella, ma fanno semplicemente riferimento a righe con caratteristiche diverse. Le celle di tabella contengono il contenuto effettivo, che può [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] essere costituito da testo, immagini o quasi qualsiasi altro elemento.  
  
 Innanzitutto, <xref:System.Windows.Documents.FlowDocument> viene creato <xref:System.Windows.Documents.Table>un oggetto <xref:System.Windows.Documents.Table> per ospitare l'oggetto , <xref:System.Windows.Documents.FlowDocument>e ne viene creato uno nuovo che viene aggiunto al contenuto dell'oggetto .  
  
 [!code-csharp[TableSnippets#_TableCreate](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 Successivamente, <xref:System.Windows.Documents.TableColumn> sei oggetti vengono creati e <xref:System.Windows.Documents.Table.Columns%2A> aggiunti alla raccolta della tabella, con una certa formattazione applicata.  
  
> [!NOTE]
> Si noti che <xref:System.Windows.Documents.Table.Columns%2A> la raccolta della tabella utilizza l'indicizzazione in base zero standard.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 Viene quindi creata una riga del titolo che viene aggiunta alla tabella con l'applicazione di alcuni elementi di formattazione.  La riga del titolo può contenere una sola cella che si estende su tutte e sei le colonne della tabella.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 Successivamente, viene creata e aggiunta alla tabella una riga di intestazione, per la quale vengono create celle in cui viene inserito contenuto.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 Successivamente, viene creata e aggiunta alla tabella una riga per i dati, per la quale vengono create celle in cui viene inserito contenuto.  La compilazione di questa riga è simile alla compilazione della riga di intestazione, con l'applicazione di una formattazione leggermente diversa.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 Infine, viene creata, aggiunta e formattata una riga di piè di pagina.  Analogamente alla riga del titolo, il piè di pagina contiene una sola cella che si estende su tutte e sei le colonne della tabella.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sui documenti dinamici](flow-document-overview.md)
- [Definire un oggetto Table tramite XAML](how-to-define-a-table-with-xaml.md)
- [Documenti in WPF](documents-in-wpf.md)
- [Usare elementi di contenuto di flusso](how-to-use-flow-content-elements.md)
