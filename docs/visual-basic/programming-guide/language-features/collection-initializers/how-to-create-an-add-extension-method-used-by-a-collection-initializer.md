---
title: 'Procedura: Creare un metodo di estensione usata da un inizializzatore di raccolta (Visual Basic) Add'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: a5af41e25b8f82aa173e2df28cc41b313c8d68dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825404"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="b4257-102">Procedura: Creare un metodo di estensione usata da un inizializzatore di raccolta (Visual Basic) Add</span><span class="sxs-lookup"><span data-stu-id="b4257-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="b4257-103">Quando si usa un inizializzatore di insieme per creare una raccolta, il compilatore Visual Basic cerca un' `Add` metodo di raccolta per il quale i parametri per il `Add` metodo corrispondono ai tipi dei valori nell'inizializzatore di insieme.</span><span class="sxs-lookup"><span data-stu-id="b4257-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="b4257-104">Ciò `Add` metodo viene utilizzato per popolare la raccolta con i valori dall'inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="b4257-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="b4257-105">Se non corrisponde ad alcuna `Add` metodo esista e non è possibile modificare il codice per la raccolta, è possibile aggiungere un metodo di estensione denominato `Add` che accetta i parametri necessari per l'inizializzatore di insieme.</span><span class="sxs-lookup"><span data-stu-id="b4257-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="b4257-106">Si tratta in genere quello che devi se si usano gli inizializzatori di raccolta per le raccolte generiche.</span><span class="sxs-lookup"><span data-stu-id="b4257-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4257-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4257-107">Example</span></span>  
 <span data-ttu-id="b4257-108">Nell'esempio seguente viene illustrato come aggiungere un metodo di estensione per il tipo generico <xref:System.Collections.Generic.List%601> digitate in modo che un inizializzatore di raccolta può essere utilizzato per aggiungere gli oggetti di tipo `Employee`.</span><span class="sxs-lookup"><span data-stu-id="b4257-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="b4257-109">Il metodo di estensione consente di usare la sintassi dell'inizializzatore di raccolta abbreviato.</span><span class="sxs-lookup"><span data-stu-id="b4257-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="b4257-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4257-110">See also</span></span>

- [<span data-ttu-id="b4257-111">Inizializzatori di raccolta</span><span class="sxs-lookup"><span data-stu-id="b4257-111">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="b4257-112">Procedura: Creare una raccolta usata da un inizializzatore di raccolta</span><span class="sxs-lookup"><span data-stu-id="b4257-112">How to: Create a Collection Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
