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
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Procedura: creare un metodo di estensione Add utilizzato da un inizializzatore di raccolta (Visual Basic)
Quando si usa un inizializzatore di raccolta per creare una raccolta, il compilatore Visual Basic cerca un `Add` metodo del tipo di raccolta per il quale i parametri per il `Add` Metodo corrispondono ai tipi dei valori nell'inizializzatore di raccolta. Questo `Add` metodo viene utilizzato per popolare la raccolta con i valori dell'inizializzatore di raccolta.  
  
 Se non `Add` esiste alcun metodo corrispondente e non è possibile modificare il codice per la raccolta, è possibile aggiungere un metodo `Add` di estensione denominato che accetta i parametri richiesti dall'inizializzatore di raccolta. Questa operazione è in genere necessaria quando si usano gli inizializzatori di insieme per le raccolte generiche.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come aggiungere un metodo di estensione al tipo generico in <xref:System.Collections.Generic.List%601> modo che sia possibile utilizzare un inizializzatore di raccolta per aggiungere oggetti di tipo `Employee` . Il metodo di estensione consente di usare la sintassi abbreviata dell'inizializzatore di raccolta.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Inizializzatori di insieme](index.md)
- [Procedura: Creare una raccolta usata da un inizializzatore di raccolta](how-to-create-a-collection-used-by-a-collection-initializer.md)
