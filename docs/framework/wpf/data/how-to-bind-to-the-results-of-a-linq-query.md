---
title: 'Procedura: Eseguire il binding ai risultati di una query LINQ'
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 5464ee9c59a7c99a83774a7535b9b3c422c1d2e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644417"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a><span data-ttu-id="f12ad-102">Procedura: Eseguire il binding ai risultati di una query LINQ</span><span class="sxs-lookup"><span data-stu-id="f12ad-102">How to: Bind to the Results of a LINQ Query</span></span>
<span data-ttu-id="f12ad-103">In questo esempio viene illustrato come eseguire una query LINQ e quindi eseguire l'associazione ai risultati.</span><span class="sxs-lookup"><span data-stu-id="f12ad-103">This example demonstrates how to run a LINQ query and then bind to the results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f12ad-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f12ad-104">Example</span></span>  
 <span data-ttu-id="f12ad-105">L'esempio seguente crea due caselle di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="f12ad-105">The following example creates two list boxes.</span></span> <span data-ttu-id="f12ad-106">Prima casella di riepilogo contiene tre voci di elenco.</span><span class="sxs-lookup"><span data-stu-id="f12ad-106">The first list box contains three list items.</span></span>  
  
 [!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="f12ad-107">Selezione di un elemento dalla casella di riepilogo prima richiama il gestore eventi seguente.</span><span class="sxs-lookup"><span data-stu-id="f12ad-107">Selecting an item from the first list box invokes the following event handler.</span></span> <span data-ttu-id="f12ad-108">In questo esempio `Tasks` è una raccolta di `Task` oggetti.</span><span class="sxs-lookup"><span data-stu-id="f12ad-108">In this example, `Tasks` is a collection of `Task` objects.</span></span> <span data-ttu-id="f12ad-109">Il `Task` classe ha una proprietà denominata `Priority`.</span><span class="sxs-lookup"><span data-stu-id="f12ad-109">The `Task` class has a property named `Priority`.</span></span> <span data-ttu-id="f12ad-110">Questo gestore eventi viene eseguita una query LINQ che restituisce la raccolta di `Task` gli oggetti che hanno il valore di priorità selezionata e quindi imposta come il <xref:System.Windows.FrameworkElement.DataContext%2A>:</span><span class="sxs-lookup"><span data-stu-id="f12ad-110">This event handler runs a LINQ query that returns the collection of `Task` objects that have the selected priority value, and then sets that as the <xref:System.Windows.FrameworkElement.DataContext%2A>:</span></span>  
  
 [!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 <span data-ttu-id="f12ad-111">La seconda casella di riepilogo esegue l'associazione alla raccolta perché relativi <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> valore è impostato su `{Binding}`.</span><span class="sxs-lookup"><span data-stu-id="f12ad-111">The second list box binds to that collection because its <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> value is set to `{Binding}`.</span></span> <span data-ttu-id="f12ad-112">Di conseguenza, viene visualizzato l'insieme restituito (in base il `myTaskTemplate` <xref:System.Windows.DataTemplate>).</span><span class="sxs-lookup"><span data-stu-id="f12ad-112">As a result, it displays the returned collection (based on the `myTaskTemplate`<xref:System.Windows.DataTemplate>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f12ad-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f12ad-113">See also</span></span>

- [<span data-ttu-id="f12ad-114">Rendere i dati disponibili per l'associazione in XAML</span><span class="sxs-lookup"><span data-stu-id="f12ad-114">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
- [<span data-ttu-id="f12ad-115">Eseguire l'associazione a una raccolta e visualizzare informazioni in base alla selezione</span><span class="sxs-lookup"><span data-stu-id="f12ad-115">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="f12ad-116">Novità di WPF versione 4.5</span><span class="sxs-lookup"><span data-stu-id="f12ad-116">What's New in WPF Version 4.5</span></span>](../getting-started/whats-new.md)
- [<span data-ttu-id="f12ad-117">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="f12ad-117">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="f12ad-118">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="f12ad-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
