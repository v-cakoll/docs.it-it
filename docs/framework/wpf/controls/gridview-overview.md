---
title: Cenni preliminari su GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: d2f55db90fb130416ee4dcb15d440b6d367c0b06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008761"
---
# <a name="gridview-overview"></a>Cenni preliminari su GridView
<xref:System.Windows.Controls.GridView> modalità di visualizzazione è una delle modalità di visualizzazione di un <xref:System.Windows.Controls.ListView> controllo. Il <xref:System.Windows.Controls.GridView> classe e delle relative classi di supporto consentono agli utenti di visualizzare raccolte di elementi in una tabella che utilizza in genere i pulsanti come intestazioni di colonna interattive. Questo argomento vengono presentate le <xref:System.Windows.Controls.GridView> classe e relativo uso.  

<a name="DefiningaListViewthatusesGridViewView"></a>   
## <a name="what-is-a-gridview-view"></a>Definizione della visualizzazione GridView  
 Il <xref:System.Windows.Controls.GridView> visualizzazione modalità consente di visualizzare un elenco di elementi di dati da associando i campi dati a colonne e visualizzando un'intestazione di colonna che identifica il campo. Il valore predefinito <xref:System.Windows.Controls.GridView> stile implementa i pulsanti come intestazioni di colonna. Usando i pulsanti per le intestazioni di colonna, è possibile implementare funzionalità di interazione dell'utente che è importante; ad esempio, gli utenti possono selezionare l'intestazione di colonna per ordinare <xref:System.Windows.Controls.GridView> dati in base al contenuto di una colonna specifica.  
  
