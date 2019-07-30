---
title: 'Procedura: Determinare a quale tipo fa riferimento una variabile oggetto (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 935623dd4b6edca188f932aca0e560130199e8f6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626578"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Procedura: Determinare a quale tipo fa riferimento una variabile oggetto (Visual Basic)

Una variabile oggetto contiene un puntatore ai dati archiviati altrove. Il tipo di dati può essere modificato in fase di esecuzione. In qualsiasi momento, è possibile utilizzare il <xref:System.Type.GetTypeCode%2A> metodo per determinare il tipo in fase di esecuzione corrente o l' [operatore typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md) per verificare se il tipo di runtime corrente è compatibile con un tipo specificato.

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>Per determinare il tipo esatto a cui fa attualmente riferimento una variabile oggetto

1. Nella variabile oggetto chiamare il <xref:System.Object.GetType%2A> metodo per recuperare un <xref:System.Type?displayProperty=nameWithType> oggetto.

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. Nella classe chiamare il metodo <xref:System.Type.GetTypeCode%2A> Shared per recuperare il <xref:System.TypeCode> valore di enumerazione per il tipo dell'oggetto. <xref:System.Type?displayProperty=nameWithType>

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    È possibile testare il <xref:System.TypeCode> valore di enumerazione rispetto a qualsiasi membro di enumerazione di interesse, `Double`ad esempio.

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>Per determinare se il tipo di una variabile oggetto è compatibile con un tipo specificato

- Usare l' `TypeOf` operatore in combinazione con l' [operatore is](../../../../visual-basic/language-reference/operators/is-operator.md) per testare `TypeOf`l'oggetto con... `Is` espressione.

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    `TypeOf`... l'espressione `True` restituisce se il tipo di runtime dell'oggetto è compatibile con il tipo specificato. `Is`

    Il criterio per la compatibilità dipende dal fatto che il tipo specificato sia una classe, una struttura o un'interfaccia. In generale, i tipi sono compatibili se l'oggetto è dello stesso tipo di, eredita da o implementa il tipo specificato. Per ulteriori informazioni, vedere [operatore typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md).

## <a name="compiling-the-code"></a>Compilazione del codice

Si noti che il tipo specificato non può essere una variabile o un'espressione. Deve corrispondere al nome di un tipo definito, ad esempio una classe, una struttura o un'interfaccia. Sono inclusi i tipi intrinseci `Integer` , `String`ad esempio e.

## <a name="see-also"></a>Vedere anche

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
