---
title: Il tipo della variabile '<variablename>' non verrà dedotto perché associato a un ambito di inclusione
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: e56529919945558df178e18a83a895a79bfe4919
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512719"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>Il tipo per la variabile\<' variablename >' non verrà dedotto perché è associato a un campo in un ambito di inclusione

Il tipo per la variabile\<' variablename >' non verrà dedotto perché è associato a un campo in un ambito di inclusione. Modificare il nome di '\<VariableName >' o usare il nome completo (ad esempio,' me. VariableName ' o ' MyBase. VariableName ').

Una variabile di controllo loop nel codice ha lo stesso nome di un campo della classe o di un altro ambito di inclusione. Poiché la variabile di controllo viene utilizzata senza `As` una clausola, viene associata al campo nell'ambito di inclusione e il compilatore non crea una nuova variabile o ne deduce il tipo.

Nell'esempio `Index`seguente, la variabile di controllo `For` nell'istruzione è associata `Customer` al `Index` campo nella classe. Il compilatore non crea una nuova variabile per la variabile `Index` di controllo o ne deduce il tipo.

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

    ' The following line will raise this warning.
        For Index = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

**ID errore:** BC42110

### <a name="to-address-this-warning"></a>Per risolvere questo avviso

- Impostare la variabile di controllo del ciclo come variabile locale cambiando il nome in un identificatore che non sia anche il nome di un campo della classe.

  ```vb
  For I = 1 To 10
  ```

- Chiarire che la variabile di controllo del ciclo viene associata al campo della classe `Me.` anteponendo il nome della variabile.

  ```vb
  For Me.Index = 1 To 10
  ```

- Anziché basarsi sull'inferenza del tipo locale, usare `As` una clausola per specificare un tipo per la variabile di controllo del ciclo.

  ```vb
  For Index As Integer = 1 To 10
  ```

## <a name="example"></a>Esempio
 Il codice seguente illustra l'esempio precedente con la prima correzione sul posto.

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

        For I = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

## <a name="see-also"></a>Vedere anche

- [Istruzione Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Istruzione For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Procedura: Fare riferimento all'istanza corrente di un oggetto](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Me, My, MyBase e MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
