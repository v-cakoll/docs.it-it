---
title: Differenze tra argomenti modificabili e non modificabili (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 2b60d732b260ad0477946e41ece4cd182de541ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649763"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a>Differenze tra argomenti modificabili e non modificabili (Visual Basic)
Quando si chiama una routine, in genere passato uno o più argomenti. Ciascun argomento corrisponde a un elemento di programmazione sottostante. Sia gli elementi sottostanti e gli argomenti stessi possono essere modificabili o meno.  
  
## <a name="modifiable-and-nonmodifiable-elements"></a>Elementi modificabili e non modificabili  
 Può essere un elemento di programmazione un *elemento modificabile*, che può essere modificata, o un *modificabile*, che ha un valore fisso, dopo essere stato creato.  
  
 Nella tabella seguente sono elencati gli elementi di programmazione modificabili e non modificabili.  
  
|Elementi modificabili|Elementi non modificabili|  
|-------------------------|----------------------------|  
|Le variabili locali (dichiarate all'interno di procedure), incluse le variabili di oggetto, ad eccezione di sola lettura|Proprietà, campi e le variabili di sola lettura|  
|Campi (variabili membro delle classi, moduli e strutture), ad eccezione di sola lettura|Costanti e valori letterali|  
|Proprietà, ad eccezione di sola lettura|Membri dell'enumerazione|  
|Elementi della matrice|Espressioni (anche se i relativi elementi sono modificabili)|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a>Argomenti modificabili e  
 Oggetto *argomento modificabile* è un attributo con un elemento sottostante modificabile. Il codice chiamante può archiviare un nuovo valore in qualsiasi momento, e se si passa l'argomento [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), il codice nella procedura possa inoltre modificare l'elemento sottostante nel codice chiamante.  
  
 Oggetto *argomento non modificabile* non contiene un elemento sottostante non modificabile o è passato [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). La procedura non è possibile modificare l'elemento sottostante nel codice chiamante, anche se si tratta di un elemento modificabile. Se si tratta di un elemento non è modificabile, il codice non è possibile modificarlo.  
  
 La routine chiamata potrebbe modificare la copia locale di un argomento non è modificabile, ma tale modifica non ha effetto sull'elemento sottostante nel codice chiamante.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Procedura: Passare argomenti a una routine](./how-to-pass-arguments-to-a-procedure.md)  
 [Passaggio di argomenti per valore e per riferimento](./passing-arguments-by-value-and-by-reference.md)  
 [Differenze tra il passaggio di un argomento per valore e per riferimento](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [Procedura: cambiare il valore di un argomento di routine](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Procedura: impedire la modifica del valore di un argomento di una routine](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Procedura: forzare il passaggio di un argomento per valore](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Passaggio di argomenti in base alla posizione e al nome](./passing-arguments-by-position-and-by-name.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
