---
title: 'Procedura: creare un metodo di estensione Add utilizzato da un inizializzatore di raccolta (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d19ac8b03b992eb9b09b5cb45fdcceadad3a822a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="c54bf-102">Procedura: creare un metodo di estensione Add utilizzato da un inizializzatore di raccolta (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c54bf-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>
<span data-ttu-id="c54bf-103">Quando si utilizza un inizializzatore di raccolta per creare una raccolta, il compilatore Visual Basic cerca un `Add` metodo del tipo di raccolta per cui i parametri per il `Add` metodo corrispondono ai tipi dei valori nell'inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="c54bf-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="c54bf-104">Questo `Add` metodo viene utilizzato per popolare la raccolta con i valori dall'inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="c54bf-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="c54bf-105">Se non corrisponde ad alcuna `Add` metodo esiste e non è possibile modificare il codice per la raccolta, è possibile aggiungere un metodo di estensione denominato `Add` che accetta i parametri necessari per l'inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="c54bf-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="c54bf-106">Si tratta in genere è necessario quando si utilizzano gli inizializzatori di raccolta per le raccolte generiche.</span><span class="sxs-lookup"><span data-stu-id="c54bf-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c54bf-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="c54bf-107">Example</span></span>  
 <span data-ttu-id="c54bf-108">Nell'esempio seguente viene illustrato come aggiungere un metodo di estensione per il tipo generico <xref:System.Collections.Generic.List%601> tipo in modo che un inizializzatore di raccolta può essere utilizzato per aggiungere gli oggetti di tipo `Employee`.</span><span class="sxs-lookup"><span data-stu-id="c54bf-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="c54bf-109">Il metodo di estensione consente di utilizzare la sintassi dell'inizializzatore di raccolta abbreviata.</span><span class="sxs-lookup"><span data-stu-id="c54bf-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c54bf-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c54bf-110">See Also</span></span>  
 [<span data-ttu-id="c54bf-111">Inizializzatori di raccolta</span><span class="sxs-lookup"><span data-stu-id="c54bf-111">Collection Initializers</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [<span data-ttu-id="c54bf-112">Procedura: Creare una raccolta usata da un inizializzatore di raccolta</span><span class="sxs-lookup"><span data-stu-id="c54bf-112">How to: Create a Collection Used by a Collection Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
