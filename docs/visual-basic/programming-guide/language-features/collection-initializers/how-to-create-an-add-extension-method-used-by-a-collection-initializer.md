---
title: 'Procedura: creare un metodo di estensione Add utilizzato da un inizializzatore di raccolta'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 4dbe6146b70181864a6717146071f9b93a1f583e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414569"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="a257c-102">Procedura: creare un metodo di estensione Add utilizzato da un inizializzatore di raccolta (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a257c-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="a257c-103">Quando si usa un inizializzatore di raccolta per creare una raccolta, il compilatore Visual Basic cerca un `Add` metodo del tipo di raccolta per il quale i parametri per il `Add` Metodo corrispondono ai tipi dei valori nell'inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="a257c-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="a257c-104">Questo `Add` metodo viene utilizzato per popolare la raccolta con i valori dell'inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="a257c-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="a257c-105">Se non `Add` esiste alcun metodo corrispondente e non è possibile modificare il codice per la raccolta, è possibile aggiungere un metodo `Add` di estensione denominato che accetta i parametri richiesti dall'inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="a257c-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="a257c-106">Questa operazione è in genere necessaria quando si usano gli inizializzatori di insieme per le raccolte generiche.</span><span class="sxs-lookup"><span data-stu-id="a257c-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a257c-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="a257c-107">Example</span></span>  
 <span data-ttu-id="a257c-108">Nell'esempio seguente viene illustrato come aggiungere un metodo di estensione al tipo generico in <xref:System.Collections.Generic.List%601> modo che sia possibile utilizzare un inizializzatore di raccolta per aggiungere oggetti di tipo `Employee` .</span><span class="sxs-lookup"><span data-stu-id="a257c-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="a257c-109">Il metodo di estensione consente di usare la sintassi abbreviata dell'inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="a257c-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a257c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a257c-110">See also</span></span>

- [<span data-ttu-id="a257c-111">Inizializzatori di insieme</span><span class="sxs-lookup"><span data-stu-id="a257c-111">Collection Initializers</span></span>](index.md)
- [<span data-ttu-id="a257c-112">Procedura: Creare una raccolta usata da un inizializzatore di raccolta</span><span class="sxs-lookup"><span data-stu-id="a257c-112">How to: Create a Collection Used by a Collection Initializer</span></span>](how-to-create-a-collection-used-by-a-collection-initializer.md)
