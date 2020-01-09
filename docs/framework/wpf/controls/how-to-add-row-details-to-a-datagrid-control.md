---
title: 'Procedura: aggiungere dettagli di riga un controllo DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: 4db414e1907d42071f7251c390077d4020fa577c
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559677"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Procedura: aggiungere dettagli di riga un controllo DataGrid
Quando si usa il controllo <xref:System.Windows.Controls.DataGrid>, è possibile personalizzare la presentazione dei dati aggiungendo una sezione dettagli riga. L'aggiunta di una sezione dettagli riga consente di raggruppare alcuni dati in un modello che è facoltativamente visibile o compresso. È ad esempio possibile aggiungere dettagli di riga a una <xref:System.Windows.Controls.DataGrid> che presenta solo un riepilogo dei dati per ogni riga del <xref:System.Windows.Controls.DataGrid>, ma presenta più campi dati quando l'utente seleziona una riga. Definire il modello per la sezione dettagli riga nella proprietà <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>. Nella figura seguente viene illustrato un esempio di sezione dettagli riga.  
  
 ![DataGrid visualizzato con dettagli riga](./media/ndp-rowdetails.png "NDP_RowDetails")  
  
 Il modello di dettagli della riga viene definito come XAML inline o come risorsa. Entrambi gli approcci sono illustrati nelle procedure riportate di seguito. Un modello di dati aggiunto come risorsa può essere usato in tutto il progetto senza dover ricreare il modello. Un modello di dati aggiunto come XAML inline è accessibile solo dal controllo in cui è definito.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>Per visualizzare i dettagli delle righe utilizzando XAML inline  
  
1. Creare una <xref:System.Windows.Controls.DataGrid> che visualizzi i dati di un'origine dati.  
  
2. Nell'elemento <xref:System.Windows.Controls.DataGrid> aggiungere un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  
  
3. Creare una <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione dettagli riga.  
  
     Il codice XAML seguente illustra il <xref:System.Windows.Controls.DataGrid> e come definire il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline. Il <xref:System.Windows.Controls.DataGrid> Visualizza tre valori in ogni riga e altri tre valori quando la riga è selezionata.  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     Nel codice seguente viene illustrata la query utilizzata per selezionare i dati visualizzati nel <xref:System.Windows.Controls.DataGrid>. In questo esempio la query seleziona i dati da un'entità che contiene informazioni sul cliente.  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>Per visualizzare i dettagli delle righe utilizzando una risorsa  
  
1. Creare una <xref:System.Windows.Controls.DataGrid> che visualizzi i dati di un'origine dati.  
  
2. Aggiungere un elemento <xref:System.Windows.FrameworkElement.Resources%2A> all'elemento radice, ad esempio un controllo <xref:System.Windows.Window> o un controllo <xref:System.Windows.Controls.Page>, oppure aggiungere un elemento <xref:System.Windows.Application.Resources%2A> alla classe <xref:System.Windows.Application> nel file app. XAML (o Application. Xaml).  
  
3. Nell'elemento resources creare un <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione dettagli riga.  
  
     Il codice XAML seguente illustra il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definito nella classe <xref:System.Windows.Application>.  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. Nella <xref:System.Windows.DataTemplate>impostare la [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) su un valore che identifica in modo univoco il modello di dati.  
  
5. Nell'elemento <xref:System.Windows.Controls.DataGrid> impostare la proprietà <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> sulla risorsa definita nei passaggi precedenti. Assegnare la risorsa come risorsa statica.  
  
     Il codice XAML seguente mostra la proprietà <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> impostata sulla risorsa dell'esempio precedente.  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>Per impostare la visibilità ed evitare lo scorrimento orizzontale per i dettagli delle righe  
  
1. Se necessario, impostare la proprietà <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> su un valore <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>.  
  
     Per impostazione predefinita, il valore è impostato su <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>. È possibile impostarlo su <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> per visualizzare i dettagli di tutte le righe o <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> per nascondere i dettagli di tutte le righe.  
  
2. Se necessario, impostare la proprietà <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> su `true` per impedire lo scorrimento orizzontale della sezione dettagli riga.
