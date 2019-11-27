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
ms.openlocfilehash: bdde4beae242c3175b02cd2af252babb850416f6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346734"
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
 Facoltativa. Testo di qualsiasi commento che si desidera includere. Tra la parola chiave `REM` e la `comment`è necessario uno spazio.  
  
## <a name="remarks"></a>Note  
 È possibile inserire un'istruzione `REM` da solo su una riga oppure è possibile inserirla in una riga che segue un'altra istruzione. L'istruzione `REM` deve essere l'ultima istruzione della riga. Se segue un'altra istruzione, il `REM` deve essere separato da tale istruzione da uno spazio.  
  
 Anziché `REM`, è possibile utilizzare una virgoletta singola (`'`). Questo vale se il commento segue un'altra istruzione sulla stessa riga o si trova da solo su una riga.  
  
> [!NOTE]
> Non è possibile continuare un'istruzione `REM` usando una sequenza di continuazione di riga (`_`). Una volta che viene avviato un commento, il compilatore non esamina i caratteri per un significato speciale. Per un commento su più righe, usare un'altra istruzione `REM` o un simbolo di commento (`'`) per ogni riga.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata l'istruzione `REM`, che viene utilizzata per includere osservazioni esplicative in un programma. Viene inoltre illustrata l'alternativa di utilizzare il carattere virgoletta singola (`'`) anziché `REM`.  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vedere anche

- [Commenti nel codice](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Procedura: Interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
