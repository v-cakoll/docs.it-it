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
ms.openlocfilehash: 4e846c59d3da01d4d9fe943795376c37db4fb397
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>Differenze tra il passaggio di un argomento per valore e per riferimento (Visual Basic)
Quando si passano a uno o più argomenti a una routine, ciascun argomento corrisponde a un elemento di programmazione sottostante nel codice chiamante. È possibile passare il valore di questo elemento sottostante o un riferimento a esso. Questo è noto come il *meccanismo di passaggio*.  
  
## <a name="passing-by-value"></a>passaggio per valore  
 Si passa un argomento *dal valore* specificando il [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) (parola chiave) per il parametro corrispondente nella definizione della routine. Quando si utilizza il meccanismo di passaggio, Visual Basic copia il valore dell'elemento di programmazione sottostante in una variabile locale nella routine. Il codice della routine non hanno accesso all'elemento sottostante nel codice chiamante.  
  
## <a name="passing-by-reference"></a>Il passaggio per riferimento  
 Si passa un argomento *per riferimento* specificando il [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) (parola chiave) per il parametro corrispondente nella definizione della routine. Quando si utilizza il meccanismo di passaggio, Visual Basic fornisce la procedura di un riferimento diretto all'elemento di programmazione sottostante nel codice chiamante.  
  
## <a name="passing-mechanism-and-element-type"></a>Meccanismo di passaggio e tipo di elemento  
 La scelta del meccanismo di passaggio non è lo stesso come la classificazione del tipo di elemento sottostante. Passaggio per valore o per riferimento si riferisce a quali Visual Basic fornisce al codice della routine. Un tipo di valore o riferimento fa riferimento a un elemento di programmazione come archiviato in memoria.  
  
 Tuttavia, il meccanismo di passaggio e il tipo di elemento sono correlati tra loro. Il valore di un tipo riferimento è un puntatore ai dati in un' posizione in memoria. Ciò significa che quando si passa un tipo di riferimento per valore, il codice della stored procedure dispone di un puntatore ai dati dell'elemento sottostante, anche se non può accedere l'elemento sottostante. Ad esempio, se l'elemento è una variabile di matrice, il codice della routine non ha accesso alla variabile stessa, ma possa accedere ai membri di matrice.  
  
## <a name="ability-to-modify"></a>Possibilità di modificare  
 Quando si passa un elemento non è modificabile come argomento, la procedura mai modificarlo nel codice chiamante, se viene passato `ByVal` o `ByRef`.  
  
 Per un elemento modificabile, nella tabella seguente viene riepilogata l'interazione tra il tipo di elemento e il meccanismo di passaggio.  
  
|Tipo di elemento|Passato `ByVal`|Passato `ByRef`|  
|------------------|--------------------|--------------------|  
|Tipo di valore (contiene un solo valore)|La routine non è possibile modificare la variabile o i relativi membri.|La procedura è possibile modificare la variabile e i relativi membri.|  
|Tipo di riferimento (contiene un puntatore a un'istanza di classe o struttura)|La procedura non è possibile modificare la variabile, ma può modificare i membri dell'istanza a cui fa riferimento.|La procedura è possibile modificare la variabile e i membri dell'istanza a cui fa riferimento.|  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)  
 [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)  
 [Differenze tra argomenti modificabili e non modificabili](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [Procedura: cambiare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Procedura: impedire la modifica del valore di un argomento di una routine](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Procedura: forzare il passaggio di un argomento per valore](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
