---
title: Istruzione REM
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
ms.openlocfilehash: 68c898145bd8845c657b6ebb8776a3a9027c359c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404265"
---
# <a name="rem-statement-visual-basic"></a>Istruzione REM (Visual Basic)
Utilizzato per includere osservazioni esplicative nel codice sorgente di un programma.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Parti  
 `comment`  
 Facoltativa. Testo di qualsiasi commento che si desidera includere. È necessario uno spazio tra la `REM` parola chiave e `comment` .  
  
## <a name="remarks"></a>Commenti  
 È possibile inserire un' `REM` istruzione da solo su una riga oppure è possibile inserirla in una riga che segue un'altra istruzione. L' `REM` istruzione deve essere l'ultima istruzione della riga. Se segue un'altra istruzione, l'oggetto `REM` deve essere separato dall'istruzione da uno spazio.  
  
 È possibile utilizzare le virgolette singole ( `'` ) anziché `REM` . Questo vale se il commento segue un'altra istruzione sulla stessa riga o si trova da solo su una riga.  
  
> [!NOTE]
> Non è possibile continuare un' `REM` istruzione utilizzando una sequenza di continuazione di riga ( `_` ). Una volta che viene avviato un commento, il compilatore non esamina i caratteri per un significato speciale. Per un commento su più righe, usare un'altra `REM` istruzione o un simbolo di commento ( `'` ) in ogni riga.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata l' `REM` istruzione, che viene utilizzata per includere osservazioni esplicative in un programma. Viene inoltre illustrata l'alternativa di utilizzare il carattere virgoletta singola ( `'` ) anziché `REM` .  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Commenti nel codice](../../programming-guide/program-structure/comments-in-code.md)
- [Procedura: Interrompere e combinare istruzioni nel codice](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
