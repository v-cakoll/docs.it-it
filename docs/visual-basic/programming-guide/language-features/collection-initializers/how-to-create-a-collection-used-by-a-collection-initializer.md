---
title: 'Procedura: creare una raccolta utilizzata da un inizializzatore di raccolta'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 7cba290b92f41125a93d1ed022e4db5ef62da789
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414556"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Procedura: creare una raccolta utilizzata da un inizializzatore di raccolta (Visual Basic)
Quando si usa un inizializzatore di raccolta per creare una raccolta, il compilatore Visual Basic cerca un `Add` metodo del tipo di raccolta per il quale i parametri per il `Add` Metodo corrispondono ai tipi dei valori nell'inizializzatore di raccolta. Questo `Add` metodo viene utilizzato per popolare la raccolta con i valori dell'inizializzatore di raccolta.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una `OrderCollection` raccolta che contiene un `Add` Metodo pubblico che può essere utilizzato da un inizializzatore di raccolta per aggiungere oggetti di tipo `Order` . Il `Add` metodo consente di usare la sintassi abbreviata dell'inizializzatore di raccolta.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Inizializzatori di insieme](index.md)
- [Procedura: creare un metodo di estensione Add utilizzato da un inizializzatore di raccolta](how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
