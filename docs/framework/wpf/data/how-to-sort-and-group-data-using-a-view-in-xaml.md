---
title: 'Procedura: ordinare e raggruppare i dati tramite una visualizzazione di XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: 9e42dd330535f71438ab7af3dca9d078e9dfd8d3
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460121"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="fa392-102">Procedura: ordinare e raggruppare i dati tramite una visualizzazione di XAML</span><span class="sxs-lookup"><span data-stu-id="fa392-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="fa392-103">Questo esempio illustra come creare una vista di una raccolta dati in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa392-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="fa392-104">Le visualizzazioni consentono le funzionalità di raggruppamento, ordinamento, filtro e la nozione di elemento corrente.</span><span class="sxs-lookup"><span data-stu-id="fa392-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa392-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa392-105">Example</span></span>  
 <span data-ttu-id="fa392-106">Nell'esempio seguente, la risorsa statica denominata *Places* viene definita come una raccolta di oggetti *Place* , in cui ogni oggetto *Place* è costituito da un nome di città e dallo stato.</span><span class="sxs-lookup"><span data-stu-id="fa392-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="fa392-107">Il prefisso *src* viene mappato allo spazio dei nomi in cui è definita *l'origine dati* .</span><span class="sxs-lookup"><span data-stu-id="fa392-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="fa392-108">Il prefisso *SCM* esegue il mapping a `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` e *dat* viene mappato a `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span><span class="sxs-lookup"><span data-stu-id="fa392-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="fa392-109">Nell'esempio seguente viene creata una vista della raccolta di dati ordinata in base al nome della città e raggruppata in base allo stato.</span><span class="sxs-lookup"><span data-stu-id="fa392-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="fa392-110">La vista può quindi essere un'origine di binding, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="fa392-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="fa392-111">Per i binding ai dati XML definiti in una risorsa <xref:System.Windows.Data.XmlDataProvider>, anteporre il nome XML a un simbolo @.</span><span class="sxs-lookup"><span data-stu-id="fa392-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="fa392-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa392-112">See also</span></span>

- <xref:System.Windows.Data.CollectionViewSource>
- [<span data-ttu-id="fa392-113">Ottenere la visualizzazione predefinita di una raccolta dati</span><span class="sxs-lookup"><span data-stu-id="fa392-113">Get the Default View of a Data Collection</span></span>](how-to-get-the-default-view-of-a-data-collection.md)
- [<span data-ttu-id="fa392-114">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="fa392-114">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="fa392-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="fa392-115">How-to Topics</span></span>](data-binding-how-to-topics.md)
