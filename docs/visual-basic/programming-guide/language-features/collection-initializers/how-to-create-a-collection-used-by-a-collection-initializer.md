---
title: 'Procedura: Creare una raccolta usata da un inizializzatore di raccolta (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 75c280b57df03bde173c740123cccda278536dc1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053626"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Procedura: Creare una raccolta usata da un inizializzatore di raccolta (Visual Basic)
Quando si usa un inizializzatore di insieme per creare una raccolta, il compilatore Visual Basic cerca un' `Add` metodo di raccolta per il quale i parametri per il `Add` metodo corrispondono ai tipi dei valori nell'inizializzatore di insieme. Ciò `Add` metodo viene utilizzato per popolare la raccolta con i valori dall'inizializzatore di raccolta.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un' `OrderCollection` raccolta che contiene un pubblico `Add` metodo che è possibile usare un inizializzatore di raccolta per aggiungere gli oggetti di tipo `Order`. Il `Add` metodo consente di utilizzare la sintassi dell'inizializzatore di raccolta abbreviato.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Inizializzatori di raccolta](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Procedura: Creare un metodo di estensione usata da un inizializzatore di raccolta Add](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
