---
title: Conversione implicita da '<typename1>' a '<typename2>' quando il valore del parametro 'ByRef' '<parametername>' viene ricopiato nell'argomento corrispondente
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: 7b02659d96b08c592b25ddf3ef1f99114c3ee269
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831761"
---
# <a name="implicit-conversion-from-typename1-to-typename2-in-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument"></a>La conversione implicita da '\<NomeTipo1 >' a '\<in NomeTipo2 >' quando il valore del parametro 'ByRef' '\<nomeparametro >' nell'argomento corrispondente.
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
