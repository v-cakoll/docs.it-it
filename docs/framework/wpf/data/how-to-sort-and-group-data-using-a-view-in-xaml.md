---
title: 'Procedura: ordinare e raggruppare i dati tramite una visualizzazione di XAML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1bfa1941e6352372712debb5a5243bdd24810aac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="1dfdc-102">Procedura: ordinare e raggruppare i dati tramite una visualizzazione di XAML</span><span class="sxs-lookup"><span data-stu-id="1dfdc-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="1dfdc-103">In questo esempio viene illustrato come creare una visualizzazione di una raccolta di dati in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1dfdc-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="1dfdc-104">Le viste consentono per le funzionalità di raggruppamento, ordinamento, filtro e la nozione di un elemento corrente.</span><span class="sxs-lookup"><span data-stu-id="1dfdc-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1dfdc-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="1dfdc-105">Example</span></span>  
 <span data-ttu-id="1dfdc-106">Nell'esempio seguente, la risorsa statica denominata *inserisce* è definito come una raccolta di *sul posto* oggetti, in cui ogni *sul posto* oggetto è costituito da un nome di città e la stato.</span><span class="sxs-lookup"><span data-stu-id="1dfdc-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="1dfdc-107">Il prefisso *src* viene eseguito il mapping allo spazio dei nomi in cui l'origine dati *posizioni* è definito.</span><span class="sxs-lookup"><span data-stu-id="1dfdc-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="1dfdc-108">Il prefisso *scm* esegue il mapping a `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` e *dat* esegue il mapping a `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span><span class="sxs-lookup"><span data-stu-id="1dfdc-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="1dfdc-109">L'esempio seguente crea una vista della raccolta di dati ordinata in base al nome della città e raggruppata in base allo stato.</span><span class="sxs-lookup"><span data-stu-id="1dfdc-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="1dfdc-110">La vista può essere quindi un'origine di associazione, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1dfdc-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="1dfdc-111">Per le associazioni ai dati XML definiti in un <xref:System.Windows.Data.XmlDataProvider> risorsa, anteporre al nome XML con un simbolo @.</span><span class="sxs-lookup"><span data-stu-id="1dfdc-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="1dfdc-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dfdc-112">See Also</span></span>  
 <xref:System.Windows.Data.CollectionViewSource>  
 [<span data-ttu-id="1dfdc-113">Ottenere la visualizzazione predefinita di una raccolta dati</span><span class="sxs-lookup"><span data-stu-id="1dfdc-113">Get the Default View of a Data Collection</span></span>](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)  
 [<span data-ttu-id="1dfdc-114">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="1dfdc-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="1dfdc-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="1dfdc-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
