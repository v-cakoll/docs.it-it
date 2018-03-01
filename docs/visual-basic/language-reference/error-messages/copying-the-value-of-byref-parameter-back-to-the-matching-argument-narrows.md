---
title: Copia il valore di &#39; ByRef &#39; parametro &#39; &lt;parametername&gt;&#39; back per la corrispondenza consente di restringere argomento di tipo &#39;&lt; NomeTipo1&gt;&#39; nel tipo &#39;&lt; NomeTipo2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4bf993639007162e2e17d4b8cb9dfe8d5316acaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a>Copia il valore di &#39; ByRef &#39; parametro &#39; &lt;parametername&gt;&#39; back per la corrispondenza consente di restringere argomento di tipo &#39;&lt; NomeTipo1&gt;&#39; nel tipo &#39;&lt; NomeTipo2&gt;&#39;
Una routine viene chiamata con un argomento che viene ampliato al tipo di parametro corrispondente e la conversione dal parametro per l'argomento è di restrizione.  
  
 Quando si definisce una classe o una struttura, è possibile definire uno o più operatori di conversione per convertire il tipo della classe o della struttura in altri tipi. È anche possibile definire operatori di conversione inversi per riconvertire gli altri tipi nel tipo della classe o della struttura originale. Quando il tipo della classe o della struttura viene usato in una chiamata di routine, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] può usare questi operatori di conversione per convertire il tipo di un argomento nel tipo del parametro corrispondente.  
  
 Se si passa l'argomento [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] copia a volte il valore dell'argomento in una variabile locale nella routine invece di passare un riferimento. In un caso simile, alla restituzione della routine [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] deve quindi ricopiare il valore della variabile locale nell'argomento nel codice chiamante.  
  
 Se un valore dell'argomento `ByRef` viene copiato nella routine e l'argomento e il parametro sono dello stesso tipo, non è necessaria alcuna conversione. Se invece i tipi sono diversi, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] deve eseguire la conversione in entrambe le direzioni. Se uno dei tipi è il tipo della classe o della struttura, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] deve convertirlo nell'altro tipo e dall'altro tipo. Se una di queste conversioni è ampliamento, potrebbe limitare la conversione inversa.  
  
 **ID errore:** BC32053  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se possibile, usare un argomento chiamante dello stesso tipo del parametro della routine, in modo che [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] non debba eseguire alcuna conversione.  
  
-   Se è necessario chiamare la routine con un argomento di tipo diverso dal tipo di parametro ma non è necessario restituire un valore nell'argomento chiamante, definire il parametro come [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anziché `ByRef`.  
  
-   Se è necessario restituire un valore nell'argomento chiamante, definire l'operatore di conversione inversi come [Widening](../../../visual-basic/language-reference/modifiers/widening.md), se possibile.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Parametri e argomenti delle routine](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [Passaggio di argomenti per valore e per riferimento](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [Routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Procedura: Definire un operatore di conversione](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Conversioni di tipi in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
