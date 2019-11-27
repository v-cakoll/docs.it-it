---
title: 'Procedura: creare un metodo di estensione Add utilizzato da un inizializzatore di raccolta'
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: 6d5f9d38b413b79f111a14ec3829c57a9797ce54
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346718"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Procedura: creare un metodo di estensione Add utilizzato da un inizializzatore di raccolta (Visual Basic)
Quando si usa un inizializzatore di raccolta per creare una raccolta, il compilatore Visual Basic cerca un metodo di `Add` del tipo di raccolta per il quale i parametri per il metodo `Add` corrispondono ai tipi dei valori nell'inizializzatore di raccolta. Questo metodo `Add` viene usato per popolare la raccolta con i valori dall'inizializzatore di raccolta.  
  
 Se non esiste alcun metodo di `Add` corrispondente e non è possibile modificare il codice per la raccolta, è possibile aggiungere un metodo di estensione denominato `Add` che accetta i parametri richiesti dall'inizializzatore di raccolta. Questa operazione è in genere necessaria quando si usano gli inizializzatori di insieme per le raccolte generiche.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come aggiungere un metodo di estensione al tipo di <xref:System.Collections.Generic.List%601> generico in modo che sia possibile utilizzare un inizializzatore di raccolta per aggiungere oggetti di tipo `Employee`. Il metodo di estensione consente di usare la sintassi abbreviata dell'inizializzatore di raccolta.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Inizializzatori di raccolta](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Procedura: Creare una raccolta usata da un inizializzatore di raccolta](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
