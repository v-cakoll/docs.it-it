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
ms.openlocfilehash: e9382ee34842fc3a3b4b23f71848bda602c99780
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583227"
---
# <a name="stop-statement-visual-basic"></a>Istruzione Stop (Visual Basic)
Sospende l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a>Note  
 Per sospendere l'esecuzione, è possibile inserire `Stop` istruzioni in qualsiasi punto delle procedure. L'utilizzo dell'istruzione `Stop` è simile all'impostazione di un punto di interruzione nel codice.  
  
 L'istruzione `Stop` sospende l'esecuzione, ma a differenza di `End` non chiude alcun file né cancella alcuna variabile, a meno che non venga rilevata in un file eseguibile compilato (exe).  
  
> [!NOTE]
> Se l'istruzione `Stop` viene rilevata nel codice in esecuzione all'esterno del Integrated Development Environment (IDE), il debugger viene richiamato. Questo vale indipendentemente dal fatto che il codice sia stato compilato in modalità debug o al dettaglio.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene utilizzata l'istruzione `Stop` per sospendere l'esecuzione per ogni iterazione nel ciclo di `For...Next`.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione End](../../../visual-basic/language-reference/statements/end-statement.md)
