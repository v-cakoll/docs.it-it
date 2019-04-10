---
title: 'Procedura: Aggiungere dettagli di riga a un controllo DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: d5b6539f3d379088528b9654861267988b6fc69b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317890"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Procedura: Aggiungere dettagli di riga a un controllo DataGrid
Quando si usa il <xref:System.Windows.Controls.DataGrid> (controllo), è possibile personalizzare la presentazione dei dati mediante l'aggiunta di una sezione di dettagli della riga. Aggiunta di una sezione di dettagli di riga consente di raggruppare i dati in un modello che è possibile rendere visibile o compressa. Ad esempio, è possibile aggiungere i dettagli delle righe per un <xref:System.Windows.Controls.DataGrid> che presenta solo un riepilogo dei dati per ogni riga nel <xref:System.Windows.Controls.DataGrid>, ma presenta più campi di dati quando l'utente seleziona una riga. Viene definito il modello per la sezione dettagli della riga nel <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> proprietà. La figura seguente mostra un esempio di una sezione di dettagli della riga.  
  
 ![DataGrid con i dettagli della riga](./media/ndp-rowdetails.png "NDP_RowDetails")  
  
 Il modello di dettagli della riga è definire come inline XAML o come una risorsa. Entrambi gli approcci sono illustrati nelle procedure seguenti. Un modello di dati che viene aggiunto come una risorsa può essere usata nel corso del progetto senza creare di nuovo il modello. Un modello di dati che viene aggiunto come inline XAML è accessibile solo dal controllo in cui è definito.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>Per visualizzare i dettagli della riga con inline XAML  
  
1. Creare un <xref:System.Windows.Controls.DataGrid> che visualizza i dati da un'origine dati.  
  
2. Nell'elemento <xref:System.Windows.Controls.DataGrid> aggiungere un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  
  
3. Creare un <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione di dettagli di riga.  
  
     Nell'esempio di XAML seguente viene illustrato il <xref:System.Windows.Controls.DataGrid> e come definire il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline. Il <xref:System.Windows.Controls.DataGrid> consente di visualizzare tre valori in ogni riga e tre i valori più quando la riga è selezionata.  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     Il codice seguente mostra la query che consente di selezionare i dati che viene visualizzati nei <xref:System.Windows.Controls.DataGrid>. In questo esempio, la query Seleziona i dati da un'entità che contiene informazioni sul cliente.  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>Per visualizzare i dettagli della riga tramite una risorsa  
  
1. Creare un <xref:System.Windows.Controls.DataGrid> che visualizza i dati da un'origine dati.  
  
2. Aggiungere un <xref:System.Windows.FrameworkElement.Resources%2A> elemento e l'elemento radice, ad esempio un <xref:System.Windows.Window> controllo o una <xref:System.Windows.Controls.Page> controllare o aggiungere un <xref:System.Windows.Application.Resources%2A> elemento per il <xref:System.Windows.Application> classe nel file app. XAML (o Application. XAML).  
  
3. Nell'elemento resources, creare un <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione di dettagli di riga.  
  
     XAML seguente il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definito nel <xref:System.Windows.Application> classe.  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. Nel <xref:System.Windows.DataTemplate>, impostare il [direttiva X:Key](../../xaml-services/x-key-directive.md) su un valore che identifica in modo univoco il modello di dati.  
  
5. Nel <xref:System.Windows.Controls.DataGrid> elemento, impostare il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> proprietà per la risorsa definita nei passaggi precedenti. Assegnare la risorsa come una risorsa statica.  
  
     L'esempio di XAML seguente illustra il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> proprietà è impostata per la risorsa dell'esempio precedente.  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>Per impostare la visibilità e impedire lo scorrimento orizzontale per i dettagli della riga  
  
1. Se necessario, impostare il <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> proprietà su un <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> valore.  
  
     Per impostazione predefinita, il valore è impostato su <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>. È possibile impostarla su <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> per visualizzare i dettagli per tutte le righe o <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> per nascondere i dettagli per tutte le righe.  
  
2. Se necessario, impostare il <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> proprietà `true` sezione effettuato uno scorrimento orizzontale per impedire la riga dei dettagli.
