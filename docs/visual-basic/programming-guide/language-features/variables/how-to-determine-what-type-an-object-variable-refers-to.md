---
title: 'Procedura: Determinare a quale tipo fa riferimento una variabile oggetto (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 6499dfce880cc9ce16e5d77887afc0598692f48e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342869"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Procedura: Determinare a quale tipo fa riferimento una variabile oggetto (Visual Basic)
Una variabile oggetto contiene un puntatore ai dati archiviati in un' posizione. Il tipo di dati può modificare durante la fase di esecuzione. In qualsiasi momento, è possibile usare la <xref:System.Type.GetTypeCode%2A> metodo per determinare il tipo di runtime corrente, o il [operatore TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) per determinare se il tipo in fase di esecuzione è compatibile con un tipo specificato.  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>Per determinare che il tipo esatto una variabile oggetto attualmente fa riferimento a  
  
1. La variabile oggetto, chiamare il <xref:System.Object.GetType%2A> metodo per recuperare un <xref:System.Type?displayProperty=nameWithType> oggetto.  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2. Nel <xref:System.Type?displayProperty=nameWithType> classe, chiamare il metodo condiviso <xref:System.Type.GetTypeCode%2A> per recuperare il <xref:System.TypeCode> valore di enumerazione per il tipo dell'oggetto.  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     È possibile testare il <xref:System.TypeCode> valore dell'enumerazione su un qualsiasi membro di enumerazione è di interesse, ad esempio `Double`.  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>Per determinare se un oggetto tipo di variabile è compatibile con un tipo specificato  
  
-   Usare la `TypeOf` operatore in combinazione con il [operatore Is](../../../../visual-basic/language-reference/operators/is-operator.md) per testare l'oggetto con un `TypeOf`... `Is` espressione.  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     Il `TypeOf`... `Is` espressione restituisce `True` se l'oggetto della fase di esecuzione tipo è compatibile con il tipo specificato.  
  
     Il criterio per la compatibilità dipende dal fatto che il tipo specificato è una classe, struttura o interfaccia. In generale, i tipi sono compatibili se l'oggetto è dello stesso tipo, eredita o implementa il tipo specificato. Per altre informazioni, vedere [operatore TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Si noti che il tipo specificato non può essere una variabile o espressione. Deve essere il nome di un tipo definito, ad esempio una classe, struttura o interfaccia. Questo include, ad esempio tipi intrinseci `Integer` e `String`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
