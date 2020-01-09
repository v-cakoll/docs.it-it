---
title: 'Procedura: determinare a quale tipo fa riferimento una variabile oggetto'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: b3778a170759f685db78e7dcde219138196f9eca
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344192"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Procedura: determinare a quale tipo fa riferimento una variabile oggetto (Visual Basic)

Una variabile oggetto contiene un puntatore ai dati archiviati altrove. Il tipo di dati può essere modificato in fase di esecuzione. In qualsiasi momento, è possibile utilizzare il metodo <xref:System.Type.GetTypeCode%2A> per determinare il tipo in fase di esecuzione corrente o l' [operatore typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md) per verificare se il tipo di runtime corrente è compatibile con un tipo specificato.

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>Per determinare il tipo esatto a cui fa attualmente riferimento una variabile oggetto

1. Nella variabile oggetto chiamare il metodo <xref:System.Object.GetType%2A> per recuperare un oggetto <xref:System.Type?displayProperty=nameWithType>.

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. Nella classe <xref:System.Type?displayProperty=nameWithType> chiamare il metodo Shared <xref:System.Type.GetTypeCode%2A> per recuperare il <xref:System.TypeCode> valore di enumerazione per il tipo dell'oggetto.

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    È possibile testare il valore di enumerazione <xref:System.TypeCode> rispetto a qualsiasi membro di enumerazione di interesse, ad esempio `Double`.

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>Per determinare se il tipo di una variabile oggetto è compatibile con un tipo specificato

- Utilizzare l'operatore `TypeOf` in combinazione con l' [operatore is](../../../../visual-basic/language-reference/operators/is-operator.md) per testare l'oggetto con un'espressione `TypeOf`...`Is`.

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    L'espressione `TypeOf`...`Is` restituisce `True` se il tipo di runtime dell'oggetto è compatibile con il tipo specificato.

    Il criterio per la compatibilità dipende dal fatto che il tipo specificato sia una classe, una struttura o un'interfaccia. In generale, i tipi sono compatibili se l'oggetto è dello stesso tipo di, eredita da o implementa il tipo specificato. Per ulteriori informazioni, vedere [operatore typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md).

## <a name="compile-the-code"></a>Compilare il codice

Si noti che il tipo specificato non può essere una variabile o un'espressione. Deve corrispondere al nome di un tipo definito, ad esempio una classe, una struttura o un'interfaccia. Sono inclusi i tipi intrinseci, ad esempio `Integer` e `String`.

## <a name="see-also"></a>Vedere anche

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Valori di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
