---
title: Cenni preliminari su GridView
description: Informazioni sugli stili e i modelli per il controllo ListView Windows Presentation Foundation. Modificare il ControlTemplate per dare al controllo un aspetto univoco.
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 02a2182ef1fc893107e434f431b9fbe0b3fbcd08
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165923"
---
# <a name="gridview-overview"></a>Cenni preliminari su GridView
<xref:System.Windows.Controls.GridView>la modalità di visualizzazione è una delle modalità di visualizzazione di un <xref:System.Windows.Controls.ListView> controllo. La <xref:System.Windows.Controls.GridView> classe e le relative classi di supporto consentono all'utente e agli utenti di visualizzare le raccolte di elementi in una tabella che in genere usa i pulsanti come intestazioni di colonna interattive. In questo argomento viene presentata la <xref:System.Windows.Controls.GridView> classe e ne viene descritto l'utilizzo.  

<a name="DefiningaListViewthatusesGridViewView"></a>
## <a name="what-is-a-gridview-view"></a>Definizione della visualizzazione GridView  
 La <xref:System.Windows.Controls.GridView> modalità di visualizzazione consente di visualizzare un elenco di elementi di dati associando campi dati alle colonne e visualizzando un'intestazione di colonna per identificare il campo. Lo <xref:System.Windows.Controls.GridView> stile predefinito implementa i pulsanti come intestazioni di colonna. Utilizzando i pulsanti per le intestazioni di colonna, è possibile implementare importanti funzionalità di interazione dell'utente. ad esempio, gli utenti possono fare clic sull'intestazione di colonna per ordinare i <xref:System.Windows.Controls.GridView> dati in base al contenuto di una colonna specifica.  
  
