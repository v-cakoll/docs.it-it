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
ms.openlocfilehash: 3c63c5613b40cb2014c77a0a996e3acb2cc304d4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817019"
---
# <a name="rem-statement-visual-basic"></a>Istruzione REM (Visual Basic)
Utilizzato per includere note esplicative nel codice sorgente di un programma.  
  
## <a name="syntax"></a>Sintassi  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Parti  
 `comment`  
 Facoltativo. Il testo di qualsiasi commento da includere. Uno spazio è necessario tra i `REM` parola chiave e `comment`.  
  
## <a name="remarks"></a>Note  
 È possibile inserire un `REM` istruzione da solo su una riga, oppure è possibile inserirlo in una riga che segue un'altra istruzione. Il `REM` istruzione deve essere l'ultima istruzione nella riga. Se il simbolo segue un'altra istruzione, il `REM` devono essere separati da tale istruzione da uno spazio.  
  
 È possibile usare una virgoletta singola (`'`) anziché `REM`. Ciò è vero se il commento segue un'altra istruzione sulla stessa riga o si trova da sola in una riga.  
  
> [!NOTE]
>  Non è possibile continuare una `REM` istruzione mediante una sequenza di continuazione di riga (`_`). Dopo aver iniziato un commento, il compilatore non esamina i caratteri per un significato speciale. Per commenti su più righe, usare un'altra `REM` istruzione o un simbolo di commento (`'`) per ogni riga.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato il `REM` istruzione, che viene usato per includere note esplicative in un programma. Viene inoltre illustrato l'alternativa di uso del carattere di virgoletta singola (`'`) anziché `REM`.  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Commenti nel codice](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
