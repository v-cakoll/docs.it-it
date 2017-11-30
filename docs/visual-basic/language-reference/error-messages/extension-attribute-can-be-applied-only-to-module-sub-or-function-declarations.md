---
title: "&#39; Estensione &#39; attributo può essere applicato solo a &#39; Modulo &#39; &#39; Sub &#39; o &#39; Funzione &#39; dichiarazioni"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords: BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d77933c52484eb934501107d1ddad15f0eca826
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a><span data-ttu-id="7a654-102">&#39; Estensione &#39; attributo può essere applicato solo a &#39; Modulo &#39; &#39; Sub &#39; o &#39; Funzione &#39; dichiarazioni</span><span class="sxs-lookup"><span data-stu-id="7a654-102">&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations</span></span>
<span data-ttu-id="7a654-103">L'unico modo per estendere un tipo di dati in Visual Basic consiste nel definire un metodo di estensione all'interno di un modulo standard.</span><span class="sxs-lookup"><span data-stu-id="7a654-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="7a654-104">Il metodo di estensione può essere un `Sub` stored procedure o un `Function` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="7a654-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="7a654-105">Tutti i metodi di estensione devono essere contrassegnati con l'attributo di estensione, `<Extension()>`, dal <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7a654-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="7a654-106">Facoltativamente, un modulo che contiene un metodo di estensione può essere contrassegnato nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="7a654-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="7a654-107">Nessun altro utilizzo dell'attributo di estensione è valido.</span><span class="sxs-lookup"><span data-stu-id="7a654-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="7a654-108">**ID errore:** BC36550</span><span class="sxs-lookup"><span data-stu-id="7a654-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7a654-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7a654-109">To correct this error</span></span>  
  
-   <span data-ttu-id="7a654-110">Rimuovere l'attributo di estensione.</span><span class="sxs-lookup"><span data-stu-id="7a654-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="7a654-111">Riprogettare l'estensione di un metodo, definito in un modulo contenitore.</span><span class="sxs-lookup"><span data-stu-id="7a654-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a654-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a654-112">Example</span></span>  
 <span data-ttu-id="7a654-113">L'esempio seguente definisce un `Print` metodo per il `String` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="7a654-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7a654-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a654-114">See Also</span></span>  
 [<span data-ttu-id="7a654-115">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="7a654-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="7a654-116">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="7a654-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [<span data-ttu-id="7a654-117">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="7a654-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
