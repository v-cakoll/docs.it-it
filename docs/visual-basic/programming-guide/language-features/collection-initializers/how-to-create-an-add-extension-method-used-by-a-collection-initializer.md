---
title: 'Procedura: Creare un metodo di estensione usata da un inizializzatore di raccolta (Visual Basic) Add'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 3a1db8ede8162b329d546c0e712ef1c2df7d7883
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661672"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Procedura: Creare un metodo di estensione usata da un inizializzatore di raccolta (Visual Basic) Add
Quando si usa un inizializzatore di insieme per creare una raccolta, il compilatore Visual Basic cerca un' `Add` metodo di raccolta per il quale i parametri per il `Add` metodo corrispondono ai tipi dei valori nell'inizializzatore di insieme. Ciò `Add` metodo viene utilizzato per popolare la raccolta con i valori dall'inizializzatore di raccolta.  
  
 Se non corrisponde ad alcuna `Add` metodo esista e non è possibile modificare il codice per la raccolta, è possibile aggiungere un metodo di estensione denominato `Add` che accetta i parametri necessari per l'inizializzatore di insieme. Si tratta in genere quello che devi se si usano gli inizializzatori di raccolta per le raccolte generiche.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come aggiungere un metodo di estensione per il tipo generico <xref:System.Collections.Generic.List%601> digitate in modo che un inizializzatore di raccolta può essere utilizzato per aggiungere gli oggetti di tipo `Employee`. Il metodo di estensione consente di usare la sintassi dell'inizializzatore di raccolta abbreviato.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Inizializzatori di raccolta](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Procedura: Creare una raccolta usata da un inizializzatore di raccolta](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
