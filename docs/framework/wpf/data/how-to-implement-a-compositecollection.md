---
title: 'Procedura: Implementare un oggetto CompositeCollection'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: 71d55a23711b116a91386a537d5572e8506d4c6b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372672"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="39b09-102">Procedura: Implementare un oggetto CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="39b09-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="39b09-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="39b09-103">Example</span></span>  
 <span data-ttu-id="39b09-104">Nell'esempio seguente viene illustrato come visualizzare più connessioni ed elementi come un elenco utilizzando il <xref:System.Windows.Data.CompositeCollection> classe.</span><span class="sxs-lookup"><span data-stu-id="39b09-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="39b09-105">In questo esempio `GreekGods` è un <xref:System.Collections.ObjectModel.ObservableCollection%601> di `GreekGod` oggetti personalizzati.</span><span class="sxs-lookup"><span data-stu-id="39b09-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="39b09-106">I modelli di dati sono definiti in modo che `GreekGod` gli oggetti e `GreekHero` oggetti vengano visualizzati rispettivamente con un gold e un colore ciano in primo piano.</span><span class="sxs-lookup"><span data-stu-id="39b09-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="39b09-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39b09-107">See also</span></span>
- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="39b09-108">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="39b09-108">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="39b09-109">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="39b09-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
