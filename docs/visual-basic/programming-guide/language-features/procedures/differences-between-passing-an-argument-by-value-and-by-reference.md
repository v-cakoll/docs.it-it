---
title: Differenze tra il passaggio di un argomento per valore e per riferimento (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
ms.openlocfilehash: 1b85941c14721280a5025db442c4793930244ec8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864546"
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>Differenze tra il passaggio di un argomento per valore e per riferimento (Visual Basic)
Quando si passano a uno o più argomenti a una routine, ciascun argomento corrisponde a un elemento di programmazione sottostante nel codice chiamante. È possibile passare il valore di questo elemento sottostante o un riferimento a esso. Questo è noto come il *meccanismo di trasferimento*.  
  
## <a name="passing-by-value"></a>passaggio per valore  
 Si passa un argomento *dal valore* specificando la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) parola chiave per il parametro corrispondente nella definizione della procedura. Quando si usa il meccanismo di passaggio, Visual Basic copia il valore dell'elemento di programmazione sottostante in una variabile locale nella routine. Il codice della routine è privo di qualsiasi accesso all'elemento sottostante nel codice chiamante.  
  
## <a name="passing-by-reference"></a>Il passaggio per riferimento  
 Si passa un argomento *per riferimento* specificando la [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) parola chiave per il parametro corrispondente nella definizione della procedura. Quando si usa il meccanismo di passaggio, Visual Basic fornisce la procedura di un riferimento diretto all'elemento di programmazione sottostante nel codice chiamante.  
  
## <a name="passing-mechanism-and-element-type"></a>Meccanismo di passaggio e il tipo di elemento  
 La scelta del meccanismo di trasferimento non è quello utilizzato per la classificazione del tipo di elemento sottostante. Il passaggio per valore o per riferimento fa riferimento a ciò che Visual Basic fornisce al codice della routine. Un tipo valore o tipo di riferimento si riferisce al modo in cui un elemento di programmazione viene archiviato in memoria.  
  
 Tuttavia, il meccanismo di passaggio e il tipo di elemento sono correlati tra loro. Il valore di un tipo riferimento è un puntatore ai dati in un' posizione in memoria. Ciò significa che quando si passa un tipo di riferimento per valore, il codice della routine ha un puntatore ai dati dell'elemento sottostante, anche se non può accedere l'elemento sottostante. Ad esempio, se l'elemento è una variabile di matrice, il codice della routine non ha accesso alla variabile stessa, ma possa accedere ai membri di matrice.  
  
## <a name="ability-to-modify"></a>Possibilità di modificare  
 Quando si passa un elemento non è modificabile come argomento, la procedura non può mai modificarla nel codice chiamante, a se viene passato `ByVal` o `ByRef`.  
  
 Per un elemento modificabile, la tabella seguente riepiloga l'interazione tra il tipo di elemento e il meccanismo di passaggio.  
  
|Tipo di elemento|Passato `ByVal`|Passato `ByRef`|  
|------------------|--------------------|--------------------|  
|Tipo di valore (contiene un solo valore)|La procedura non è possibile modificare la variabile o i relativi membri.|La procedura è possibile modificare la variabile e i relativi membri.|  
|Tipo di riferimento (contiene un puntatore a un'istanza di classe o struttura)|La procedura non è possibile modificare la variabile, ma può modificare i membri dell'istanza a cui punta.|La procedura è possibile modificare la variabile e i membri dell'istanza a cui punta.|  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Differenze tra argomenti modificabili e non modificabili](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Procedura: Modificare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md)
- [Procedura: Proteggere un argomento di routine modifica del valore](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Procedura: Forzare un argomento da passare per valore](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
