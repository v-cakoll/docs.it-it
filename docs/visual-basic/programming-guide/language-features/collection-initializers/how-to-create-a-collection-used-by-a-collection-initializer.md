---
title: 'Procedura: creare una raccolta utilizzata da un inizializzatore di raccolta'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
ms.openlocfilehash: 5eaf9e828455bf2accda86ab52a1ce645f10b9ee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349055"
---
# <a name="how-to-create-a-collection-used-by-a-collection-initializer-visual-basic"></a>Procedura: creare una raccolta utilizzata da un inizializzatore di raccolta (Visual Basic)
Quando si usa un inizializzatore di raccolta per creare una raccolta, il compilatore Visual Basic cerca un metodo di `Add` del tipo di raccolta per il quale i parametri per il metodo `Add` corrispondono ai tipi dei valori nell'inizializzatore di raccolta. Questo metodo `Add` viene usato per popolare la raccolta con i valori dall'inizializzatore di raccolta.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una raccolta di `OrderCollection` contenente un metodo di `Add` pubblico che può essere utilizzato da un inizializzatore di raccolta per aggiungere oggetti di tipo `Order`. Il `Add` metodo consente di usare la sintassi abbreviata dell'inizializzatore di raccolta.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#4)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo2/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Inizializzatori di raccolta](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Procedura: Creare un metodo di estensione Add usato da un inizializzatore di raccolta](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)
