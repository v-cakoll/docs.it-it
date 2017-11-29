---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06770f05aabedcf13cc9af1970a2c511a30c73b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="eb2fa-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb2fa-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="eb2fa-103">Specifica che un parametro di routine accetta una matrice facoltativa di elementi del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="eb2fa-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="eb2fa-104">`ParamArray`può essere utilizzato solo nel parametro ultimo di un elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="eb2fa-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb2fa-105">Note</span><span class="sxs-lookup"><span data-stu-id="eb2fa-105">Remarks</span></span>  
 <span data-ttu-id="eb2fa-106">`ParamArray`Consente di passare un numero arbitrario di argomenti per la procedura.</span><span class="sxs-lookup"><span data-stu-id="eb2fa-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="eb2fa-107">Oggetto `ParamArray` parametro sempre è dichiarato mediante [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="eb2fa-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="eb2fa-108">È possibile fornire uno o più argomenti a un `ParamArray` parametro passando una matrice di dati appropriato, un elenco delimitato da virgole dei valori o non di tipo.</span><span class="sxs-lookup"><span data-stu-id="eb2fa-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="eb2fa-109">Per ulteriori informazioni, vedere "Chiamata di ParamArray" [matrici di parametro](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="eb2fa-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eb2fa-110">Ogni volta che gestisce una matrice che può essere elevata per un periodo illimitato, c'è un rischio di sovraccaricare capacità interna dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eb2fa-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="eb2fa-111">Se si accetta una matrice di parametri dal codice chiamante, è necessario verificarne la lunghezza e adottare se è troppo grande per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eb2fa-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="eb2fa-112">Il modificatore `ParamArray` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="eb2fa-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="eb2fa-113">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="eb2fa-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="eb2fa-114">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="eb2fa-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="eb2fa-115">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="eb2fa-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="eb2fa-116">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="eb2fa-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="eb2fa-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb2fa-117">See Also</span></span>  
 [<span data-ttu-id="eb2fa-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="eb2fa-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="eb2fa-119">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="eb2fa-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
