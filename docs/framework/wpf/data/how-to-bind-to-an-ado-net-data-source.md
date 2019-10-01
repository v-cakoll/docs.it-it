---
title: "Procedura: Eseguire l'associazione a un'origine dati ADO.NET"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: dbe34cba8f01320fbf37beea65ed95656e09395c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697136"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a>Procedura: Eseguire l'associazione a un'origine dati ADO.NET

Questo esempio illustra come associare un controllo [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> a un ADO.NET `DataSet`.

## <a name="example"></a>Esempio

In questo esempio viene usato un oggetto `OleDbConnection` per la connessione all'origine dati che è un file `Access MDB` specificato nella stringa di connessione. Dopo aver stabilito la connessione viene creato l'oggetto `OleDbDataAdapter` . L'oggetto `OleDbDataAdapter` esegue un'istruzione SELECT Structured Query Language (SQL) per recuperare il recordset dal database. I risultati del comando SQL vengono archiviati in un `DataTable` del `DataSet` chiamando il metodo `Fill` del `OleDbDataAdapter`. `DataTable` in questo esempio è denominato `BookTable`. Nell'esempio viene quindi impostata la proprietà <xref:System.Windows.FrameworkElement.DataContext%2A> del <xref:System.Windows.Controls.ListBox> sull'oggetto `DataSet`.

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

È quindi possibile associare la proprietà <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> del <xref:System.Windows.Controls.ListBox> al `BookTable` del `DataSet`:

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

`BookItemTemplate` è il <xref:System.Windows.DataTemplate> che definisce il modo in cui vengono visualizzati i dati:

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

`IntColorConverter` converte un oggetto `int` in un colore. Con l'uso di questo convertitore, il colore <xref:System.Windows.Controls.TextBlock.Background%2A> della terza <xref:System.Windows.Controls.TextBlock> viene visualizzato in verde se il valore di `NumPages` è minore di 350 e rosso in caso contrario. L'implementazione del convertitore non viene visualizzata qui.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.BindingListCollectionView>
- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
