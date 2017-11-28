---
title: 'Procedura: creare un metodo di estensione Add utilizzato da un inizializzatore di raccolta (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d19ac8b03b992eb9b09b5cb45fdcceadad3a822a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a>Procedura: creare un metodo di estensione Add utilizzato da un inizializzatore di raccolta (Visual Basic)
Quando si utilizza un inizializzatore di raccolta per creare una raccolta, il compilatore Visual Basic cerca un `Add` metodo del tipo di raccolta per cui i parametri per il `Add` metodo corrispondono ai tipi dei valori nell'inizializzatore di raccolta. Questo `Add` metodo viene utilizzato per popolare la raccolta con i valori dall'inizializzatore di raccolta.  
  
 Se non corrisponde ad alcuna `Add` metodo esiste e non è possibile modificare il codice per la raccolta, è possibile aggiungere un metodo di estensione denominato `Add` che accetta i parametri necessari per l'inizializzatore di raccolta. Si tratta in genere è necessario quando si utilizzano gli inizializzatori di raccolta per le raccolte generiche.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come aggiungere un metodo di estensione per il tipo generico <xref:System.Collections.Generic.List%601> tipo in modo che un inizializzatore di raccolta può essere utilizzato per aggiungere gli oggetti di tipo `Employee`. Il metodo di estensione consente di utilizzare la sintassi dell'inizializzatore di raccolta abbreviata.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-an-add-extension-method-used-by-a-collection-initializer_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Inizializzatori di raccolta](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [Procedura: Creare una raccolta usata da un inizializzatore di raccolta](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)
