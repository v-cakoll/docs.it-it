---
title: 'Procedura: Creare una raccolta usata da un inizializzatore di raccolta (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: aaa367e5a1739f26e9b0458d8f2fc44462b73b7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631724"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Procedura: Creare una raccolta usata da un inizializzatore di raccolta (Visual Basic)
Quando si usa un inizializzatore di insieme per creare una raccolta, il compilatore Visual Basic cerca un' `Add` metodo di raccolta per il quale i parametri per il `Add` metodo corrispondono ai tipi dei valori nell'inizializzatore di insieme. Ciò `Add` metodo viene utilizzato per popolare la raccolta con i valori dall'inizializzatore di raccolta.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un' `OrderCollection` raccolta che contiene un pubblico `Add` metodo che è possibile usare un inizializzatore di raccolta per aggiungere gli oggetti di tipo `Order`. Il `Add` metodo consente di utilizzare la sintassi dell'inizializzatore di raccolta abbreviato.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Inizializzatori di raccolta](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Procedura: Creare un metodo di estensione usata da un inizializzatore di raccolta Add](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
