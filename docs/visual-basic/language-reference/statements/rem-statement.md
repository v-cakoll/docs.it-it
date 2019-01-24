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
ms.openlocfilehash: a3ad63472f6a3f7ae1ec13742185790667c7bcf0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699051"
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
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Commenti nel codice](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
