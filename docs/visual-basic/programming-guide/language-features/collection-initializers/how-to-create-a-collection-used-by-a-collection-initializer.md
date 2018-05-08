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
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Procedura: creare una raccolta utilizzata da un inizializzatore di raccolta (Visual Basic)
Quando si utilizza un inizializzatore di raccolta per creare una raccolta, il compilatore Visual Basic cerca un `Add` metodo del tipo di raccolta per cui i parametri per il `Add` metodo corrispondono ai tipi dei valori nell'inizializzatore di raccolta. Questo `Add` metodo viene utilizzato per popolare la raccolta con i valori dall'inizializzatore di raccolta.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente un `OrderCollection` raccolta che contiene un pubblico `Add` metodo che è possibile utilizzare un inizializzatore di raccolta per aggiungere oggetti di tipo `Order`. Il `Add` metodo consente di utilizzare la sintassi dell'inizializzatore di raccolta abbreviata.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Inizializzatori di raccolta](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [Procedura: Creare un metodo di estensione Add usato da un inizializzatore di raccolta](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