> [!NOTE]
> I controlli Button <xref:System.Windows.Controls.GridView> utilizzati da per le intestazioni di colonna sono derivati da <xref:System.Windows.Controls.Primitives.ButtonBase> .  
  
 Nella figura seguente è illustrata una <xref:System.Windows.Controls.GridView> visualizzazione del <xref:System.Windows.Controls.ListView> contenuto.  

 ![Screenshot che mostra la visualizzazione GridView del contenuto di ListView.](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView>le colonne sono rappresentate da <xref:System.Windows.Controls.GridViewColumn> oggetti, che possono essere ridimensionati automaticamente in base al relativo contenuto. Facoltativamente, è possibile impostare in modo esplicito <xref:System.Windows.Controls.GridViewColumn> su una larghezza specifica. È possibile ridimensionare le colonne trascinando la barra gripper tra le intestazioni di colonna. È inoltre possibile aggiungere, rimuovere, sostituire e riordinare le colonne in modo dinamico perché questa funzionalità è incorporata in <xref:System.Windows.Controls.GridView> . Tuttavia, <xref:System.Windows.Controls.GridView> non è in grado di aggiornare direttamente i dati visualizzati.  
  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.Controls.GridView> che Visualizza i dati dei dipendenti. In questo esempio, <xref:System.Windows.Controls.ListView> definisce `EmployeeInfoDataSource` come <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> . Definizioni delle proprietà di <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> binding <xref:System.Windows.Controls.GridViewColumn> contenuto alle `EmployeeInfoDataSource` categorie di dati.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 La figura seguente illustra la tabella creata nell'esempio precedente. Il controllo GridView Visualizza i dati di un oggetto ItemsSource:

 ![Screenshot che mostra un ListView con l'output di GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>
## <a name="gridview-layout-and-style"></a>Layout e stile di GridView  
 Le celle di colonna e l'intestazione di colonna di <xref:System.Windows.Controls.GridViewColumn> hanno la stessa larghezza. Per impostazione predefinita, la larghezza di ogni colonna viene ridimensionata in base al contenuto. Facoltativamente, è possibile impostare una colonna a larghezza fissa.  
  
 Il contenuto dei dati correlati viene visualizzato in righe orizzontali. Ad esempio, nell'illustrazione precedente il cognome, il nome e l'ID di ogni dipendente vengono visualizzati come un insieme perché appaiono in una riga orizzontale.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>
### <a name="defining-and-styling-columns-in-a-gridview"></a>Definizione e applicazione di stili alle colonne in GridView  
 Quando si definisce il campo dati da visualizzare in un oggetto <xref:System.Windows.Controls.GridViewColumn> , usare le <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> proprietà, o <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> . La <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> proprietà ha la precedenza su una delle proprietà del modello.  
  
 Per specificare l'allineamento del contenuto in una colonna di un oggetto <xref:System.Windows.Controls.GridView> , definire un oggetto <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> . Non usare le <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> proprietà e <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> per il <xref:System.Windows.Controls.ListView> contenuto visualizzato tramite un <xref:System.Windows.Controls.GridView> .  
  
 Per specificare le proprietà del modello e dello stile per le intestazioni di colonna, usare le <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.GridViewColumn> classi, e <xref:System.Windows.Controls.GridViewColumnHeader> . Per altre informazioni, vedere [Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView](gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>
### <a name="adding-visual-elements-to-a-gridview"></a>Aggiunta di elementi visivi a GridView  
 Per aggiungere elementi visivi, ad esempio i <xref:System.Windows.Controls.CheckBox> <xref:System.Windows.Controls.Button> controlli e, a una <xref:System.Windows.Controls.GridView> modalità di visualizzazione, usare modelli o stili.  
  
 Se si definisce in modo esplicito un elemento visivo come elemento dati, può essere visualizzato solo una volta in un oggetto <xref:System.Windows.Controls.GridView> . Questa limitazione esiste perché un elemento può avere un solo padre e, di conseguenza, può essere visualizzato solo una volta nella struttura ad albero visuale.  
  
<a name="StylingRowsinaGridViewView"></a>
### <a name="styling-rows-in-a-gridview"></a>Applicazione di stili alle righe in GridView  
 Utilizzare le <xref:System.Windows.Controls.GridViewRowPresenter> <xref:System.Windows.Controls.GridViewHeaderRowPresenter> classi e per formattare e visualizzare le righe di un oggetto <xref:System.Windows.Controls.GridView> . Per un esempio di come applicare uno stile alle righe in una <xref:System.Windows.Controls.GridView> modalità di visualizzazione, vedere Applicare uno stile a una [riga in un controllo ListView che implementa un controllo GridView](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Problemi di allineamento durante l'uso di ItemContainerStyle  
 Per evitare problemi di allineamento tra le intestazioni di colonna e le celle, non impostare una proprietà o specificare un modello che influisca sulla larghezza di un elemento in un oggetto <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> . Ad esempio, non impostare la <xref:System.Windows.FrameworkElement.Margin%2A> proprietà o specificare un oggetto <xref:System.Windows.Controls.ControlTemplate> che aggiunge un oggetto <xref:System.Windows.Controls.CheckBox> a un oggetto <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> definito in un <xref:System.Windows.Controls.ListView> controllo. Specificare invece le proprietà e i modelli che influiscono sulla larghezza delle colonne direttamente sulle classi che definiscono una <xref:System.Windows.Controls.GridView> modalità di visualizzazione.  
  
 Ad esempio, per aggiungere un oggetto <xref:System.Windows.Controls.CheckBox> alle righe in <xref:System.Windows.Controls.GridView> modalità di visualizzazione, aggiungere <xref:System.Windows.Controls.CheckBox> a un oggetto <xref:System.Windows.DataTemplate> , quindi impostare la <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> proprietà su <xref:System.Windows.DataTemplate> .  
  
<a name="InteractingwithaGridViewControl"></a>
## <a name="user-interactions-with-a-gridview"></a>Interazioni dell'utente con GridView  
 Quando si utilizza un <xref:System.Windows.Controls.GridView> nell'applicazione, gli utenti possono interagire con e modificare la formattazione di <xref:System.Windows.Controls.GridView> . Ad esempio, gli utenti possono riordinare le colonne, ridimensionare una colonna, selezionare gli elementi in una tabella e scorrere il contenuto. È inoltre possibile definire un gestore eventi che risponda quando un utente fa clic sul pulsante di intestazione di colonna. Il gestore eventi può eseguire operazioni come l'ordinamento dei dati visualizzati in in base al <xref:System.Windows.Controls.GridView> contenuto di una colonna.  
  
 Nell'elenco seguente vengono descritte in modo più dettagliato le funzionalità di utilizzo di <xref:System.Windows.Controls.GridView> per l'interazione dell'utente:  
  
- **Riordinare le colonne con il metodo di trascinamento della selezione.**  
  
     Gli utenti possono riordinare le colonne in un oggetto <xref:System.Windows.Controls.GridView> premendo il pulsante sinistro del mouse mentre si trova su un'intestazione di colonna e quindi trascinando la colonna in una nuova posizione. Mentre l'utente trascina l'intestazione di colonna, viene visualizzata una versione a virgola mobile dell'intestazione e una linea nera continua che indica dove inserire la colonna.  
  
     Se si desidera modificare lo stile predefinito per la versione mobile di un'intestazione, specificare un oggetto <xref:System.Windows.Controls.ControlTemplate> per un <xref:System.Windows.Controls.GridViewColumnHeader> tipo che viene attivato quando la <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> proprietà è impostata su <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> . Per altre informazioni vedere [Creare uno stile per un'intestazione di colonna GridView trascinata](how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
- **Ridimensionare una colonna in base al contenuto.**  
  
     Gli utenti possono fare doppio clic sulla barra gripper a destra di un'intestazione di colonna per adattare le dimensioni di una colonna al contenuto.  
  
    > [!NOTE]
    > È possibile impostare la <xref:System.Windows.Controls.GridViewColumn.Width%2A> proprietà su `Double.NaN` per produrre lo stesso effetto.  
  
- **Selezionare gli elementi di una riga.**  
  
     Gli utenti possono selezionare uno o più elementi in un <xref:System.Windows.Controls.GridView> .  
  
     Per modificare la <xref:System.Windows.Style> proprietà di un elemento selezionato, vedere usare i [trigger per applicare uno stile agli elementi selezionati in un controllo ListView](how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
- **Scorrere per visualizzare il contenuto che non è inizialmente visibile sullo schermo.**  
  
     Se la dimensione di <xref:System.Windows.Controls.GridView> non è sufficiente per visualizzare tutti gli elementi, gli utenti possono scorrere orizzontalmente o verticalmente usando le barre di scorrimento, fornite da un <xref:System.Windows.Controls.ScrollViewer> controllo. Un oggetto <xref:System.Windows.Controls.Primitives.ScrollBar> è nascosto se tutto il contenuto è visibile in una direzione specifica. Le intestazioni di colonna non scorrono mediante una barra di scorrimento verticale, ma scorrono in senso orizzontale.  
  
- **Interagire con le colonne facendo clic sui pulsanti di intestazione di colonna.**  
  
     Quando si fa clic su un pulsante di intestazione di colonna, è possibile ordinare i dati visualizzati nella colonna se è stato specificato un algoritmo di ordinamento.  
  
     È possibile gestire l' <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento per i pulsanti di intestazione di colonna per fornire funzionalità come un algoritmo di ordinamento. Per gestire l' <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento per una singola intestazione di colonna, impostare un gestore eventi su <xref:System.Windows.Controls.GridViewColumnHeader> . Per impostare un gestore eventi che gestisce l' <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento per tutte le intestazioni di colonna, impostare il gestore sul <xref:System.Windows.Controls.ListView> controllo.  
  
<a name="Obtaining_Other_Custom_Views"></a>
## <a name="obtaining-other-custom-views"></a>Ottenere altre visualizzazioni personalizzate  
 La <xref:System.Windows.Controls.GridView> classe, derivata dalla <xref:System.Windows.Controls.ViewBase> classe astratta, è solo una delle possibili modalità di visualizzazione per la <xref:System.Windows.Controls.ListView> classe. È possibile creare altre visualizzazioni personalizzate per <xref:System.Windows.Controls.ListView> mediante derivazione dalla <xref:System.Windows.Controls.ViewBase> classe. Per un esempio di una modalità di visualizzazione personalizzata, vedere [Creare una modalità di visualizzazione personalizzata per un oggetto ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>
## <a name="gridview-supporting-classes"></a>Classi che supportano GridView  
 Le classi seguenti supportano la <xref:System.Windows.Controls.GridView> modalità di visualizzazione.  
  
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
- [Procedure relative](listview-how-to-topics.md)
