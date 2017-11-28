---
title: Variabile di intervallo &lt;variabile&gt; nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords: BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ccbac48694a13daa09f2511cf39d5dbd51cdaaf7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="range-variable-ltvariablegt-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a>Variabile di intervallo &lt;variabile&gt; nasconde una variabile in un blocco di inclusione, una variabile di intervallo precedentemente definita o una variabile dichiarata in modo implicito in un'espressione di query
Un nome di variabile di intervallo specificato un `Select`, `From`, `Aggregate`, o `Let` clausola Duplica il nome di una variabile di intervallo già specificato nella query o il nome di una variabile dichiarata in modo implicito tramite la query, ad esempio un nome di campo o il nome di una funzione di aggregazione.  
  
 **ID errore:** BC36633  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Verificare che tutte le variabili di intervallo in un particolare ambito di query abbiano nomi univoci. È possibile racchiudere tra parentesi per garantire che le query annidate abbiano un ambito univoco di una query.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Let](../../../visual-basic/language-reference/queries/let-clause.md)  
 [Clausola Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