> [!NOTE]
>  Il pulsante Controlla che <xref:System.Windows.Controls.GridView> viene utilizzata per le intestazioni di colonna derivano da <xref:System.Windows.Controls.Primitives.ButtonBase>.  
  
 La figura seguente mostra una <xref:System.Windows.Controls.GridView> visualizzazione di <xref:System.Windows.Controls.ListView> contenuto.  
    
 ![Screenshot che mostra la visualizzazione GridView del contenuto di ListView.](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView> le colonne sono rappresentate da <xref:System.Windows.Controls.GridViewColumn> gli oggetti che possono essere ridimensionati automaticamente in base al contenuto. Facoltativamente, è possibile impostare in modo esplicito un <xref:System.Windows.Controls.GridViewColumn> a una larghezza specifica. È possibile ridimensionare le colonne trascinando la barra gripper tra le intestazioni di colonna. È possibile anche in modo dinamico aggiungere, rimuovere, sostituire e riordinare le colonne, poiché questa funzionalità è incorporata in <xref:System.Windows.Controls.GridView>. Tuttavia, <xref:System.Windows.Controls.GridView> non è possibile aggiornare direttamente i dati che vengono visualizzati.  
  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.GridView> che consente di visualizzare i dati dei dipendenti. In questo esempio <xref:System.Windows.Controls.ListView> definisce i `EmployeeInfoDataSource` come la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Le definizioni delle proprietà <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> associare <xref:System.Windows.Controls.GridViewColumn> contenuto `EmployeeInfoDataSource` categorie di dati.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 La figura seguente illustra la tabella creata nell'esempio precedente. Il controllo GridView Visualizza i dati da un oggetto ItemsSource:
    
 ![Screenshot che mostra un ListView con output GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>   
## <a name="gridview-layout-and-style"></a>Layout e stile di GridView  
 Le celle e l'intestazione di colonna di una <xref:System.Windows.Controls.GridViewColumn> hanno la stessa larghezza. Per impostazione predefinita, la larghezza di ogni colonna viene ridimensionata in base al contenuto. Facoltativamente, è possibile impostare una colonna a larghezza fissa.  
  
 Il contenuto dei dati correlati viene visualizzato in righe orizzontali. Ad esempio, nell'illustrazione precedente il cognome, il nome e l'ID di ogni dipendente vengono visualizzati come un insieme perché appaiono in una riga orizzontale.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### <a name="defining-and-styling-columns-in-a-gridview"></a>Definizione e applicazione di stili alle colonne in GridView  
 Quando si definisce il campo dati da visualizzare in una <xref:System.Windows.Controls.GridViewColumn>, usare il <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>, o <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> proprietà. Il <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> proprietà ha la precedenza su una delle proprietà del modello.  
  
 Per specificare l'allineamento del contenuto in una colonna di una <xref:System.Windows.Controls.GridView>, definire un <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>. Non usare la <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> e <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> delle proprietà per <xref:System.Windows.Controls.ListView> contenuto visualizzato tramite un <xref:System.Windows.Controls.GridView>.  
  
 Per specificare le proprietà di modello e di stile per intestazioni di colonna, usare il <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn>, e <xref:System.Windows.Controls.GridViewColumnHeader> classi. Per altre informazioni, vedere [Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView](gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### <a name="adding-visual-elements-to-a-gridview"></a>Aggiunta di elementi visivi a GridView  
 Per aggiungere elementi visivi, ad esempio <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.Button> controlli, a un <xref:System.Windows.Controls.GridView> modalità di visualizzazione, usare i modelli o stili.  
  
 Se si definisce in modo esplicito un elemento visivo come elemento di dati, può essere visualizzato solo una volta in un <xref:System.Windows.Controls.GridView>. Questa limitazione esiste perché un elemento può avere un solo padre e, di conseguenza, può essere visualizzato solo una volta nella struttura ad albero visuale.  
  
<a name="StylingRowsinaGridViewView"></a>   
### <a name="styling-rows-in-a-gridview"></a>Applicazione di stili alle righe in GridView  
 Usare la <xref:System.Windows.Controls.GridViewRowPresenter> e <xref:System.Windows.Controls.GridViewHeaderRowPresenter> classi per formattare e visualizzare le righe di una <xref:System.Windows.Controls.GridView>. Per un esempio di come stili alle righe in una <xref:System.Windows.Controls.GridView> modalità di visualizzazione, vedere [disegnare una riga in un ListView che implementa una GridView](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Problemi di allineamento durante l'uso di ItemContainerStyle  
 Per evitare problemi di allineamento tra le intestazioni di colonna e le celle, non impostare una proprietà o specificare un modello che influisca sulla larghezza di un elemento in un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>. Ad esempio, non impostare il <xref:System.Windows.FrameworkElement.Margin%2A> proprietà oppure specificare un <xref:System.Windows.Controls.ControlTemplate> che aggiunge un <xref:System.Windows.Controls.CheckBox> a un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> definito in un <xref:System.Windows.Controls.ListView> controllo. In alternativa, specificare le proprietà e i modelli che influenzano la larghezza di colonna direttamente nelle classi che definiscono un <xref:System.Windows.Controls.GridView> modalità di visualizzazione.  
  
 Ad esempio, per aggiungere un <xref:System.Windows.Controls.CheckBox> alle righe in <xref:System.Windows.Controls.GridView> modalità di visualizzazione, aggiungere il <xref:System.Windows.Controls.CheckBox> a un <xref:System.Windows.DataTemplate>e quindi impostare il <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> proprietà a cui <xref:System.Windows.DataTemplate>.  
  
<a name="InteractingwithaGridViewControl"></a>   
## <a name="user-interactions-with-a-gridview"></a>Interazioni dell'utente con GridView  
 Quando si usa un' <xref:System.Windows.Controls.GridView> nell'applicazione, gli utenti possono interagire con e modificarne la formattazione di <xref:System.Windows.Controls.GridView>. Ad esempio, gli utenti possono riordinare le colonne, ridimensionare una colonna, selezionare gli elementi in una tabella e scorrere il contenuto. È inoltre possibile definire un gestore eventi che risponda quando un utente fa clic sul pulsante di intestazione di colonna. Il gestore eventi può eseguire operazioni quali l'ordinamento dei dati che viene visualizzati nei <xref:System.Windows.Controls.GridView> in base al contenuto di una colonna.  
  
 Nell'elenco seguente vengono illustrati in dettaglio le funzionalità dell'uso <xref:System.Windows.Controls.GridView> per l'interazione dell'utente:  
  
- **Riordinare le colonne con il metodo di trascinamento della selezione.**  
  
     Gli utenti possono riordinare le colonne in un <xref:System.Windows.Controls.GridView> premendo il pulsante sinistro del mouse mentre si trova su un'intestazione di colonna e quindi trascinando la colonna in una nuova posizione. Mentre l'utente trascina l'intestazione di colonna, viene visualizzata una versione a virgola mobile dell'intestazione e una linea nera continua che indica dove inserire la colonna.  
  
     Se si desidera modificare lo stile predefinito per la versione mobile di un'intestazione, specificare una <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.GridViewColumnHeader> tipo che è attivata quando il <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> è impostata su <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>. Per altre informazioni vedere [Creare uno stile per un'intestazione di colonna GridView trascinata](how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
- **Ridimensionare una colonna in base al contenuto.**  
  
     Gli utenti possono fare doppio clic sulla barra gripper a destra di un'intestazione di colonna per adattare le dimensioni di una colonna al contenuto.  
  
    > [!NOTE]
    >  È possibile impostare il <xref:System.Windows.Controls.GridViewColumn.Width%2A> proprietà `Double.NaN` per produrre lo stesso effetto.  
  
- **Selezionare gli elementi di una riga.**  
  
     Gli utenti possono selezionare uno o più elementi in un <xref:System.Windows.Controls.GridView>.  
  
     Se si desidera modificare il <xref:System.Windows.Style> di un elemento selezionato, vedere [usare i trigger per gli elementi selezionati in un ListView](how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
- **Scorrere per visualizzare il contenuto che non è inizialmente visibile sullo schermo.**  
  
     Se le dimensioni dei <xref:System.Windows.Controls.GridView> è non sufficientemente grande per visualizzare tutti gli elementi, gli utenti possono scorrere orizzontalmente o verticalmente usando le barre di scorrimento, che sono fornite da un <xref:System.Windows.Controls.ScrollViewer> controllo. Oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> viene nascosto se tutto il contenuto è visibile in una direzione specifica. Le intestazioni di colonna non scorrono mediante una barra di scorrimento verticale, ma scorrono in senso orizzontale.  
  
- **Interagire con le colonne facendo clic sui pulsanti di intestazione di colonna.**  
  
     Quando si fa clic su un pulsante di intestazione di colonna, è possibile ordinare i dati visualizzati nella colonna se è stato specificato un algoritmo di ordinamento.  
  
     È possibile gestire il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventi per i pulsanti di intestazione di colonna per fornire funzionalità quali un algoritmo di ordinamento. Per gestire il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento per una singola intestazione di colonna, impostare un gestore eventi sul <xref:System.Windows.Controls.GridViewColumnHeader>. Per impostare un gestore eventi che gestisce il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventi per tutte le intestazioni di colonna, impostare il gestore nel <xref:System.Windows.Controls.ListView> controllo.  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## <a name="obtaining-other-custom-views"></a>Ottenere altre visualizzazioni personalizzate  
 Il <xref:System.Windows.Controls.GridView> classe che deriva dal <xref:System.Windows.Controls.ViewBase> classe astratta, è solo una delle possibili modalità di visualizzazione per il <xref:System.Windows.Controls.ListView> classe. È possibile creare altre visualizzazioni personalizzate per <xref:System.Windows.Controls.ListView> mediante la derivazione da di <xref:System.Windows.Controls.ViewBase> classe. Per un esempio di una modalità di visualizzazione personalizzata, vedere [Creare una modalità di visualizzazione personalizzata per un oggetto ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>   
## <a name="gridview-supporting-classes"></a>Classi che supportano GridView  
 Le classi seguenti supportano il <xref:System.Windows.Controls.GridView> modalità di visualizzazione.  
  
- <xref:System.Windows.Controls.GridViewColumn>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GridViewRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewColumnCollection>  
  
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Controls.GridViewColumn>
- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.ViewBase>
- [Panoramica sul controllo ListView](listview-overview.md)
- [Ordinare una colonna GridView quando si fa clic su un'intestazione](how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Procedure relative alle proprietà](listview-how-to-topics.md)
