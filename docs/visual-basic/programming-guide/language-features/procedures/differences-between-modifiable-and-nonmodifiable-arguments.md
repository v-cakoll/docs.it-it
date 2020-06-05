---
title: Differenze tra argomenti modificabili e non modificabili
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 733f92cc2cdaa6e923c57649774ceb64de172c18
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403343"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a>Differenze tra argomenti modificabili e non modificabili (Visual Basic)
Quando si chiama una routine, in genere si passa uno o più argomenti. Ogni argomento corrisponde a un elemento di programmazione sottostante. Sia gli elementi sottostanti che gli argomenti possono essere modificabili o non modificabili.  
  
## <a name="modifiable-and-nonmodifiable-elements"></a>Elementi modificabili e non modificabili  
 Un elemento di programmazione può essere un *elemento modificabile*, il cui valore può essere modificato o un *elemento non modificabile*, che ha un valore fisso dopo che è stato creato.  
  
 Nella tabella seguente sono elencati gli elementi di programmazione modificabili e non modificabili.  
  
|Elementi modificabili|Elementi non modificabili|  
|-------------------------|----------------------------|  
|Variabili locali (dichiarate all'interno di procedure), incluse le variabili oggetto, ad eccezione di sola lettura|Variabili, campi e proprietà di sola lettura|  
|Campi (variabili membro di moduli, classi e strutture), ad eccezione di sola lettura|Costanti e valori letterali|  
|Proprietà, ad eccezione di sola lettura|Membri dell'enumerazione|  
|Elementi di matrice|Espressioni (anche se i relativi elementi sono modificabili)|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a>Argomenti modificabili e non modificabili  
 Un *argomento modificabile* è uno con un elemento sottostante modificabile. Il codice chiamante può archiviare un nuovo valore in qualsiasi momento e, se si passa l'argomento [ByRef](../../../language-reference/modifiers/byref.md), il codice nella procedura può anche modificare l'elemento sottostante nel codice chiamante.  
  
 Un *argomento non modificabile* presenta un elemento sottostante non modificabile o viene passato [ByVal](../../../language-reference/modifiers/byval.md). La routine non può modificare l'elemento sottostante nel codice chiamante, anche se è un elemento modificabile. Se è un elemento non modificabile, il codice chiamante non può modificarlo.  
  
 La procedura chiamata potrebbe modificare la copia locale di un argomento non modificabile, ma la modifica non influisce sull'elemento sottostante nel codice chiamante.  
  
## <a name="see-also"></a>Vedere anche

- [Procedure](./index.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Procedura: passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)
- [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)
- [Differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Procedura: cambiare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md)
- [Procedura: impedire la modifica del valore di un argomento di una routine](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Procedura: forzare il passaggio di un argomento per valore](./how-to-force-an-argument-to-be-passed-by-value.md)
- [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../data-types/value-types-and-reference-types.md)
