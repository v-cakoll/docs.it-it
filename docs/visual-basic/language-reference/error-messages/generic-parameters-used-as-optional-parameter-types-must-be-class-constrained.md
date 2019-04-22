---
title: I parametri generici utilizzati come tipi di parametri facoltativi devono essere vincolati a livello di classe
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 9b0293472f5eda74c2bf8fb215e15ae5cf8d8b98
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813899"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>I parametri generici utilizzati come tipi di parametri facoltativi devono essere vincolati a livello di classe
Una routine è dichiarata con un parametro facoltativo che usa un parametro di tipo che non sia vincolato a un tipo riferimento.  
  
 È necessario fornire sempre un valore predefinito per ogni parametro facoltativo. Se il parametro è di un tipo riferimento, il valore facoltativo deve essere `Nothing`, ovvero un valore valido per qualsiasi tipo di riferimento. Tuttavia, se il parametro è un tipo di valore, tale tipo deve essere un tipo di dati elementari predefinito da Visual Basic. Questo avviene perché un tipo valore composito, ad esempio una struttura definita dall'utente, prevede alcun valore predefinito valido.  
  
 Quando si usa un parametro di tipo per un parametro facoltativo, è necessario garantire che sia di un tipo di riferimento per evitare l'insorgere di un tipo di valore non prevede alcun valore predefinito valido. Ciò significa che è necessario vincolare il parametro di tipo con il `Class` parola chiave o con il nome di una classe specifica.  
  
 **ID errore:** BC32124  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Vincolare il parametro di tipo per accettare solo un tipo riferimento oppure non usarlo per il parametro facoltativo.  
  
## <a name="see-also"></a>Vedere anche

- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Elenco dei tipi](../../../visual-basic/language-reference/statements/type-list.md)
- [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Parametri facoltativi](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Nothing](../../../visual-basic/language-reference/nothing.md)
