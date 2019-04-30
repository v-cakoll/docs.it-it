---
title: 'Procedura: Creare una nuova variabile (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: ee1e93b4e9819992f17738eb024004a4d66210d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938242"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>Procedura: Creare una nuova variabile (Visual Basic)
Creare una variabile con un [istruzione Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).  
  
### <a name="to-create-a-new-variable"></a>Per creare una nuova variabile  
  
1. Dichiarare la variabile in un `Dim` istruzione.  
  
    ```  
    Dim newCustomer  
    ```  
  
2. Includono informazioni specifiche per le caratteristiche della variabile, ad esempio [privati](../../../../visual-basic/language-reference/modifiers/private.md), [statici](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), oppure [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md). Per altre informazioni, vedere [caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
     Non è necessario il `Dim` parola chiave se si usano altre parole chiave nella dichiarazione.  
  
3. Seguire le specifiche con il nome della variabile, che deve seguire le convenzioni e regole di Visual Basic. Per altre informazioni, vedere [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
    ```  
    Public Static newCustomer  
    ```  
  
4. Seguire il nome con il [come](../../../../visual-basic/language-reference/statements/as-clause.md) clausola per specificare il tipo di dati della variabile.  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     Se non si specifica il tipo di dati, viene usato il valore predefinito: `Object`.  
  
5. Seguire le `As` clausola con un segno di uguale (`=`) e seguire il segno di uguale con valore iniziale della variabile.  
  
     Visual Basic assegna il valore specificato per la variabile ogni volta che viene eseguito il `Dim` istruzione. Se non si specifica un valore iniziale, Visual Basic viene assegnato il valore iniziale predefinito per il tipo di dati della variabile quando si accede alla prima di tutto il codice che contiene il `Dim` istruzione.  
  
     Se la variabile è un tipo riferimento, è possibile creare un'istanza della relativa classe includendo il [nuovo operatore](../../../../visual-basic/language-reference/operators/new-operator.md) parola chiave nel `As` clausola. Se non si usa `New`, il valore iniziale della variabile è [Nothing](../../../../visual-basic/language-reference/nothing.md).  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a>Vedere anche

- [Variabili](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Dichiarazione di variabile](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Istruzioni](../../../../visual-basic/language-reference/statements/index.md)
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Istruzione Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
