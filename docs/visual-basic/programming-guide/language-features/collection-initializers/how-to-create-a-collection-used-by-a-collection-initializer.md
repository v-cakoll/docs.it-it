---
title: 'Procedura: creare una raccolta utilizzata da un inizializzatore di raccolta (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 6158b6f02d95260e2955e77d732fae8b8d9d5e04
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654161"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="25d69-102">Procedura: creare una raccolta utilizzata da un inizializzatore di raccolta (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25d69-102">How to: Create a Collection Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="25d69-103">Quando si utilizza un inizializzatore di raccolta per creare una raccolta, il compilatore Visual Basic cerca un `Add` metodo del tipo di raccolta per cui i parametri per il `Add` metodo corrispondono ai tipi dei valori nell'inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="25d69-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="25d69-104">Questo `Add` metodo viene utilizzato per popolare la raccolta con i valori dall'inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="25d69-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25d69-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="25d69-105">Example</span></span>  
 <span data-ttu-id="25d69-106">Nell'esempio seguente un `OrderCollection` raccolta che contiene un pubblico `Add` metodo che è possibile utilizzare un inizializzatore di raccolta per aggiungere oggetti di tipo `Order`.</span><span class="sxs-lookup"><span data-stu-id="25d69-106">The following example shows an `OrderCollection` collection that contains a public `Add` method that a collection initializer can use to add objects of type `Order`.</span></span> <span data-ttu-id="25d69-107">Il `Add` metodo consente di utilizzare la sintassi dell'inizializzatore di raccolta abbreviata.</span><span class="sxs-lookup"><span data-stu-id="25d69-107">The `Add` method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="25d69-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25d69-108">See Also</span></span>  
 [<span data-ttu-id="25d69-109">Inizializzatori di raccolta</span><span class="sxs-lookup"><span data-stu-id="25d69-109">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [<span data-ttu-id="25d69-110">Procedura: Creare un metodo di estensione Add usato da un inizializzatore di raccolta</span><span class="sxs-lookup"><span data-stu-id="25d69-110">How to: Create an Add Extension Method Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
