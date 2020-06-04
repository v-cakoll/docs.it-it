---
title: La variabile di intervallo <variable> nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: 290ca81dea500558ed73956c91bdf7bfec312014
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400396"
---
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a>La variabile di intervallo \<variable> nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query
Un nome di variabile di intervallo specificato in una `Select` `From` clausola,, `Aggregate` o `Let` Duplica il nome di una variabile di intervallo già specificata in precedenza nella query o il nome di una variabile dichiarata in modo implicito dalla query, ad esempio un nome di campo o il nome di una funzione di aggregazione.  
  
 **ID errore:** BC36633  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Verificare che tutte le variabili di intervallo in un determinato ambito di query abbiano nomi univoci. È possibile racchiudere una query tra parentesi per garantire che le query annidate abbiano un ambito univoco.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Clausola from](../queries/from-clause.md)
- [Clausola Let](../queries/let-clause.md)
- [Aggregate Clause](../queries/aggregate-clause.md)
- [Clausola SELECT](../queries/select-clause.md)
