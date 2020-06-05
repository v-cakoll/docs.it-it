---
title: Istruzione Stop
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
ms.openlocfilehash: 2ef1e2f9045e5509e11557c9fdaf3edd2786b72c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404226"
---
# <a name="stop-statement-visual-basic"></a>Istruzione Stop (Visual Basic)
Sospende l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a>Osservazioni  
 È possibile inserire `Stop` istruzioni in qualsiasi punto delle procedure per sospendere l'esecuzione. L'utilizzo dell' `Stop` istruzione è simile all'impostazione di un punto di interruzione nel codice.  
  
 L' `Stop` istruzione sospende l'esecuzione, ma, a differenza di `End` , non chiude alcun file né cancella alcuna variabile, a meno che non venga rilevata in un file eseguibile compilato (exe).  
  
> [!NOTE]
> Se l' `Stop` istruzione viene rilevata nel codice in esecuzione all'esterno del Integrated Development Environment (IDE), il debugger viene richiamato. Questo vale indipendentemente dal fatto che il codice sia stato compilato in modalità debug o al dettaglio.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene utilizzata l' `Stop` istruzione per sospendere l'esecuzione per ogni iterazione del `For...Next` ciclo.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione End](end-statement.md)
