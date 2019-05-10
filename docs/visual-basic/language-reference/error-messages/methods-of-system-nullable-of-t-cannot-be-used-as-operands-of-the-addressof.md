---
title: È impossibile utilizzare i metodi di "System.Nullable (Of T)" come operandi dell'operatore "AddressOf".
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: e55e561fa20a3740d352537958681b0a66fc381e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592035"
---
# <a name="methods-of-systemnullableof-t-cannot-be-used-as-operands-of-the-addressof-operator"></a><span data-ttu-id="ce0c7-102">È impossibile utilizzare i metodi di "System.Nullable (Of T)" come operandi dell'operatore "AddressOf".</span><span class="sxs-lookup"><span data-stu-id="ce0c7-102">Methods of 'System.Nullable(Of T)' cannot be used as operands of the 'AddressOf' operator</span></span>
<span data-ttu-id="ce0c7-103">Un'istruzione Usa il `AddressOf` operatore con un operando che rappresenta una procedura del <xref:System.Nullable%601> struttura.</span><span class="sxs-lookup"><span data-stu-id="ce0c7-103">A statement uses the `AddressOf` operator with an operand that represents a procedure of the <xref:System.Nullable%601> structure.</span></span>  
  
 <span data-ttu-id="ce0c7-104">**ID errore:** BC32126</span><span class="sxs-lookup"><span data-stu-id="ce0c7-104">**Error ID:** BC32126</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ce0c7-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ce0c7-105">To correct this error</span></span>  
  
- <span data-ttu-id="ce0c7-106">Sostituire il nome della routine nel `AddressOf` clausola con un operando che non è un membro di <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="ce0c7-106">Replace the procedure name in the `AddressOf` clause with an operand that is not a member of <xref:System.Nullable%601>.</span></span>  
  
- <span data-ttu-id="ce0c7-107">Scrivere una classe che il wrapping del metodo di <xref:System.Nullable%601> che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ce0c7-107">Write a class that wraps the method of <xref:System.Nullable%601> that you want to use.</span></span> <span data-ttu-id="ce0c7-108">Nell'esempio seguente, il `NullableWrapper` classe definisce un nuovo metodo denominato `GetValueOrDefault`.</span><span class="sxs-lookup"><span data-stu-id="ce0c7-108">In the following example, the `NullableWrapper` class defines a new method named `GetValueOrDefault`.</span></span> <span data-ttu-id="ce0c7-109">Poiché questo nuovo metodo non è un membro del <xref:System.Nullable%601>, è possibile applicarlo al `nullInstance`, un'istanza di un tipo che ammette valori null, in modo da formare un argomento per `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="ce0c7-109">Because this new method is not a member of <xref:System.Nullable%601>, it can be applied to `nullInstance`, an instance of a nullable type, to form an argument for `AddressOf`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce0c7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce0c7-110">See also</span></span>

- <xref:System.Nullable%601>
- [<span data-ttu-id="ce0c7-111">Operatore AddressOf</span><span class="sxs-lookup"><span data-stu-id="ce0c7-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="ce0c7-112">Tipi di valori nullable</span><span class="sxs-lookup"><span data-stu-id="ce0c7-112">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="ce0c7-113">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce0c7-113">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
