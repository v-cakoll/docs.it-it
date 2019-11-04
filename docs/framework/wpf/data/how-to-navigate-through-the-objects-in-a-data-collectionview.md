---
title: 'Procedura: navigare tra gli oggetti nella visualizzazione di una raccolta dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: 5ca386db89dcaa66d364d2ed7169c67393cebead
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459711"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a><span data-ttu-id="9b6fb-102">Procedura: navigare tra gli oggetti nella visualizzazione di una raccolta dati</span><span class="sxs-lookup"><span data-stu-id="9b6fb-102">How to: Navigate Through the Objects in a Data CollectionView</span></span>
<span data-ttu-id="9b6fb-103">Le visualizzazioni consentono di visualizzare la stessa raccolta dati in modi diversi, a seconda dell'ordinamento, del filtro o del raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="9b6fb-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping.</span></span> <span data-ttu-id="9b6fb-104">Le visualizzazioni forniscono anche un concetto di puntatore di record corrente e consentono di trasferire il puntatore.</span><span class="sxs-lookup"><span data-stu-id="9b6fb-104">Views also provide a current record pointer concept and enable moving the pointer.</span></span> <span data-ttu-id="9b6fb-105">Questo esempio Mostra come ottenere l'oggetto corrente e spostarsi tra gli oggetti in una raccolta di dati usando la funzionalità fornita nella classe <xref:System.Windows.Data.CollectionView>.</span><span class="sxs-lookup"><span data-stu-id="9b6fb-105">This example shows how to get the current object as well as navigate through the objects in a data collection using the functionality provided in the <xref:System.Windows.Data.CollectionView> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b6fb-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b6fb-106">Example</span></span>  
 <span data-ttu-id="9b6fb-107">In questo esempio `myCollectionView` è un oggetto <xref:System.Windows.Data.CollectionView> che rappresenta una vista su una raccolta associata.</span><span class="sxs-lookup"><span data-stu-id="9b6fb-107">In this example, `myCollectionView` is a <xref:System.Windows.Data.CollectionView> object that is a view over a bound collection.</span></span>  
  
 <span data-ttu-id="9b6fb-108">Nell'esempio seguente `OnButton` è un gestore eventi per i pulsanti `Previous` e `Next` in un'applicazione, che sono pulsanti che consentono all'utente di spostarsi nella raccolta dei dati.</span><span class="sxs-lookup"><span data-stu-id="9b6fb-108">In the following example, `OnButton` is an event handler for the `Previous` and `Next` buttons in an application, which are buttons that allow the user to navigate the data collection.</span></span> <span data-ttu-id="9b6fb-109">Si noti che le proprietà <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> e <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> indicano se il puntatore di record corrente è arrivato rispettivamente all'inizio e alla fine dell'elenco, in modo che <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> e <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> possano essere chiamati in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="9b6fb-109">Note that the <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> and <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> properties report whether the current record pointer has come to the beginning and the end of the list respectively so that <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> and <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> can be called as appropriately.</span></span>  
  
 <span data-ttu-id="9b6fb-110">Viene eseguito il cast della proprietà <xref:System.Windows.Data.CollectionView.CurrentItem%2A> della visualizzazione come `Order` per restituire l'elemento dell'ordine corrente nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="9b6fb-110">The <xref:System.Windows.Data.CollectionView.CurrentItem%2A> property of the view is cast as an `Order` to return the current order item in the collection.</span></span>  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a><span data-ttu-id="9b6fb-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b6fb-111">See also</span></span>

- [<span data-ttu-id="9b6fb-112">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="9b6fb-112">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="9b6fb-113">Ordinare i dati in una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="9b6fb-113">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="9b6fb-114">Filtrare i dati di una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="9b6fb-114">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="9b6fb-115">Ordinare e raggruppare dati con una visualizzazione in XAML</span><span class="sxs-lookup"><span data-stu-id="9b6fb-115">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="9b6fb-116">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="9b6fb-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
