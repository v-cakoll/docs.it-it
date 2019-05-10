---
title: La variabile di intervallo <variable> nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: 5e071970eec70828841c686e89aa673d38ff9918
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661628"
---
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a>Variabile di intervallo \<variabile > nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query
Un nome di variabile di intervallo specificato in un `Select`, `From`, `Aggregate`, o `Let` clausola Duplica il nome di una variabile di intervallo già specificato nella query o il nome di una variabile che viene dichiarato in modo implicito dalla query, ad esempio un nome di campo o il nome di una funzione di aggregazione.  
  
 **ID errore:** BC36633  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Assicurarsi che tutte le variabili di intervallo in un particolare ambito di query abbiano nomi univoci. Una query è possibile racchiudere tra parentesi per garantire che le query annidate hanno un ambito univoco.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Let](../../../visual-basic/language-reference/queries/let-clause.md)
- [Clausola Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
