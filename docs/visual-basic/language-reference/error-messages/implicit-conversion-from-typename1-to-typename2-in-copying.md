---
title: Conversione implicita da '<typename1>' a '<typename2>' quando il valore del parametro 'ByRef' '<parametername>' viene ricopiato nell'argomento corrispondente
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: 4d0f9aac795f683cf58210ea38b3783e451ccfc3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402862"
---
# <a name="implicit-conversion-from-typename1-to-typename2-in-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument"></a>Conversione implicita da '\<typename1>' a '\<typename2>' quando il valore del parametro 'ByRef' '\<parametername>' viene ricopiato nell'argomento corrispondente
Una routine viene chiamata con un argomento [ByRef](../modifiers/byref.md) di un tipo diverso rispetto a quello del parametro corrispondente.  
  
 Se si passa un argomento `ByRef` , Visual Basic talvolta copia il valore dell'argomento in una variabile locale nella procedura anziché passare un riferimento. In tal caso, quando la procedura viene restituita, Visual Basic necessario copiare nuovamente il valore della variabile locale nell'argomento nel codice chiamante.  
  
 Se un valore dell'argomento `ByRef` viene copiato nella routine e l'argomento e il parametro sono dello stesso tipo, non è necessaria alcuna conversione. Tuttavia, se i tipi sono diversi, Visual Basic necessario eseguire la conversione in entrambe le direzioni. Poiché non è possibile usare `CType` o una delle altre parole chiave di conversione in un argomento o parametro di routine, tale conversione è sempre implicita.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC41999  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se possibile, usare un argomento chiamante dello stesso tipo del parametro della routine, in modo che Visual Basic non debba eseguire alcuna conversione.  
  
- Se è necessario chiamare la routine con un tipo di argomento diverso dal tipo del parametro, ma non è necessario restituire un valore nell'argomento chiamante, definire il parametro in modo che sia [ByVal](../modifiers/byval.md) invece che `ByRef`.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](../../programming-guide/language-features/procedures/index.md)
- [Parametri e argomenti delle routine](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Passaggio di argomenti per valore e per riferimento](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Conversioni implicite ed esplicite](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
