---
title: La conversione implicita da &#39; &lt;NomeTipo1&gt; &#39; per &#39; &lt;in NomeTipo2&gt; &#39; quando il valore di &#39;ByRef&#39; parametro &#39; &lt; ParameterName&gt; &#39; nell'argomento corrispondente.
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: 9f05a5fbcbef828b4ffa920d8cade475cedb64d5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537236"
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a>La conversione implicita da &#39; &lt;NomeTipo1&gt; &#39; per &#39; &lt;in NomeTipo2&gt; &#39; quando il valore di &#39;ByRef&#39; parametro &#39; &lt; ParameterName&gt; &#39; nell'argomento corrispondente.
Una routine viene chiamata con un [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argomento di tipo diverso rispetto a quello del parametro corrispondente.  
  
 Se si passa un argomento `ByRef`, Visual Basic copia a volte il valore dell'argomento in una variabile locale nella routine invece di passare un riferimento. In tal caso, quando la procedura termina, Visual Basic deve quindi copiare il valore della variabile locale nell'argomento nel codice chiamante.  
  
 Se un valore dell'argomento `ByRef` viene copiato nella routine e l'argomento e il parametro sono dello stesso tipo, non è necessaria alcuna conversione. Ma se i tipi sono diversi, Visual Basic deve convertire in entrambe le direzioni. Poiché non è possibile usare `CType` o una delle altre parole chiave di conversione in un argomento di routine o parametro, tale conversione è sempre implicita.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC41999  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se possibile, usare un argomento chiamante dello stesso tipo del parametro di routine, in modo che Visual Basic non è necessario eseguire alcuna conversione.  
  
-   Se è necessario chiamare la routine con un tipo di argomento diverso dal tipo del parametro, ma non è necessario restituire un valore nell'argomento chiamante, definire il parametro in modo che sia [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) invece che `ByRef`.  
  
## <a name="see-also"></a>Vedere anche
- [Routine](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Parametri e argomenti delle routine](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Passaggio di argomenti per valore e per riferimento](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Conversioni implicite ed esplicite](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
