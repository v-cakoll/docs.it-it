---
title: I parametri generici utilizzati come tipi di parametri facoltativi devono essere vincolati a livello di classe
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 273ea592e73be5d76a4ffef077e691014a108347
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402927"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>I parametri generici utilizzati come tipi di parametri facoltativi devono essere vincolati a livello di classe
Una routine viene dichiarata con un parametro facoltativo che utilizza un parametro di tipo che non è vincolato come tipo di riferimento.  
  
 È sempre necessario specificare un valore predefinito per ogni parametro facoltativo. Se il parametro è di un tipo di riferimento, il valore facoltativo deve essere `Nothing` , che è un valore valido per qualsiasi tipo di riferimento. Tuttavia, se il parametro è di un tipo di valore, tale tipo deve essere un tipo di dati Elementary predefinito da Visual Basic. Questo perché un tipo di valore composito, ad esempio una struttura definita dall'utente, non ha un valore predefinito valido.  
  
 Quando si usa un parametro di tipo per un parametro facoltativo, è necessario garantire che sia di un tipo di riferimento per evitare la possibilità di un tipo di valore senza valore predefinito valido. Ciò significa che è necessario vincolare il parametro di tipo con la `Class` parola chiave o con il nome di una classe specifica.  
  
 **ID errore:** BC32124  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Vincolare il parametro di tipo in modo che accetti solo un tipo riferimento o non lo usi per il parametro facoltativo.  
  
## <a name="see-also"></a>Vedere anche

- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Type List](../statements/type-list.md)
- [Istruzione Class](../statements/class-statement.md)
- [Parametri facoltativi](../../programming-guide/language-features/procedures/optional-parameters.md)
- [Strutture](../../programming-guide/language-features/data-types/structures.md)
- [Nothing](../nothing.md)
