---
title: 'Procedura: navigare tra gli oggetti nella visualizzazione di una raccolta dati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 215e3583d50567a2bfec8226e006bc7398628299
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="250ab-102">Procedura: navigare tra gli oggetti nella visualizzazione di una raccolta dati</span><span class="sxs-lookup"><span data-stu-id="250ab-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="250ab-103">Le viste consentono la stessa raccolta di dati da visualizzare in modi diversi, a seconda di ordinamento, filtro o di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="250ab-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="250ab-104">Viste inoltre forniscono un concetto di puntatore del record corrente e consentono di spostare il puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="250ab-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="250ab-105">In questo esempio viene illustrato come ottenere l'oggetto corrente, nonché di spostarsi tra gli oggetti in una raccolta di dati tramite la funzionalità fornita nel <xref:System.Windows.Data.CollectionView> classe.</span><span class="sxs-lookup"><span data-stu-id="250ab-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="250ab-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="250ab-106">Example</span></span>  
 <span data-ttu-id="250ab-107">In questo esempio, `myCollectionView` è un <xref:System.Windows.Data.CollectionView> oggetto che rappresenta una visualizzazione di una raccolta associata.</span><span class="sxs-lookup"><span data-stu-id="250ab-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="250ab-108">Nell'esempio seguente, `OnButton` è un gestore eventi per il `Previous` e `Next` pulsanti in un'applicazione, che sono disponibili pulsanti che consentono all'utente di esplorare la raccolta di dati.</span><span class="sxs-lookup"><span data-stu-id="250ab-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="250ab-109">Si noti che il <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> e <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> le proprietà del report se il puntatore del record corrente si trova all'inizio e fine dell'elenco rispettivamente in modo che <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> e <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> può essere chiamato come appropriato.</span><span class="sxs-lookup"><span data-stu-id="250ab-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="250ab-110">Il <xref:System.Windows.Data.CollectionView.CurrentItem%2A> proprietà della vista viene eseguito il cast come un `Order` per restituire l'elemento ordine corrente nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="250ab-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="250ab-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="250ab-111">See Also</span></span>  
 [<span data-ttu-id="250ab-112">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="250ab-112">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="250ab-113">Ordinare i dati in una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="250ab-113">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [<span data-ttu-id="250ab-114">Filtrare i dati di una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="250ab-114">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="250ab-115">Ordinare e raggruppare dati con una visualizzazione in XAML</span><span class="sxs-lookup"><span data-stu-id="250ab-115">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [<span data-ttu-id="250ab-116">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="250ab-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
