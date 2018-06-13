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
ms.openlocfilehash: b6b0cc99c9833e514d2d52ecf139ab8e110f73e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555951"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Procedura: aggiungere dettagli di riga un controllo DataGrid
Quando si utilizza il <xref:System.Windows.Controls.DataGrid> (controllo), è possibile personalizzare la presentazione dei dati tramite l'aggiunta di una sezione dei dettagli di riga. L'aggiunta di una sezione dei dettagli di riga consente di raggruppare i dati in un modello che è possibile rendere visibile o compressa. Ad esempio, è possibile aggiungere i dettagli di riga per un <xref:System.Windows.Controls.DataGrid> che includa solo un riepilogo dei dati per ogni riga di <xref:System.Windows.Controls.DataGrid>, ma presenta più campi di dati quando l'utente seleziona una riga. Definire il modello per la sezione dei dettagli della riga nel <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> proprietà. Nella figura seguente viene illustrato un esempio di una sezione dei dettagli di riga.  
  
 ![DataGrid con i dettagli delle righe](../../../../docs/framework/wpf/controls/media/ndp-rowdetails.png "NDP_RowDetails")  
  
 Il modello di informazioni di riga è definire come inline XAML o come una risorsa. Entrambi gli approcci vengono visualizzati nelle procedure seguenti. Un modello di dati che viene aggiunto come una risorsa può essere utilizzata in tutto il progetto senza creare nuovamente il modello. Un modello di dati che viene aggiunto come inline XAML è accessibile solo dal controllo in cui è definito.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>Per visualizzare i dettagli di riga utilizzando il codice XAML inline  
  
1.  Creare un <xref:System.Windows.Controls.DataGrid> che visualizza i dati da un'origine dati.  
  
2.  Nell'elemento <xref:System.Windows.Controls.DataGrid> aggiungere un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  
  
3.  Creare un <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione dettagli della riga.  
  
     Il codice XAML seguente viene illustrata la <xref:System.Windows.Controls.DataGrid> e come definire il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline. Il <xref:System.Windows.Controls.DataGrid> Visualizza tre valori in ogni riga e tre ulteriori valori quando la riga è selezionata.  
  
     [!code-xaml[DataGrid_RowDetails#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     Il codice seguente viene illustrata la query viene utilizzata per selezionare i dati che viene visualizzati nel <xref:System.Windows.Controls.DataGrid>. In questo esempio, la query Seleziona dati da un'entità che contiene informazioni sul cliente.  
  
     [!code-csharp[DataGrid_RowDetails#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>Per visualizzare i dettagli di riga tramite una risorsa  
  
1.  Creare un <xref:System.Windows.Controls.DataGrid> che visualizza i dati da un'origine dati.  
  
2.  Aggiungere un <xref:System.Windows.FrameworkElement.Resources%2A> elemento all'elemento radice, ad esempio un <xref:System.Windows.Window> controllo o un <xref:System.Windows.Controls.Page> controllare o aggiungere un <xref:System.Windows.Application.Resources%2A> elemento per la <xref:System.Windows.Application> classe nel file app. XAML (o Application. XAML).  
  
3.  Nell'elemento risorse, creare un <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione dettagli della riga.  
  
     Il codice XAML seguente viene illustrata la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definito nel <xref:System.Windows.Application> classe.  
  
     [!code-xaml[DataGrid_RowDetails#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4.  Nel <xref:System.Windows.DataTemplate>, impostare il [direttiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md) su un valore che identifica in modo univoco il modello di dati.  
  
5.  Nel <xref:System.Windows.Controls.DataGrid> elemento, impostare il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> proprietà della risorsa definita nei passaggi precedenti. Assegnare la risorsa come una risorsa statica.  
  
     Il codice XAML seguente viene illustrata la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> impostata per la risorsa dell'esempio precedente.  
  
     [!code-xaml[DataGrid_RowDetails#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>Per impostare la visibilità e impedire lo scorrimento orizzontale per i dettagli delle righe  
  
1.  Se necessario, impostare il <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> proprietà per un <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> valore.  
  
     Per impostazione predefinita, il valore è impostato su <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>. È possibile impostare <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> per visualizzare i dettagli per tutte le righe o <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> per nascondere i dettagli per tutte le righe.  
  
2.  Se necessario, impostare il <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> proprietà `true` sezione lo scorrimento orizzontale per impedire la riga dei dettagli.
