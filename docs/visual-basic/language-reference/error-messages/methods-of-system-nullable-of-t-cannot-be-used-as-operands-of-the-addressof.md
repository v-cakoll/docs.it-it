---
title: È impossibile utilizzare i metodi di "System.Nullable (Of T)" come operandi dell'operatore "AddressOf".
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: 61c6fe7c33b3292066e653304ded43a863413723
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397220"
---
# <a name="methods-of-systemnullableof-t-cannot-be-used-as-operands-of-the-addressof-operator"></a>È impossibile utilizzare i metodi di "System.Nullable (Of T)" come operandi dell'operatore "AddressOf".
Un'istruzione usa l' `AddressOf` operatore con un operando che rappresenta una routine della <xref:System.Nullable%601> struttura.  
  
 **ID errore:** BC32126  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Sostituire il nome della stored procedure nella `AddressOf` clausola con un operando che non è un membro di <xref:System.Nullable%601> .  
  
- Scrivere una classe che esegue il wrapping del metodo di <xref:System.Nullable%601> che si desidera utilizzare. Nell'esempio seguente, la `NullableWrapper` classe definisce un nuovo metodo denominato `GetValueOrDefault` . Poiché questo nuovo metodo non è un membro di <xref:System.Nullable%601> , può essere applicato a `nullInstance` , un'istanza di un tipo nullable, per formare un argomento per `AddressOf` .  
  
```vb  
Module Module1  
  
    Delegate Function Deleg() As Integer  
  
    Sub Main()  
        Dim nullInstance As New Nullable(Of Integer)(1)  
  
        Dim del As Deleg  
  
        ' GetValueOrDefault is a method of the Nullable generic  
        ' type. It cannot be used as an operand of AddressOf.  
        ' del = AddressOf nullInstance.GetValueOrDefault  
  
        ' The following line uses the GetValueOrDefault method  
        ' defined in the NullableWrapper class.  
        del = AddressOf (New NullableWrapper(  
            Of Integer)(nullInstance)).GetValueOrDefault  
  
        Console.WriteLine(del.Invoke())  
    End Sub  
  
    Class NullableWrapper(Of T As Structure)  
        Private m_Value As Nullable(Of T)  
  
        Sub New(ByVal Value As Nullable(Of T))  
            m_Value = Value  
        End Sub  
  
        Public Function GetValueOrDefault() As T  
            Return m_Value.Value  
        End Function  
    End Class  
End Module  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Nullable%601>
- [Operatore AddressOf](../operators/addressof-operator.md)
- [Tipi di valore Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
