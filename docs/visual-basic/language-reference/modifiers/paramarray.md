---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: b9dee0fc876c6e7a02d085db7db4bf1c5dd2c68d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053912"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="14670-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14670-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="14670-103">Specifica che un parametro di routine accetta una matrice facoltativa di elementi del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="14670-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="14670-104">`ParamArray` può essere utilizzato solo sull'ultimo parametro dell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="14670-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14670-105">Note</span><span class="sxs-lookup"><span data-stu-id="14670-105">Remarks</span></span>  
 <span data-ttu-id="14670-106">`ParamArray` Consente di passare un numero arbitrario di argomenti per la procedura.</span><span class="sxs-lookup"><span data-stu-id="14670-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="14670-107">Oggetto `ParamArray` parametro viene sempre dichiarato usando [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="14670-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="14670-108">È possibile fornire uno o più argomenti per un `ParamArray` passando una matrice dei dati appropriati tipo di parametro, un elenco delimitato da virgole di valori o niente affatto.</span><span class="sxs-lookup"><span data-stu-id="14670-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="14670-109">Per informazioni dettagliate, vedere la sezione "Chiamata ParamArray" nella [matrici di parametri](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="14670-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="14670-110">Ogni volta che gestisce una matrice che può essere elevato per un periodo illimitato, sussiste il rischio di sovraccaricare capacità interna dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="14670-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="14670-111">Se si accetta una matrice di parametri dal codice chiamante, occorre verificarne la lunghezza ed eseguire i passaggi appropriati, se è troppo grande per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="14670-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="14670-112">Il modificatore `ParamArray` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="14670-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="14670-113">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="14670-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="14670-114">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="14670-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="14670-115">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="14670-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="14670-116">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="14670-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="14670-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14670-117">See also</span></span>

- [<span data-ttu-id="14670-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="14670-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="14670-119">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="14670-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
