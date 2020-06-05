---
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: e3c24818ea87884a0dd9b42c604e13e16ca6d3d7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84391820"
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="7fea3-102">ParamArray (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7fea3-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="7fea3-103">Specifica che un parametro di routine accetta una matrice facoltativa di elementi del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="7fea3-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="7fea3-104">`ParamArray`può essere usato solo nell'ultimo parametro di un elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="7fea3-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fea3-105">Commenti</span><span class="sxs-lookup"><span data-stu-id="7fea3-105">Remarks</span></span>  
 <span data-ttu-id="7fea3-106">`ParamArray`consente di passare un numero arbitrario di argomenti alla procedura.</span><span class="sxs-lookup"><span data-stu-id="7fea3-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="7fea3-107">Un `ParamArray` parametro viene sempre dichiarato utilizzando [ByVal](byval.md).</span><span class="sxs-lookup"><span data-stu-id="7fea3-107">A `ParamArray` parameter is always declared using [ByVal](byval.md).</span></span>  
  
 <span data-ttu-id="7fea3-108">È possibile specificare uno o più argomenti per un `ParamArray` parametro passando una matrice del tipo di dati appropriato, un elenco delimitato da virgole di valori o nulla.</span><span class="sxs-lookup"><span data-stu-id="7fea3-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="7fea3-109">Per informazioni dettagliate, vedere la sezione relativa alla chiamata a ParamArray in [matrici di parametri](../../programming-guide/language-features/procedures/parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="7fea3-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7fea3-110">Ogni volta che si tratta di una matrice che può essere indefinitamente grande, esiste il rischio di sovraeseguire una capacità interna dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7fea3-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="7fea3-111">Se si accetta una matrice di parametri dal codice chiamante, è necessario testarne la lunghezza ed eseguire le operazioni appropriate se è troppo grande per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7fea3-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="7fea3-112">Il modificatore `ParamArray` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7fea3-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="7fea3-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="7fea3-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="7fea3-114">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="7fea3-114">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="7fea3-115">Property Statement</span><span class="sxs-lookup"><span data-stu-id="7fea3-115">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="7fea3-116">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="7fea3-116">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="7fea3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fea3-117">See also</span></span>

- [<span data-ttu-id="7fea3-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7fea3-118">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="7fea3-119">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="7fea3-119">Parameter Arrays</span></span>](../../programming-guide/language-features/procedures/parameter-arrays.md)
