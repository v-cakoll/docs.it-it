---
title: Istruzione REM (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: 16149ce42e3476cf07a62298f83734fee9ec7253
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957764"
---
# <a name="rem-statement-visual-basic"></a>Istruzione REM (Visual Basic)
Utilizzato per includere osservazioni esplicative nel codice sorgente di un programma.  
  
## <a name="syntax"></a>Sintassi  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Parti  
 `comment`  
 facoltativo. Testo di qualsiasi commento che si desidera includere. È necessario uno spazio tra la `REM` parola chiave `comment`e.  
  
## <a name="remarks"></a>Note  
 È possibile inserire un' `REM` istruzione da solo su una riga oppure è possibile inserirla in una riga che segue un'altra istruzione. L' `REM` istruzione deve essere l'ultima istruzione della riga. Se segue un'altra istruzione, l' `REM` oggetto deve essere separato dall'istruzione da uno spazio.  
  
 È possibile utilizzare le`'` `REM`virgolette singole () anziché. Questo vale se il commento segue un'altra istruzione sulla stessa riga o si trova da solo su una riga.  
  
> [!NOTE]
> Non è possibile continuare `REM` un'istruzione utilizzando una sequenza di continuazione di`_`riga (). Una volta che viene avviato un commento, il compilatore non esamina i caratteri per un significato speciale. Per un commento su più righe, usare un' `REM` altra istruzione o un simbolo di`'`commento () in ogni riga.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata `REM` l'istruzione, che viene utilizzata per includere osservazioni esplicative in un programma. Viene inoltre illustrata l'alternativa di utilizzare il carattere virgoletta singola (`'`) `REM`anziché.  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Commenti nel codice](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
