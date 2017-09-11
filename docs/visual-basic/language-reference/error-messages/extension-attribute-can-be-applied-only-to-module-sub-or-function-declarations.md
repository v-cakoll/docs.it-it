---
title: "Attributo &quot;Extension&quot; può essere applicato solo alle dichiarazioni &quot;Module&quot;, &quot;Sub&quot; o &quot;Function&quot; | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
dev_langs:
- VB
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e88241180fe1320bfd1db90a38a9a7560ae3dead
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a><span data-ttu-id="3d710-102">Attributo 'Extension' può essere applicato solo alle dichiarazioni 'Module', 'Sub' o 'Function'</span><span class="sxs-lookup"><span data-stu-id="3d710-102">&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations</span></span>
<span data-ttu-id="3d710-103">L'unico modo per estendere un tipo di dati in Visual Basic consiste nel definire un metodo di estensione all'interno di un modulo standard.</span><span class="sxs-lookup"><span data-stu-id="3d710-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="3d710-104">Il metodo di estensione può essere un `Sub` procedura o una `Function` procedura.</span><span class="sxs-lookup"><span data-stu-id="3d710-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="3d710-105">Tutti i metodi di estensione devono essere contrassegnati con l'attributo di estensione, `<Extension()>`, dal <xref:System.Runtime.CompilerServices?displayProperty=fullName>dello spazio dei nomi.</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3d710-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="3d710-106">Facoltativamente, un modulo che contiene un metodo di estensione può essere contrassegnato nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="3d710-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="3d710-107">Nessun altro utilizzo dell'attributo di estensione è valido.</span><span class="sxs-lookup"><span data-stu-id="3d710-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="3d710-108">**ID errore:** BC36550</span><span class="sxs-lookup"><span data-stu-id="3d710-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3d710-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3d710-109">To correct this error</span></span>  
  
-   <span data-ttu-id="3d710-110">Rimuovere l'attributo di estensione.</span><span class="sxs-lookup"><span data-stu-id="3d710-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="3d710-111">Riprogettare l'estensione di un metodo, definito in un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="3d710-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d710-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d710-112">Example</span></span>  
 <span data-ttu-id="3d710-113">L'esempio seguente definisce una `Print` metodo per la `String` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="3d710-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3d710-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d710-114">See Also</span></span>  
 <span data-ttu-id="3d710-115">[Cenni preliminari sugli attributi](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="3d710-115">[Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="3d710-116"> [Metodi di estensione](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) </span><span class="sxs-lookup"><span data-stu-id="3d710-116"> [Extension Methods](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) </span></span>  
<span data-ttu-id="3d710-117"> [Istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md)</span><span class="sxs-lookup"><span data-stu-id="3d710-117"> [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)</span></span>

