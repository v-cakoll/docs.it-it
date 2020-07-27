---
title: 'Procedura: Aggiungere dettagli di riga a un controllo DataGrid'
description: Informazioni su come personalizzare la presentazione dei dati quando si usa il controllo DataGrid Windows Presentation Foundation aggiungendo una sezione dettagli riga.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: 8fd6b07f454681a0eed70d7a6208cfcc426dc920
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164946"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a>Procedura: Aggiungere dettagli di riga a un controllo DataGrid
Quando si usa il <xref:System.Windows.Controls.DataGrid> controllo, è possibile personalizzare la presentazione dei dati aggiungendo una sezione dettagli riga. L'aggiunta di una sezione dettagli riga consente di raggruppare alcuni dati in un modello che è facoltativamente visibile o compresso. Ad esempio, è possibile aggiungere dettagli di riga a un oggetto <xref:System.Windows.Controls.DataGrid> che presenta solo un riepilogo dei dati per ogni riga in <xref:System.Windows.Controls.DataGrid> , ma presenta più campi dati quando l'utente seleziona una riga. Definire il modello per la sezione dettagli riga della <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Proprietà. Nella figura seguente viene illustrato un esempio di sezione dettagli riga.  
  
 ![DataGrid con i dettagli della riga](./media/ndp-rowdetails.png "NDP_RowDetails")  
  
 Il modello di dettagli della riga viene definito come XAML inline o come risorsa. Entrambi gli approcci sono illustrati nelle procedure riportate di seguito. Un modello di dati aggiunto come risorsa può essere usato in tutto il progetto senza dover ricreare il modello. Un modello di dati aggiunto come XAML inline è accessibile solo dal controllo in cui è definito.  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a>Per visualizzare i dettagli delle righe utilizzando XAML inline  
  
1. Creare un oggetto <xref:System.Windows.Controls.DataGrid> che Visualizza i dati da un'origine dati.  
  
2. Nell'elemento <xref:System.Windows.Controls.DataGrid> aggiungere un elemento <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>.  
  
3. Creare un oggetto <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione dettagli riga.  
  
     Nel codice XAML riportato di seguito vengono illustrati <xref:System.Windows.Controls.DataGrid> e come definire l'oggetto <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline. Il <xref:System.Windows.Controls.DataGrid> Visualizza tre valori in ogni riga e altri tre valori quando la riga è selezionata.  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     Nel codice seguente viene illustrata la query utilizzata per selezionare i dati visualizzati in <xref:System.Windows.Controls.DataGrid> . In questo esempio la query seleziona i dati da un'entità che contiene informazioni sul cliente.  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a>Per visualizzare i dettagli delle righe utilizzando una risorsa  
  
1. Creare un oggetto <xref:System.Windows.Controls.DataGrid> che Visualizza i dati da un'origine dati.  
  
2. Aggiungere un <xref:System.Windows.FrameworkElement.Resources%2A> elemento all'elemento radice, ad esempio un <xref:System.Windows.Window> controllo o un <xref:System.Windows.Controls.Page> controllo, o aggiungere un <xref:System.Windows.Application.Resources%2A> elemento alla <xref:System.Windows.Application> classe nel file app. XAML (o Application. Xaml).  
  
3. Nell'elemento resources creare un oggetto <xref:System.Windows.DataTemplate> che definisce l'aspetto della sezione dettagli riga.  
  
     Nel codice XAML seguente viene illustrato il <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definito nella <xref:System.Windows.Application> classe.  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. In <xref:System.Windows.DataTemplate> impostare la [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) su un valore che identifichi in modo univoco il modello di dati.  
  
5. Nell' <xref:System.Windows.Controls.DataGrid> elemento impostare la proprietà sulla <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> risorsa definita nei passaggi precedenti. Assegnare la risorsa come risorsa statica.  
  
     Il codice XAML seguente mostra la <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> proprietà impostata sulla risorsa dell'esempio precedente.  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a>Per impostare la visibilità ed evitare lo scorrimento orizzontale per i dettagli delle righe  
  
1. Se necessario, impostare la <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> proprietà su un <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> valore.  
  
     Per impostazione predefinita, il valore è impostato su <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>. È possibile impostarlo su <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> per visualizzare i dettagli di tutte le righe o <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> per nascondere i dettagli di tutte le righe.  
  
2. Se necessario, impostare la <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> proprietà su `true` per impedire lo scorrimento orizzontale della sezione dettagli riga.
