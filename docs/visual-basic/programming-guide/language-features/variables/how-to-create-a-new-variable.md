---
title: 'Procedura: creare una nuova variabile (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: f2e6a97e78bc42ebea9519eb0aa4411e9aec24cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651544"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Procedura: creare una nuova variabile (Visual Basic)
Creare una variabile con un [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
### <a name="to-create-a-new-variable"></a>Per creare una nuova variabile  
  
1.  Dichiarare la variabile in un `Dim` istruzione.  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  Includere specifiche per le caratteristiche della variabile, ad esempio [privata](../../../../visual-basic/language-reference/modifiers/private.md), [statico](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), o [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md). Per ulteriori informazioni, vedere [caratteristiche di elemento dichiarato](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
     Non è necessario il `Dim` (parola chiave), se si utilizzano altre parole chiave nella dichiarazione.  
  
3.  Seguire le specifiche con il nome della variabile, che deve seguire le convenzioni e le regole di Visual Basic. Per ulteriori informazioni, vedere [nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  Dopo il nome con il [come](../../../../visual-basic/language-reference/statements/as-clause.md) clausola per specificare il tipo di dati della variabile.  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     Se non si specifica il tipo di dati, viene utilizzato il valore predefinito: `Object`.  
  
5.  Seguire il `As` clausola con un segno di uguale (`=`) e seguire il segno di uguale con valore iniziale della variabile.  
  
     Visual Basic assegna il valore specificato alla variabile ogni volta che viene eseguito il `Dim` istruzione. Se non si specifica un valore iniziale, Visual Basic viene assegnato il valore iniziale predefinito per il tipo di dati della variabile quando la prima volta inserisce il codice che contiene il `Dim` istruzione.  
  
     Se la variabile è un tipo riferimento, è possibile creare un'istanza della relativa classe includendo il [nuovo operatore](../../../../visual-basic/language-reference/operators/new-operator.md) parola chiave nel `As` clausola. Se non si utilizza `New`, il valore iniziale della variabile è [nulla](../../../../visual-basic/language-reference/nothing.md).  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Tipi valore e tipi riferimento](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Istruzioni](../../../../visual-basic/language-reference/statements/index.md)  
 [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Istruzione Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
