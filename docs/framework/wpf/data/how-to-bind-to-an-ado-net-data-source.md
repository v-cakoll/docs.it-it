---
title: "Procedura: eseguire l'associazione a un'origine dati ADO.NET"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: c9e16b9fd100eb9aec7bee2f94307aa80371d5ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556861"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a>Procedura: eseguire l'associazione a un'origine dati ADO.NET
In questo esempio viene illustrato come associare un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> il controllo a un [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato un oggetto `OleDbConnection` per la connessione all'origine dati che è un file `Access MDB` specificato nella stringa di connessione. Dopo aver stabilito la connessione viene creato l'oggetto `OleDbDataAdpater` . L'oggetto `OleDbDataAdpater` esegue un'istruzione select [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] per recuperare il recordset dal database. I risultati del comando [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] sono memorizzati in un `DataTable` di `DataSet` chiamando il metodo `Fill` di `OleDbDataAdapter`. `DataTable` in questo esempio è denominato `BookTable`. Nell'esempio viene quindi impostato il <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà del <xref:System.Windows.Controls.ListBox> per il `DataSet` oggetto.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 È possibile associare il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà del <xref:System.Windows.Controls.ListBox> a `BookTable` del `DataSet`:  
  
 [!code-xaml[ADODataSet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]  
  
 `BookItemTemplate` è il <xref:System.Windows.DataTemplate> che definisce la modalità con cui i dati vengono visualizzati:  
  
 [!code-xaml[ADODataSet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]  
  
 `IntColorConverter` converte un oggetto `int` in un colore. Con l'utilizzo di questo convertitore, il <xref:System.Windows.Controls.TextBlock.Background%2A> colore del terzo <xref:System.Windows.Controls.TextBlock> è di colore verde se il valore di `NumPages` è minore di 350 in caso contrario. L'implementazione del convertitore non viene visualizzata qui.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Data.BindingListCollectionView>  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
