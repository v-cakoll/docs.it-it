---
title: Il nome di membro di tipo anonimo può essere dedotto solo da un nome semplice o completo senza argomenti
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: 38f669fe183ac79ebed6e5a122bc70aedc9bb753
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701222"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="f003b-102">Il nome di membro di tipo anonimo può essere dedotto solo da un nome semplice o completo senza argomenti</span><span class="sxs-lookup"><span data-stu-id="f003b-102">Anonymous type member name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="f003b-103">Non è possibile dedurre un nome di membro di tipo anonimo da un'espressione complessa.</span><span class="sxs-lookup"><span data-stu-id="f003b-103">You cannot infer an anonymous type member name from a complex expression.</span></span>  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 <span data-ttu-id="f003b-104">Per ulteriori informazioni sulle origini da cui i tipi anonimi possono e non possono dedurre i nomi e i tipi dei membri, vedere [How per: Deduce i tipi e i nomi di proprietà nelle dichiarazioni di tipo anonimo @ no__t-0.</span><span class="sxs-lookup"><span data-stu-id="f003b-104">For more information about sources from which anonymous types can and cannot infer member names and types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
 <span data-ttu-id="f003b-105">**ID errore:** BC36556</span><span class="sxs-lookup"><span data-stu-id="f003b-105">**Error ID:** BC36556</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f003b-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f003b-106">To correct this error</span></span>  
  
- <span data-ttu-id="f003b-107">Assegnare l'espressione a un nome di membro, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="f003b-107">Assign the expression to a member name, as shown in the following code:</span></span>  
  
    ```vb  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f003b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f003b-108">See also</span></span>

- [<span data-ttu-id="f003b-109">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="f003b-109">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- <span data-ttu-id="f003b-110">[Procedura: Deduce i tipi e i nomi di proprietà nelle dichiarazioni di tipo anonimo @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="f003b-110">[How to: Infer Property Names and Types in Anonymous Type Declarations](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)</span></span>
