---
title: Istruzione Stop (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 955a3b6a2f7dc1d0e9823ed6d500ab7f7f9fe5b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599135"
---
# <a name="stop-statement-visual-basic"></a>Istruzione Stop (Visual Basic)
Sospende l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Stop  
```  
  
## <a name="remarks"></a>Note  
 È possibile inserire `Stop` istruzioni in un punto qualsiasi nelle procedure per sospendere l'esecuzione. Utilizzo di `Stop` istruzione è simile all'impostazione di un punto di interruzione nel codice.  
  
 Il `Stop` istruzione sospende l'esecuzione, ma a differenza `End`, non chiudere qualsiasi file o deselezionare tutte le variabili, a meno che non viene rilevata in un file eseguibile compilato (.exe).  
  
> [!NOTE]
>  Se il `Stop` viene rilevata l'istruzione nel codice che è in esecuzione all'esterno dell'ambiente di sviluppo integrato (IDE), il debugger viene richiamato. Questo vale indipendentemente dal fatto che il codice è stato compilato in modalità di debug o finale.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `Stop` istruzione per sospendere l'esecuzione per ogni iterazione di `For...Next` ciclo.  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Istruzione End](../../../visual-basic/language-reference/statements/end-statement.md)
