---
title: 'Procedura: determinare a quale tipo fa riferimento una variabile oggetto'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: d3224000f5958a8619e38c4d2f6dc5dbb275ad45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410490"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Procedura: determinare a quale tipo fa riferimento una variabile oggetto (Visual Basic)

Una variabile oggetto contiene un puntatore ai dati archiviati altrove. Il tipo di dati può essere modificato in fase di esecuzione. In qualsiasi momento, è possibile utilizzare il <xref:System.Type.GetTypeCode%2A> metodo per determinare il tipo in fase di esecuzione corrente o l' [operatore typeof](../../../language-reference/operators/typeof-operator.md) per verificare se il tipo di runtime corrente è compatibile con un tipo specificato.

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>Per determinare il tipo esatto a cui fa attualmente riferimento una variabile oggetto

1. Nella variabile oggetto chiamare il <xref:System.Object.GetType%2A> metodo per recuperare un <xref:System.Type?displayProperty=nameWithType> oggetto.

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. Nella <xref:System.Type?displayProperty=nameWithType> classe chiamare il metodo Shared <xref:System.Type.GetTypeCode%2A> per recuperare il valore di <xref:System.TypeCode> enumerazione per il tipo dell'oggetto.

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    È possibile testare il <xref:System.TypeCode> valore di enumerazione rispetto a qualsiasi membro di enumerazione di interesse, ad esempio `Double` .

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>Per determinare se il tipo di una variabile oggetto è compatibile con un tipo specificato

- Usare l' `TypeOf` operatore in combinazione con l' [operatore is](../../../language-reference/operators/is-operator.md) per testare l'oggetto con un' `TypeOf` espressione... `Is` .

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    L' `TypeOf` espressione... `Is` restituisce `True` se il tipo di runtime dell'oggetto è compatibile con il tipo specificato.

    Il criterio per la compatibilità dipende dal fatto che il tipo specificato sia una classe, una struttura o un'interfaccia. In generale, i tipi sono compatibili se l'oggetto è dello stesso tipo di, eredita da o implementa il tipo specificato. Per ulteriori informazioni, vedere [operatore typeof](../../../language-reference/operators/typeof-operator.md).

## <a name="compile-the-code"></a>Compilare il codice

Si noti che il tipo specificato non può essere una variabile o un'espressione. Deve corrispondere al nome di un tipo definito, ad esempio una classe, una struttura o un'interfaccia. Sono inclusi i tipi intrinseci, ad esempio `Integer` e `String` .

## <a name="see-also"></a>Vedere anche

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [Variabili oggetto](object-variables.md)
- [Valori di variabili oggetto](object-variable-values.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
