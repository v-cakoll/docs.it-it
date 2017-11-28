---
title: Conversione implicita da &#39; &lt;NomeTipo1&gt;&#39; a &#39;&lt; NomeTipo2&gt;&#39; copiare il valore di &#39; ByRef &#39; parametro &#39; &lt;parametername&gt;&#39; back nell'argomento corrispondente.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords: BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e858b475a816a35d18822643de5a273abe28562
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a>Conversione implicita da &#39; &lt;NomeTipo1&gt;&#39; a &#39;&lt; NomeTipo2&gt;&#39; copiare il valore di &#39; ByRef &#39; parametro &#39; &lt;parametername&gt;&#39; back nell'argomento corrispondente.
Una routine viene chiamata con un [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argomento di tipo diverso rispetto a quello del parametro corrispondente.  
  
 Se si passa un argomento `ByRef`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] copia a volte il valore dell'argomento in una variabile locale nella routine invece di passare un riferimento. In un caso simile, alla restituzione della routine [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] deve quindi ricopiare il valore della variabile locale nell'argomento nel codice chiamante.  
  
 Se un valore dell'argomento `ByRef` viene copiato nella routine e l'argomento e il parametro sono dello stesso tipo, non è necessaria alcuna conversione. Se invece i tipi sono diversi, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] deve eseguire la conversione in entrambe le direzioni. Poiché non è possibile utilizzare `CType` o una delle altre parole chiave di conversione su un argomento di routine o parametro, tale conversione è sempre implicita.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC41999  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se possibile, usare un argomento chiamante dello stesso tipo del parametro della routine, in modo che [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] non debba eseguire alcuna conversione.  
  
-   Se è necessario chiamare la routine con un argomento di tipo diverso dal tipo di parametro ma non è necessario restituire un valore nell'argomento chiamante, definire il parametro come [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anziché `ByRef`.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Parametri e argomenti delle routine](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [Passaggio di argomenti per valore e per riferimento](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
