---
title: Cenni preliminari su GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 776897d490b2748e240cf7b9a4ea21364284c4c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557681"
---
# <a name="gridview-overview"></a>Cenni preliminari su GridView
<xref:System.Windows.Controls.GridView> modalità di visualizzazione è una delle modalità di visualizzazione per un <xref:System.Windows.Controls.ListView> controllo. La <xref:System.Windows.Controls.GridView> classe e le relative classi di supporto consentono agli utenti di visualizzare raccolte di elementi in una tabella che utilizza in genere i pulsanti come intestazioni di colonna interattive. Questo argomento vengono presentate le <xref:System.Windows.Controls.GridView> classe e viene illustrato l'utilizzo.  
  
  
  
<a name="DefiningaListViewthatusesGridViewView"></a>   
## <a name="what-is-a-gridview-view"></a>Definizione della visualizzazione GridView  
 Il <xref:System.Windows.Controls.GridView> modalità Visualizza un elenco di elementi di dati per l'associazione di campi di dati alle colonne e visualizzando un'intestazione di colonna per identificare il campo di visualizzazione. Il valore predefinito <xref:System.Windows.Controls.GridView> stile implementa i pulsanti come intestazioni di colonna. Utilizzando i pulsanti per le intestazioni di colonna, è possibile implementare funzionalità di interazione dell'utente che è importante; ad esempio, gli utenti possono selezionare l'intestazione di colonna per ordinare <xref:System.Windows.Controls.GridView> dati in base al contenuto di una colonna specifica.  
  
