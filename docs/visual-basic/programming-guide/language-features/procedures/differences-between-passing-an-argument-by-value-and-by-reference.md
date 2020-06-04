---
title: Differenze tra il passaggio di un argomento per valore e per riferimento
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
ms.openlocfilehash: bd316ae2239ad85e4ef6dadbb8a634d5fe7ecf02
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403330"
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>Differenze tra il passaggio di un argomento per valore e per riferimento (Visual Basic)
Quando si passano uno o più argomenti a una routine, ogni argomento corrisponde a un elemento di programmazione sottostante nel codice chiamante. È possibile passare il valore di questo elemento sottostante o un riferimento ad esso. Questa operazione è nota come *meccanismo di passaggio*.  
  
## <a name="passing-by-value"></a>passaggio per valore  
 Passare un argomento per *valore* specificando la parola chiave [ByVal](../../../language-reference/modifiers/byval.md) per il parametro corrispondente nella definizione della procedura. Quando si utilizza questo meccanismo di passaggio, Visual Basic copia il valore dell'elemento di programmazione sottostante in una variabile locale nella routine. Il codice della procedura non ha accesso all'elemento sottostante nel codice chiamante.  
  
## <a name="passing-by-reference"></a>Passaggio per riferimento  
 Per passare un argomento per *riferimento* , specificare la parola chiave [ByRef](../../../language-reference/modifiers/byref.md) per il parametro corrispondente nella definizione della procedura. Quando si utilizza questo meccanismo di passaggio, Visual Basic assegna alla routine un riferimento diretto all'elemento di programmazione sottostante nel codice chiamante.  
  
## <a name="passing-mechanism-and-element-type"></a>Passaggio del meccanismo e del tipo di elemento  
 La scelta del meccanismo di passaggio non corrisponde alla classificazione del tipo di elemento sottostante. Il passaggio per valore o per riferimento si riferisce a ciò che Visual Basic fornisce al codice della procedura. Un tipo di valore o un tipo di riferimento si riferisce al modo in cui un elemento di programmazione viene archiviato in memoria.  
  
 Tuttavia, il meccanismo di passaggio e il tipo di elemento sono correlati. Il valore di un tipo di riferimento è un puntatore ai dati in un'altra posizione nella memoria. Ciò significa che quando si passa un tipo di riferimento per valore, il codice della procedura presenta un puntatore ai dati dell'elemento sottostante, anche se non è in grado di accedere all'elemento sottostante stesso. Se, ad esempio, l'elemento è una variabile di matrice, il codice della procedura non ha accesso alla variabile stessa, ma può accedere ai membri della matrice.  
  
## <a name="ability-to-modify"></a>Possibilità di modificare  
 Quando si passa un elemento non modificabile come argomento, la procedura non può mai modificarla nel codice chiamante, indipendentemente dal fatto che venga passato `ByVal` o `ByRef` .  
  
 Per un elemento modificabile, nella tabella seguente viene riepilogata l'interazione tra il tipo di elemento e il meccanismo di passaggio.  
  
|Tipo di elemento|Passato`ByVal`|Passato`ByRef`|  
|------------------|--------------------|--------------------|  
|Tipo valore (contiene solo un valore)|La stored procedure non può modificare la variabile o i relativi membri.|La procedura può modificare la variabile e i relativi membri.|  
|Tipo di riferimento (contiene un puntatore a un'istanza di classe o struttura)|La stored procedure non può modificare la variabile ma può modificare i membri dell'istanza a cui fa riferimento.|La procedura può modificare la variabile e i membri dell'istanza a cui fa riferimento.|  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Differenze tra argomenti modificabili e non modificabili](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Procedura: cambiare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md)
- [Procedura: impedire la modifica del valore di un argomento di una routine](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Procedura: forzare il passaggio di un argomento per valore](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../data-types/value-types-and-reference-types.md)
