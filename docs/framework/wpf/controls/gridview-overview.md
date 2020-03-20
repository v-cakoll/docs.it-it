---
title: Cenni preliminari su GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 98bc7985172cabeab19469af4b4c21e13a6bce73
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181895"
---
# <a name="gridview-overview"></a>Cenni preliminari su GridView
<xref:System.Windows.Controls.GridView>modalità di visualizzazione è una <xref:System.Windows.Controls.ListView> delle modalità di visualizzazione per un controllo. La <xref:System.Windows.Controls.GridView> classe e le relative classi di supporto consentono all'utente di visualizzare le raccolte di elementi in una tabella che in genere utilizza pulsanti come intestazioni di colonna interattive. In questo argomento <xref:System.Windows.Controls.GridView> viene illustrata la classe e ne viene delineato l'utilizzo.  

<a name="DefiningaListViewthatusesGridViewView"></a>
## <a name="what-is-a-gridview-view"></a>Definizione della visualizzazione GridView  
 La <xref:System.Windows.Controls.GridView> modalità di visualizzazione visualizza un elenco di elementi di dati associando i campi dati alle colonne e visualizzando un'intestazione di colonna per identificare il campo. Lo <xref:System.Windows.Controls.GridView> stile predefinito implementa i pulsanti come intestazioni di colonna. Utilizzando i pulsanti per le intestazioni di colonna, è possibile implementare importanti funzionalità di interazione dell'utente; ad esempio, gli utenti possono <xref:System.Windows.Controls.GridView> fare clic sull'intestazione di colonna per ordinare i dati in base al contenuto di una colonna specifica.  
  
