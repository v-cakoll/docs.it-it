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
ms.openlocfilehash: 80d6734945324f3f517b256051486273f6b687ec
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827991"
---
# <a name="stop-statement-visual-basic"></a>Istruzione Stop (Visual Basic)
Sospende l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Stop  
```  
  
## <a name="remarks"></a>Note  
 È possibile inserire `Stop` istruzioni in un punto qualsiasi nelle procedure per sospendere l'esecuzione. Uso di `Stop` istruzione è simile all'impostazione di un punto di interruzione nel codice.  
  
 Il `Stop` istruzione sospende l'esecuzione, ma a differenza `End`, non chiudere qualsiasi file o cancellare le variabili di qualsiasi tipo, a meno che non si è verificato in un file eseguibile compilato (.exe).  
  
> [!NOTE]
>  Se il `Stop` viene rilevata l'istruzione nel codice che è in esecuzione all'esterno dell'ambiente di sviluppo integrato (IDE), il debugger viene richiamato. Questo vale indipendentemente dal fatto che il codice è stato compilato in modalità di debug o di vendita al dettaglio.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `Stop` istruzione per sospendere l'esecuzione per ogni iterazione attraverso la `For...Next` ciclo.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione End](../../../visual-basic/language-reference/statements/end-statement.md)
