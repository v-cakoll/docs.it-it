---
title: Facoltativo
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: c46d06dba61158d7362d736731161be306af3f10
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392145"
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)

Specifica che un argomento di routine può essere omesso quando viene chiamata la stored procedure.

## <a name="remarks"></a>Commenti

Per ogni parametro facoltativo, è necessario specificare un'espressione costante come valore predefinito del parametro. Se l'espressione restituisce [Nothing](../nothing.md), il valore predefinito del tipo di dati value viene utilizzato come valore predefinito del parametro.

Se l'elenco di parametri contiene un parametro facoltativo, anche ogni parametro che lo segue deve essere facoltativo.

Il modificatore `Optional` può essere usato nei contesti seguenti:

- [Declare Statement](../statements/declare-statement.md)

- [Istruzione Function](../statements/function-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Istruzione Sub](../statements/sub-statement.md)

> [!NOTE]
> Quando si chiama una routine con o senza parametri facoltativi, è possibile passare gli argomenti in base alla posizione o al nome. Per ulteriori informazioni, vedere [passaggio di argomenti in base alla posizione e al nome](../../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).

> [!NOTE]
> È anche possibile definire una routine con parametri facoltativi tramite l'overload. Se si dispone di un parametro facoltativo, è possibile definire due versioni di overload della stored procedure, una che accetta il parametro e l'altra. Per altre informazioni, vedere [Procedure Overloading](../../programming-guide/language-features/procedures/procedure-overloading.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene definita una routine con un parametro facoltativo.

```vb
Public Function FindMatches(ByRef values As List(Of String),
                            ByVal searchString As String,
                            Optional ByVal matchCase As Boolean = False) As List(Of String)

    Dim results As IEnumerable(Of String)

    If matchCase Then
        results = From v In values
                  Where v.Contains(searchString)
    Else
        results = From v In values
                  Where UCase(v).Contains(UCase(searchString))
    End If

    Return results.ToList()
End Function
```

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come chiamare una stored procedure con argomenti passati in base alla posizione e con argomenti passati in base al nome. La procedura include due parametri facoltativi.

[!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]

## <a name="see-also"></a>Vedere anche

- [Elenco parametri](../statements/parameter-list.md)
- [Parametri facoltativi](../../programming-guide/language-features/procedures/optional-parameters.md)
- [Parole chiave](../keywords/index.md)
