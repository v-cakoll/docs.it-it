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
# <a name="how-to-bind-to-an-adonet-data-source"></a><span data-ttu-id="cb643-102">Procedura: Eseguire l'associazione a un'origine dati ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cb643-102">How to: Bind to an ADO.NET Data Source</span></span>

<span data-ttu-id="cb643-103">Questo esempio illustra come associare un controllo [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> a un ADO.NET `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="cb643-103">This example shows how to bind a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <xref:System.Windows.Controls.ListBox> control to an ADO.NET `DataSet`.</span></span>

## <a name="example"></a><span data-ttu-id="cb643-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="cb643-104">Example</span></span>

<span data-ttu-id="cb643-105">In questo esempio viene usato un oggetto `OleDbConnection` per la connessione all'origine dati che è un file `Access MDB` specificato nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="cb643-105">In this example, an `OleDbConnection` object is used to connect to the data source which is an `Access MDB` file that is specified in the connection string.</span></span> <span data-ttu-id="cb643-106">Dopo aver stabilito la connessione viene creato l'oggetto `OleDbDataAdapter` .</span><span class="sxs-lookup"><span data-stu-id="cb643-106">After the connection is established, an `OleDbDataAdapter` object is created.</span></span> <span data-ttu-id="cb643-107">L'oggetto `OleDbDataAdapter` esegue un'istruzione SELECT Structured Query Language (SQL) per recuperare il recordset dal database.</span><span class="sxs-lookup"><span data-stu-id="cb643-107">The `OleDbDataAdapter` object executes a select Structured Query Language (SQL) statement to retrieve the recordset from the database.</span></span> <span data-ttu-id="cb643-108">I risultati del comando SQL vengono archiviati in un `DataTable` del `DataSet` chiamando il metodo `Fill` del `OleDbDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="cb643-108">The results from the SQL command are stored in a `DataTable` of the `DataSet` by calling the `Fill` method of the `OleDbDataAdapter`.</span></span> <span data-ttu-id="cb643-109">`DataTable` in questo esempio è denominato `BookTable`.</span><span class="sxs-lookup"><span data-stu-id="cb643-109">The `DataTable` in this example is named `BookTable`.</span></span> <span data-ttu-id="cb643-110">Nell'esempio viene quindi impostata la proprietà <xref:System.Windows.FrameworkElement.DataContext%2A> del <xref:System.Windows.Controls.ListBox> sull'oggetto `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="cb643-110">The example then sets the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the <xref:System.Windows.Controls.ListBox> to the `DataSet` object.</span></span>

[!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
[!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]

<span data-ttu-id="cb643-111">È quindi possibile associare la proprietà <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> del <xref:System.Windows.Controls.ListBox> al `BookTable` del `DataSet`:</span><span class="sxs-lookup"><span data-stu-id="cb643-111">We can then bind the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to `BookTable` of the `DataSet`:</span></span>

[!code-xaml[ADODataSet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]

<span data-ttu-id="cb643-112">`BookItemTemplate` è il <xref:System.Windows.DataTemplate> che definisce il modo in cui vengono visualizzati i dati:</span><span class="sxs-lookup"><span data-stu-id="cb643-112">`BookItemTemplate` is the <xref:System.Windows.DataTemplate> that defines how the data appears:</span></span>

[!code-xaml[ADODataSet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]

<span data-ttu-id="cb643-113">`IntColorConverter` converte un oggetto `int` in un colore.</span><span class="sxs-lookup"><span data-stu-id="cb643-113">The `IntColorConverter` converts an `int` to a color.</span></span> <span data-ttu-id="cb643-114">Con l'uso di questo convertitore, il colore <xref:System.Windows.Controls.TextBlock.Background%2A> della terza <xref:System.Windows.Controls.TextBlock> viene visualizzato in verde se il valore di `NumPages` è minore di 350 e rosso in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="cb643-114">With the use of this converter, the <xref:System.Windows.Controls.TextBlock.Background%2A> color of the third <xref:System.Windows.Controls.TextBlock> appears green if the value of `NumPages` is less than 350 and red otherwise.</span></span> <span data-ttu-id="cb643-115">L'implementazione del convertitore non viene visualizzata qui.</span><span class="sxs-lookup"><span data-stu-id="cb643-115">The implementation of the converter is not shown here.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb643-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb643-116">See also</span></span>

- <xref:System.Windows.Data.BindingListCollectionView>
- [<span data-ttu-id="cb643-117">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="cb643-117">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="cb643-118">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="cb643-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
