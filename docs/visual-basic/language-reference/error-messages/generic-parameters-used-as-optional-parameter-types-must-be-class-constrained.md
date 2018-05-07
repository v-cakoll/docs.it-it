---
title: I parametri generici utilizzati come tipi di parametri facoltativi devono essere vincolati a livello di classe
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 7e2b59f758ef236717a912694576b514e2ae8a60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>I parametri generici utilizzati come tipi di parametri facoltativi devono essere vincolati a livello di classe
Una routine è dichiarata con un parametro facoltativo che utilizza un parametro di tipo che non è vincolato da un tipo di riferimento.  
  
 È sempre necessario fornire un valore predefinito per ogni parametro facoltativo. Se il parametro è di un tipo riferimento, il valore facoltativo deve essere `Nothing`, ovvero un valore valido per qualsiasi tipo di riferimento. Tuttavia, se il parametro è un tipo di valore, tale tipo deve essere un tipo di dati elementare predefinito da Visual Basic. Infatti, un tipo di valore composta, ad esempio una struttura definita dall'utente, non dispone di alcun valore predefinito valido.  
  
 Quando si utilizza un parametro di tipo per un parametro facoltativo, è necessario garantire che sia di un tipo di riferimento per evitare la possibilità di un tipo di valore non prevede alcun valore predefinito valido. Ciò significa che è necessario vincolare il parametro di tipo con il `Class` (parola chiave) oppure con il nome di una classe specifica.  
  
 **ID errore:** BC32124  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Vincolare il parametro di tipo accetti solo un tipo riferimento o non utilizzare tale valore per il parametro facoltativo.  
  
## <a name="see-also"></a>Vedere anche  
 [Tipi generici in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md)  
 [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Parametri facoltativi](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Nothing](../../../visual-basic/language-reference/nothing.md)
