---
title: "Procedura: eseguire l'associazione ai risultati di una query LINQ"
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: d374bb69b6b7e022497403b9591b27e9ad7e2395
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554993"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="6e36a-102">Procedura: eseguire l'associazione ai risultati di una query LINQ</span><span class="sxs-lookup"><span data-stu-id="6e36a-102">How to: Bind to the Results of a LINQ Query</span></span>
<span data-ttu-id="6e36a-103">In questo esempio viene illustrato come eseguire una query LINQ e associare quindi i risultati.</span><span class="sxs-lookup"><span data-stu-id="6e36a-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e36a-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e36a-104">Example</span></span>  
 <span data-ttu-id="6e36a-105">L'esempio seguente crea due caselle di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="6e36a-105">The following example creates two list boxes.</span></span> <span data-ttu-id="6e36a-106">Prima casella di riepilogo contiene tre voci di elenco.</span><span class="sxs-lookup"><span data-stu-id="6e36a-106">The first list box contains three list items.</span></span>  
  
 [!code-xaml[LinqExample#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="6e36a-107">Selezione di un elemento dalla casella di riepilogo prima richiama il seguente gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="6e36a-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="6e36a-108">In questo esempio, `Tasks` è una raccolta di `Task` oggetti.</span><span class="sxs-lookup"><span data-stu-id="6e36a-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="6e36a-109">Il `Task` classe dispone di una proprietà denominata `Priority`.</span><span class="sxs-lookup"><span data-stu-id="6e36a-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="6e36a-110">Questo gestore eventi viene eseguita una query LINQ che restituisce la raccolta di `Task` gli oggetti che hanno il valore di priorità selezionata e quindi imposta come il <xref:System.Windows.FrameworkElement.DataContext%2A>:</span><span class="sxs-lookup"><span data-stu-id="6e36a-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>  
  
 [!code-csharp[LinqExample#Using](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 <span data-ttu-id="6e36a-111">Seconda casella di riepilogo viene associata a tale raccolta, in quanto il relativo <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> è impostato su `{Binding}`.</span><span class="sxs-lookup"><span data-stu-id="6e36a-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="6e36a-112">Di conseguenza, Visualizza la raccolta restituita (in base il `myTaskTemplate` <xref:System.Windows.DataTemplate>).</span><span class="sxs-lookup"><span data-stu-id="6e36a-112">As a result, it displays the returned collection (based on the `myTaskTemplate`<xref:System.Windows.DataTemplate>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e36a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e36a-113">See Also</span></span>  
 [<span data-ttu-id="6e36a-114">Rendere i dati disponibili per l'associazione in XAML</span><span class="sxs-lookup"><span data-stu-id="6e36a-114">Make Data Available for Binding in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)  
 [<span data-ttu-id="6e36a-115">Eseguire l'associazione a una raccolta e visualizzare informazioni in base alla selezione</span><span class="sxs-lookup"><span data-stu-id="6e36a-115">Bind to a Collection and Display Information Based on Selection</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [<span data-ttu-id="6e36a-116">Novità di WPF versione 4.5</span><span class="sxs-lookup"><span data-stu-id="6e36a-116">What's New in WPF Version 4.5</span></span>](../../../../docs/framework/wpf/getting-started/whats-new.md)  
 [<span data-ttu-id="6e36a-117">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="6e36a-117">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="6e36a-118">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="6e36a-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
