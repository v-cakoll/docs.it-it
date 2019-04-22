---
title: Il nome di membro di tipo anonimo può essere dedotto solo da un nome semplice o completo senza argomenti
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: b798f296b62b51de34a7ec5ce5a8b608273f5748
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819229"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="38b83-102">Il nome di membro di tipo anonimo può essere dedotto solo da un nome semplice o completo senza argomenti</span><span class="sxs-lookup"><span data-stu-id="38b83-102">Anonymous type member name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="38b83-103">Non è possibile dedurre il nome di un membro di tipo anonimo da un'espressione complessa.</span><span class="sxs-lookup"><span data-stu-id="38b83-103">You cannot infer an anonymous type member name from a complex expression.</span></span>  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 <span data-ttu-id="38b83-104">Per altre informazioni sulle origini da cui i tipi anonimi possono e non è possibile dedurre i nomi dei membri e tipi, vedere [come: In grado di dedurre i nomi delle proprietà e i tipi nelle dichiarazioni di tipo anonimo](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span><span class="sxs-lookup"><span data-stu-id="38b83-104">For more information about sources from which anonymous types can and cannot infer member names and types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
 <span data-ttu-id="38b83-105">**ID errore:** BC36556</span><span class="sxs-lookup"><span data-stu-id="38b83-105">**Error ID:** BC36556</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="38b83-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="38b83-106">To correct this error</span></span>  
  
-   <span data-ttu-id="38b83-107">Assegnare l'espressione con un nome di membro, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="38b83-107">Assign the expression to a member name, as shown in the following code:</span></span>  
  
    ```  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="38b83-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38b83-108">See also</span></span>

- [<span data-ttu-id="38b83-109">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="38b83-109">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="38b83-110">Procedura: Dedurre i nomi delle proprietà e i tipi nelle dichiarazioni di tipo anonimo</span><span class="sxs-lookup"><span data-stu-id="38b83-110">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