> [!NOTE]
>  I controlli pulsante che <xref:System.Windows.Controls.GridView> viene utilizzato per le intestazioni di colonna derivati da <xref:System.Windows.Controls.Primitives.ButtonBase>.  
  
 La figura seguente mostra un <xref:System.Windows.Controls.GridView> visualizzare <xref:System.Windows.Controls.ListView> contenuto.  
  
 **Visualizzazione GridView del contenuto di ListView**  
  
 ![ListView con stile](../../../../docs/framework/wpf/controls/media/styledlistview.PNG "StyledListView")  
  
 <xref:System.Windows.Controls.GridView> le colonne sono rappresentate da <xref:System.Windows.Controls.GridViewColumn> oggetti, che possono ridimensionare automaticamente in base al contenuto. Facoltativamente, è possibile impostare in modo esplicito un <xref:System.Windows.Controls.GridViewColumn> alla larghezza. È possibile ridimensionare le colonne trascinando la barra gripper tra le intestazioni di colonna. È inoltre in modo dinamico aggiungere, rimuovere, sostituire e riordinare le colonne, poiché questa funzionalità è incorporata in <xref:System.Windows.Controls.GridView>. Tuttavia, <xref:System.Windows.Controls.GridView> non è possibile aggiornare direttamente i dati che vengono visualizzati.  
  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Controls.GridView> che consente di visualizzare i dati dei dipendenti. In questo esempio, <xref:System.Windows.Controls.ListView> definisce il `EmployeeInfoDataSource` come il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Le definizioni delle proprietà <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> associare <xref:System.Windows.Controls.GridViewColumn> contenuto `EmployeeInfoDataSource` categorie di dati.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 La figura seguente illustra la tabella creata nell'esempio precedente.  
  
 **GridView visualizza i dati da ItemsSource**  
  
 ![ListView con output GridView ](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
<a name="GridViewLayoutandStyle"></a>   
## <a name="gridview-layout-and-style"></a>Layout e stile di GridView  
 Le celle della colonna e l'intestazione di colonna di un <xref:System.Windows.Controls.GridViewColumn> hanno la stessa larghezza. Per impostazione predefinita, la larghezza di ogni colonna viene ridimensionata in base al contenuto. Facoltativamente, è possibile impostare una colonna a larghezza fissa.  
  
 Il contenuto dei dati correlati viene visualizzato in righe orizzontali. Ad esempio, nell'illustrazione precedente il cognome, il nome e l'ID di ogni dipendente vengono visualizzati come un insieme perché appaiono in una riga orizzontale.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### <a name="defining-and-styling-columns-in-a-gridview"></a>Definizione e applicazione di stili alle colonne in GridView  
 Quando si definisce il campo dei dati da visualizzare un <xref:System.Windows.Controls.GridViewColumn>, utilizzare il <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>, o <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> proprietà. Il <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> avrà la precedenza su una delle proprietà del modello.  
  
 Per specificare l'allineamento del contenuto in una colonna di un <xref:System.Windows.Controls.GridView>, definire un <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>. Non utilizzare il <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> e <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> le proprietà per <xref:System.Windows.Controls.ListView> contenuto che viene visualizzato utilizzando un <xref:System.Windows.Controls.GridView>.  
  
 Per specificare le proprietà di modello e lo stile per le intestazioni di colonna, utilizzare il <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn>, e <xref:System.Windows.Controls.GridViewColumnHeader> classi. Per altre informazioni, vedere [Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### <a name="adding-visual-elements-to-a-gridview"></a>Aggiunta di elementi visivi a GridView  
 Per aggiungere elementi visivi, ad esempio <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.Button> controlli, a un <xref:System.Windows.Controls.GridView> modalità di visualizzazione, utilizzare i modelli o gli stili.  
  
 Se si definisce in modo esplicito un elemento visivo come un elemento di dati, può essere visualizzato solo una volta in un <xref:System.Windows.Controls.GridView>. Questa limitazione esiste perché un elemento può avere un solo padre e, di conseguenza, può essere visualizzato solo una volta nella struttura ad albero visuale.  
  
<a name="StylingRowsinaGridViewView"></a>   
### <a name="styling-rows-in-a-gridview"></a>Applicazione di stili alle righe in GridView  
 Utilizzare il <xref:System.Windows.Controls.GridViewRowPresenter> e <xref:System.Windows.Controls.GridViewHeaderRowPresenter> classi per formattare e visualizzare le righe di un <xref:System.Windows.Controls.GridView>. Per un esempio di come stili alle righe in un <xref:System.Windows.Controls.GridView> modalità di visualizzazione, vedere [disegnare una riga in un ListView That Implements GridView](../../../../docs/framework/wpf/controls/how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Problemi di allineamento durante l'uso di ItemContainerStyle  
 Per evitare problemi di allineamento tra le intestazioni di colonna e le celle, non impostare una proprietà o specificare un modello che influisce sulla larghezza di un elemento in un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>. Ad esempio, non impostare il <xref:System.Windows.FrameworkElement.Margin%2A> proprietà oppure specificare un <xref:System.Windows.Controls.ControlTemplate> che aggiunge un <xref:System.Windows.Controls.CheckBox> per un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> definito in un <xref:System.Windows.Controls.ListView> controllo. In alternativa, specificare le proprietà e i modelli che influiscono sulla larghezza della colonna direttamente per le classi che definiscono un <xref:System.Windows.Controls.GridView> modalità di visualizzazione.  
  
 Ad esempio, per aggiungere un <xref:System.Windows.Controls.CheckBox> alle righe in <xref:System.Windows.Controls.GridView> modalità di visualizzazione, aggiungere il <xref:System.Windows.Controls.CheckBox> per un <xref:System.Windows.DataTemplate>e quindi impostare il <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> che proprietà <xref:System.Windows.DataTemplate>.  
  
<a name="InteractingwithaGridViewControl"></a>   
## <a name="user-interactions-with-a-gridview"></a>Interazioni dell'utente con GridView  
 Quando si utilizza un <xref:System.Windows.Controls.GridView> nell'applicazione, gli utenti possono interagire con e modificarne la formattazione di <xref:System.Windows.Controls.GridView>. Ad esempio, gli utenti possono riordinare le colonne, ridimensionare una colonna, selezionare gli elementi in una tabella e scorrere il contenuto. È inoltre possibile definire un gestore eventi che risponda quando un utente fa clic sul pulsante di intestazione di colonna. Il gestore dell'evento può eseguire operazioni quali ordinamento dei dati che viene visualizzati nel <xref:System.Windows.Controls.GridView> in base al contenuto di una colonna.  
  
 Nell'elenco seguente vengono illustrati in dettaglio le funzionalità di utilizzo <xref:System.Windows.Controls.GridView> per l'interazione dell'utente:  
  
-   **Riordinare le colonne con il metodo di trascinamento della selezione.**  
  
     Gli utenti possono riordinare le colonne in un <xref:System.Windows.Controls.GridView> premendo il pulsante sinistro del mouse mentre si trova su un'intestazione di colonna e quindi trascinare la colonna in una nuova posizione. Mentre l'utente trascina l'intestazione di colonna, viene visualizzata una versione a virgola mobile dell'intestazione e una linea nera continua che indica dove inserire la colonna.  
  
     Se si desidera modificare lo stile predefinito per la versione mobile di un'intestazione, specificare un <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.GridViewColumnHeader> tipo che è attivata quando il <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> è impostata su <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>. Per altre informazioni vedere [Creare uno stile per un'intestazione di colonna GridView trascinata](../../../../docs/framework/wpf/controls/how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
-   **Ridimensionare una colonna in base al contenuto.**  
  
     Gli utenti possono fare doppio clic sulla barra gripper a destra di un'intestazione di colonna per adattare le dimensioni di una colonna al contenuto.  
  
    > [!NOTE]
    >  È possibile impostare il <xref:System.Windows.Controls.GridViewColumn.Width%2A> proprietà `Double.NaN` per produrre lo stesso effetto.  
  
-   **Selezionare gli elementi di una riga.**  
  
     Gli utenti possono selezionare uno o più elementi in un <xref:System.Windows.Controls.GridView>.  
  
     Se si desidera modificare il <xref:System.Windows.Style> di un elemento selezionato, vedere [utilizzare i trigger di creare gli elementi selezionati in un controllo ListView](../../../../docs/framework/wpf/controls/how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
-   **Scorrere per visualizzare il contenuto che non è inizialmente visibile sullo schermo.**  
  
     Se le dimensioni del <xref:System.Windows.Controls.GridView> è non sufficiente per visualizzare tutti gli elementi, gli utenti possono scorrere orizzontalmente o verticalmente usando le barre di scorrimento, che sono fornite da un <xref:System.Windows.Controls.ScrollViewer> controllo. Oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> viene nascosto se tutto il contenuto è visibile in una direzione specifica. Le intestazioni di colonna non scorrono mediante una barra di scorrimento verticale, ma scorrono in senso orizzontale.  
  
-   **Interagire con le colonne facendo clic sui pulsanti di intestazione di colonna.**  
  
     Quando si fa clic su un pulsante di intestazione di colonna, è possibile ordinare i dati visualizzati nella colonna se è stato specificato un algoritmo di ordinamento.  
  
     È possibile gestire il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventi per i pulsanti di intestazione di colonna per fornire funzionalità quali un algoritmo di ordinamento. Per gestire il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento per una singola intestazione di colonna, impostare un gestore eventi nel <xref:System.Windows.Controls.GridViewColumnHeader>. Per impostare un gestore eventi che gestisce il <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventi per tutte le intestazioni di colonna, impostare il gestore nel <xref:System.Windows.Controls.ListView> controllo.  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## <a name="obtaining-other-custom-views"></a>Ottenere altre visualizzazioni personalizzate  
 Il <xref:System.Windows.Controls.GridView> derivata dalla classe di <xref:System.Windows.Controls.ViewBase> classe astratta, è solo una delle possibili modalità di visualizzazione per il <xref:System.Windows.Controls.ListView> classe. È possibile creare altre visualizzazioni personalizzate per <xref:System.Windows.Controls.ListView> mediante derivazione da di <xref:System.Windows.Controls.ViewBase> classe. Per un esempio di una modalità di visualizzazione personalizzata, vedere [Creare una modalità di visualizzazione personalizzata per un oggetto ListView](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>   
## <a name="gridview-supporting-classes"></a>Classi che supportano GridView  
 Le classi seguenti supportano il <xref:System.Windows.Controls.GridView> modalità di visualizzazione.  
  
-   <xref:System.Windows.Controls.GridViewColumn>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GridViewRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewColumnCollection>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.ListViewItem>  
 <xref:System.Windows.Controls.GridViewColumn>  
 <xref:System.Windows.Controls.GridViewColumnHeader>  
 <xref:System.Windows.Controls.GridViewRowPresenter>  
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
 <xref:System.Windows.Controls.ViewBase>  
 [Panoramica sul controllo ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Ordinare una colonna GridView quando si fa clic su un'intestazione](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
