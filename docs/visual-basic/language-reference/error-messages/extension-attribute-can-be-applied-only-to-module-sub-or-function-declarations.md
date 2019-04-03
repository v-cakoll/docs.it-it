---
title: È possibile applicare l'attributo 'Extension' solo alle dichiarazioni 'Module', 'Sub' o 'Function'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: a4561359e4d7cb0f6ebe44a5deb09b3374556ed8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826184"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a><span data-ttu-id="88ec8-102">È possibile applicare l'attributo 'Extension' solo alle dichiarazioni 'Module', 'Sub' o 'Function'</span><span class="sxs-lookup"><span data-stu-id="88ec8-102">'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations</span></span>
<span data-ttu-id="88ec8-103">L'unico modo per estendere un tipo di dati in Visual Basic consiste nel definire un metodo di estensione all'interno di un modulo standard.</span><span class="sxs-lookup"><span data-stu-id="88ec8-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="88ec8-104">Il metodo di estensione può essere un' `Sub` routine o un `Function` procedure.</span><span class="sxs-lookup"><span data-stu-id="88ec8-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="88ec8-105">Tutti i metodi di estensione devono essere contrassegnati con l'attributo di estensione `<Extension()>`, dal <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="88ec8-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="88ec8-106">Facoltativamente, un modulo che contiene un metodo di estensione può essere contrassegnato nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="88ec8-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="88ec8-107">Nessun altro uso dell'attributo di estensione è valido.</span><span class="sxs-lookup"><span data-stu-id="88ec8-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="88ec8-108">**ID errore:** BC36550</span><span class="sxs-lookup"><span data-stu-id="88ec8-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="88ec8-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="88ec8-109">To correct this error</span></span>  
  
-   <span data-ttu-id="88ec8-110">Rimuovere l'attributo di estensione.</span><span class="sxs-lookup"><span data-stu-id="88ec8-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="88ec8-111">Riprogettare l'estensione di un metodo, definito in un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="88ec8-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88ec8-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="88ec8-112">Example</span></span>  
 <span data-ttu-id="88ec8-113">L'esempio seguente definisce una `Print` metodo per il `String` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="88ec8-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="88ec8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88ec8-114">See also</span></span>

- [<span data-ttu-id="88ec8-115">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="88ec8-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="88ec8-116">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="88ec8-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="88ec8-117">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="88ec8-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