> [!NOTE]
> I controlli <xref:System.Windows.Controls.GridView> pulsante che utilizzano <xref:System.Windows.Controls.Primitives.ButtonBase>per le intestazioni di colonna derivano da .  
  
 Nella figura seguente <xref:System.Windows.Controls.GridView> viene <xref:System.Windows.Controls.ListView> illustrata una visualizzazione del contenuto.  

 ![Screenshot che mostra la visualizzazione GridView del contenuto di ListView.](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView>le colonne <xref:System.Windows.Controls.GridViewColumn> sono rappresentate da oggetti, che possono essere ridimensionati automaticamente in base al loro contenuto. Facoltativamente, è possibile <xref:System.Windows.Controls.GridViewColumn> impostare in modo esplicito a su una larghezza specifica. È possibile ridimensionare le colonne trascinando la barra gripper tra le intestazioni di colonna. È inoltre possibile aggiungere, rimuovere, sostituire e riordinare dinamicamente le colonne perché questa funzionalità è incorporata in <xref:System.Windows.Controls.GridView>. Tuttavia, <xref:System.Windows.Controls.GridView> non è possibile aggiornare direttamente i dati visualizzati.  
  
 Nell'esempio seguente viene <xref:System.Windows.Controls.GridView> illustrato come definire un che visualizza i dati dei dipendenti. In questo <xref:System.Windows.Controls.ListView> esempio, `EmployeeInfoDataSource` definisce <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>l'oggetto come . Definizioni di <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> <xref:System.Windows.Controls.GridViewColumn> proprietà `EmployeeInfoDataSource` di associare il contenuto alle categorie di dati.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 La figura seguente illustra la tabella creata nell'esempio precedente. Il controllo GridView visualizza i dati da un oggetto ItemsSource:The GridView control displays data from an ItemsSource object:

 ![Screenshot che mostra un controllo ListView con output di GridView.Screenshot that shows a ListView with GridView output.](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>
## <a name="gridview-layout-and-style"></a>Layout e stile di GridView  
 Le celle di colonna e <xref:System.Windows.Controls.GridViewColumn> l'intestazione di colonna di un hanno la stessa larghezza. Per impostazione predefinita, la larghezza di ogni colonna viene ridimensionata in base al contenuto. Facoltativamente, è possibile impostare una colonna a larghezza fissa.  
  
 Il contenuto dei dati correlati viene visualizzato in righe orizzontali. Ad esempio, nell'illustrazione precedente il cognome, il nome e l'ID di ogni dipendente vengono visualizzati come un insieme perché appaiono in una riga orizzontale.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>
### <a name="defining-and-styling-columns-in-a-gridview"></a>Definizione e applicazione di stili alle colonne in GridView  
 Quando si definisce il <xref:System.Windows.Controls.GridViewColumn>campo dati <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>da <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> visualizzare in un oggetto , utilizzare le proprietà , o . La <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> proprietà ha la precedenza su una delle proprietà del modello.  
  
 Per specificare l'allineamento del <xref:System.Windows.Controls.GridView>contenuto <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>in una colonna di un oggetto , definire un oggetto . Non utilizzare <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> le <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> proprietà <xref:System.Windows.Controls.ListView> e per il contenuto <xref:System.Windows.Controls.GridView>visualizzato utilizzando un oggetto .  
  
 Per specificare le proprietà del modello <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.GridViewColumn>e <xref:System.Windows.Controls.GridViewColumnHeader> dello stile per le intestazioni di colonna, utilizzare le classi , e . Per altre informazioni, vedere [Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView](gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>
### <a name="adding-visual-elements-to-a-gridview"></a>Aggiunta di elementi visivi a GridView  
 Per aggiungere elementi visivi, ad <xref:System.Windows.Controls.CheckBox> esempio e <xref:System.Windows.Controls.Button> controlli, a una <xref:System.Windows.Controls.GridView> modalità di visualizzazione, utilizzare modelli o stili.  
  
 Se si definisce in modo esplicito un elemento visivo <xref:System.Windows.Controls.GridView>come elemento di dati, può essere visualizzato una sola volta in un oggetto . Questa limitazione esiste perché un elemento può avere un solo padre e, di conseguenza, può essere visualizzato solo una volta nella struttura ad albero visuale.  
  
<a name="StylingRowsinaGridViewView"></a>
### <a name="styling-rows-in-a-gridview"></a>Applicazione di stili alle righe in GridView  
 Utilizzare <xref:System.Windows.Controls.GridViewRowPresenter> le <xref:System.Windows.Controls.GridViewHeaderRowPresenter> classi e per formattare <xref:System.Windows.Controls.GridView>e visualizzare le righe di un oggetto . Per un esempio di stile <xref:System.Windows.Controls.GridView> delle righe in una modalità di visualizzazione, vedere [stile di una riga in un controllo ListView che implementa un controllo GridView](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Problemi di allineamento durante l'uso di ItemContainerStyle  
 Per evitare problemi di allineamento tra le intestazioni di colonna e le celle, <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>non impostare una proprietà o specificare un modello che influisca sulla larghezza di un elemento in un oggetto . Ad esempio, non <xref:System.Windows.FrameworkElement.Margin%2A> impostare la <xref:System.Windows.Controls.ControlTemplate> proprietà <xref:System.Windows.Controls.CheckBox> o <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> specificare un <xref:System.Windows.Controls.ListView> che aggiunge un oggetto definito in un controllo. Specificare invece le proprietà e i modelli che <xref:System.Windows.Controls.GridView> influiscono sulla larghezza delle colonne direttamente nelle classi che definiscono una modalità di visualizzazione.  
  
 Ad esempio, per <xref:System.Windows.Controls.CheckBox> aggiungere un <xref:System.Windows.Controls.GridView> alle righe <xref:System.Windows.Controls.CheckBox> in <xref:System.Windows.DataTemplate>modalità di <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> visualizzazione, <xref:System.Windows.DataTemplate>aggiungere l'oggetto a a , quindi impostare la proprietà su tale .  
  
<a name="InteractingwithaGridViewControl"></a>
## <a name="user-interactions-with-a-gridview"></a>Interazioni dell'utente con GridView  
 Quando si <xref:System.Windows.Controls.GridView> utilizza un nell'applicazione, gli utenti possono <xref:System.Windows.Controls.GridView>interagire con e modificare la formattazione del file . Ad esempio, gli utenti possono riordinare le colonne, ridimensionare una colonna, selezionare gli elementi in una tabella e scorrere il contenuto. È inoltre possibile definire un gestore eventi che risponda quando un utente fa clic sul pulsante di intestazione di colonna. Il gestore eventi può eseguire operazioni come l'ordinamento dei dati visualizzati in <xref:System.Windows.Controls.GridView> in base al contenuto di una colonna.  
  
 Nell'elenco seguente vengono illustrate in <xref:System.Windows.Controls.GridView> modo più dettagliato le funzionalità di utilizzo per l'interazione dell'utente:  
  
- **Riordinare le colonne con il metodo di trascinamento della selezione.**  
  
     Gli utenti possono riordinare le colonne in un <xref:System.Windows.Controls.GridView> premendo il pulsante sinistro del mouse mentre si trova su un'intestazione di colonna e quindi trascinando la colonna in una nuova posizione. Mentre l'utente trascina l'intestazione di colonna, viene visualizzata una versione a virgola mobile dell'intestazione e una linea nera continua che indica dove inserire la colonna.  
  
     Se si desidera modificare lo stile predefinito per la <xref:System.Windows.Controls.ControlTemplate> versione <xref:System.Windows.Controls.GridViewColumnHeader> mobile di un'intestazione, specificare un per un tipo che viene attivato quando la <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> proprietà è impostata su . <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> Per altre informazioni vedere [Creare uno stile per un'intestazione di colonna GridView trascinata](how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
- **Ridimensionare una colonna in base al contenuto.**  
  
     Gli utenti possono fare doppio clic sulla barra gripper a destra di un'intestazione di colonna per adattare le dimensioni di una colonna al contenuto.  
  
    > [!NOTE]
    > È possibile <xref:System.Windows.Controls.GridViewColumn.Width%2A> impostare `Double.NaN` la proprietà su per produrre lo stesso effetto.  
  
- **Selezionare gli elementi di una riga.**  
  
     Gli utenti possono selezionare <xref:System.Windows.Controls.GridView>uno o più elementi in un file .  
  
     Se si desidera <xref:System.Windows.Style> modificare l'oggetto di un elemento selezionato, vedere [Utilizzare i trigger per applicare lo stile agli elementi selezionati in un controllo ListView](how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
- **Scorrere per visualizzare il contenuto che non è inizialmente visibile sullo schermo.**  
  
     Se le dimensioni <xref:System.Windows.Controls.GridView> di non è sufficientemente grande per visualizzare tutti gli elementi, gli utenti <xref:System.Windows.Controls.ScrollViewer> possono scorrere orizzontalmente o verticalmente utilizzando le barre di scorrimento, fornite da un controllo . A <xref:System.Windows.Controls.Primitives.ScrollBar> è nascosto se tutto il contenuto è visibile in una direzione specifica. Le intestazioni di colonna non scorrono mediante una barra di scorrimento verticale, ma scorrono in senso orizzontale.  
  
- **Interagire con le colonne facendo clic sui pulsanti di intestazione di colonna.**  
  
     Quando si fa clic su un pulsante di intestazione di colonna, è possibile ordinare i dati visualizzati nella colonna se è stato specificato un algoritmo di ordinamento.  
  
     È possibile <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestire l'evento per i pulsanti di intestazione di colonna per fornire funzionalità come un algoritmo di ordinamento. Per gestire <xref:System.Windows.Controls.Primitives.ButtonBase.Click> l'evento per una singola intestazione <xref:System.Windows.Controls.GridViewColumnHeader>di colonna, impostare un gestore eventi su . Per impostare un gestore eventi che gestisce l'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> per tutte le intestazioni di colonna, impostare il gestore sul <xref:System.Windows.Controls.ListView> controllo.  
  
<a name="Obtaining_Other_Custom_Views"></a>
## <a name="obtaining-other-custom-views"></a>Ottenere altre visualizzazioni personalizzate  
 La <xref:System.Windows.Controls.GridView> classe , derivata <xref:System.Windows.Controls.ViewBase> dalla classe astratta, è solo <xref:System.Windows.Controls.ListView> una delle possibili modalità di visualizzazione per la classe. È possibile creare altre <xref:System.Windows.Controls.ListView> visualizzazioni personalizzate <xref:System.Windows.Controls.ViewBase> per derivando dalla classe. Per un esempio di una modalità di visualizzazione personalizzata, vedere [Creare una modalità di visualizzazione personalizzata per un oggetto ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>
## <a name="gridview-supporting-classes"></a>Classi che supportano GridView  
 Le classi seguenti <xref:System.Windows.Controls.GridView> supportano la modalità di visualizzazione.  
  
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
- [Argomenti relativi alle procedure](listview-how-to-topics.md)
