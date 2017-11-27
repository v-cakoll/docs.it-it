---
title: Passaggio di argomenti in base alla posizione e al nome (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 164f69fcf23049441a0acbe05058c792d5363a03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>Passaggio di argomenti in base alla posizione e al nome (Visual Basic)
Quando si chiama un `Sub` o `Function` procedura, è possibile passare argomenti *in base alla posizione* , ovvero nell'ordine in cui appaiono nella definizione della stored procedure, oppure è possibile passare loro *in base al nome*, senza tener conto della posizione.  
  
 Quando si passa un argomento in base al nome, specificare il dichiarato dell'argomento nome seguito da due punti e un segno di uguale (`:=`), seguito dal valore dell'argomento. È possibile fornire argomenti denominati in qualsiasi ordine.  
  
 Ad esempio, `Sub` procedura accetta tre argomenti:  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 Quando si chiama questa procedura, è possibile fornire gli argomenti in base alla posizione, in base al nome o utilizzando una combinazione di entrambi.  
  
## <a name="passing-arguments-by-position"></a>Passaggio di argomenti in base alla posizione  
 È possibile chiamare la routine `studentInfo` con i relativi argomenti passati per posizione e delimitato da virgole, come illustrato nell'esempio seguente:  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 Se si omette un argomento facoltativo in un elenco di argomenti posizionali, deve contenere al suo posto, con una virgola. L'esempio seguente chiama `studentInfo` senza il `age` argomento:  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## <a name="passing-arguments-by-name"></a>Passaggio di argomenti in base al nome  
 In alternativa, è possibile chiamare `studentInfo` con gli argomenti passati in base al nome, delimitati da virgole, come illustrato nell'esempio seguente:  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>Combinazione di argomenti in base alla posizione e al nome  
 È possibile fornire entrambi gli argomenti in base alla posizione e con nome in un'unica chiamata di routine, come illustrato nell'esempio seguente:  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 Nell'esempio precedente, non è necessario indicare la posizione dell'omessi alcuna virgola aggiuntiva `age` argomento, poiché `birth` viene passato in base al nome.  
  
 Quando si specificano argomenti da una combinazione di posizione e nome, gli argomenti posizionali devono provenire prima. Una volta che viene fornito un argomento in base al nome, tutti i restanti argomenti devono essere in base al nome.  
  
## <a name="supplying-optional-arguments-by-name"></a>Passaggio di argomenti facoltativi per nome  
 Passaggio di argomenti in base al nome è particolarmente utile quando si chiama una routine con più di un argomento facoltativo. Se vengono forniti gli argomenti in base al nome, non è necessario utilizzare virgole per indicare gli argomenti posizionali mancante. Passaggio di argomenti in base al nome rende anche più facile tenere traccia degli argomenti passati e quelle che sono omessi.  
  
## <a name="restrictions-on-supplying-arguments-by-name"></a>Restrizioni al passaggio di argomenti in base al nome  
 È possibile passare argomenti in base al nome per evitare di immettere gli argomenti obbligatori. È possibile omettere solo gli argomenti facoltativi.  
  
 È possibile passare una matrice di parametri in base al nome. Infatti, quando si chiama la routine, si fornisce un numero indefinito di argomenti delimitato da virgole per la matrice di parametri e il compilatore non è possibile associare più di un argomento con un solo nome.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)  
 [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)  
 [Parametri facoltativi](./optional-parameters.md)  
 [Matrici di parametri](./parameter-arrays.md)  
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
