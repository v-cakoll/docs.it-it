---
title: '&#39;Estensione di&#39; attributo può essere applicato solo a &#39;modulo&#39;, &#39;Sub&#39;, o &#39;funzione&#39; dichiarazioni'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: fabd602f31a362fe33954253d565e86a065e0a83
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718234"
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a><span data-ttu-id="73510-102">&#39;Estensione di&#39; attributo può essere applicato solo a &#39;modulo&#39;, &#39;Sub&#39;, o &#39;funzione&#39; dichiarazioni</span><span class="sxs-lookup"><span data-stu-id="73510-102">&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations</span></span>
<span data-ttu-id="73510-103">L'unico modo per estendere un tipo di dati in Visual Basic consiste nel definire un metodo di estensione all'interno di un modulo standard.</span><span class="sxs-lookup"><span data-stu-id="73510-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="73510-104">Il metodo di estensione può essere un' `Sub` routine o un `Function` procedure.</span><span class="sxs-lookup"><span data-stu-id="73510-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="73510-105">Tutti i metodi di estensione devono essere contrassegnati con l'attributo di estensione `<Extension()>`, dal <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="73510-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="73510-106">Facoltativamente, un modulo che contiene un metodo di estensione può essere contrassegnato nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="73510-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="73510-107">Nessun altro uso dell'attributo di estensione è valido.</span><span class="sxs-lookup"><span data-stu-id="73510-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="73510-108">**ID errore:** BC36550</span><span class="sxs-lookup"><span data-stu-id="73510-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="73510-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="73510-109">To correct this error</span></span>  
  
-   <span data-ttu-id="73510-110">Rimuovere l'attributo di estensione.</span><span class="sxs-lookup"><span data-stu-id="73510-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="73510-111">Riprogettare l'estensione di un metodo, definito in un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="73510-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73510-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="73510-112">Example</span></span>  
 <span data-ttu-id="73510-113">L'esempio seguente definisce una `Print` metodo per il `String` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="73510-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="73510-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73510-114">See also</span></span>
- [<span data-ttu-id="73510-115">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="73510-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="73510-116">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="73510-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="73510-117">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="73510-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
