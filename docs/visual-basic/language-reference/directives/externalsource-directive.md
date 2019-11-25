---
title: '#Direttiva ExternalSource'
ms.date: 07/20/2015
f1_keywords:
- '#Externalsource'
- '#ExternalSource'
- vb.ExternalSource
- Externalsource
- vb.#ExternalSource
- ExternalSource
helpviewer_keywords:
- ExternalSource directive (#ExternalSource)
- '#ExternalSource directive'
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
ms.openlocfilehash: fa0a40827c1b3865b90c7d796ea4dd364774e1c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343824"
---
# <a name="externalsource-directive"></a><span data-ttu-id="b3801-102">Direttiva #ExternalSource</span><span class="sxs-lookup"><span data-stu-id="b3801-102">#ExternalSource Directive</span></span>

<span data-ttu-id="b3801-103">Indicates a mapping between specific lines of source code and text external to the source.</span><span class="sxs-lookup"><span data-stu-id="b3801-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3801-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3801-104">Syntax</span></span>  
  
```vb  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="b3801-105">Parti</span><span class="sxs-lookup"><span data-stu-id="b3801-105">Parts</span></span>  

 `StringLiteral`  
 <span data-ttu-id="b3801-106">The path to the external source.</span><span class="sxs-lookup"><span data-stu-id="b3801-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="b3801-107">The line number of the first line of the external source.</span><span class="sxs-lookup"><span data-stu-id="b3801-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="b3801-108">The line where the error occurs in the external source.</span><span class="sxs-lookup"><span data-stu-id="b3801-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="b3801-109">Termina il blocco `#ExternalSource`.</span><span class="sxs-lookup"><span data-stu-id="b3801-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3801-110">Note</span><span class="sxs-lookup"><span data-stu-id="b3801-110">Remarks</span></span>  

 <span data-ttu-id="b3801-111">This directive is used only by the compiler and the debugger.</span><span class="sxs-lookup"><span data-stu-id="b3801-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="b3801-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span><span class="sxs-lookup"><span data-stu-id="b3801-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="b3801-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span><span class="sxs-lookup"><span data-stu-id="b3801-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="b3801-114">External source directives have no effect on compilation and cannot be nested.</span><span class="sxs-lookup"><span data-stu-id="b3801-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="b3801-115">They are intended for internal use by the application only.</span><span class="sxs-lookup"><span data-stu-id="b3801-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3801-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3801-116">See also</span></span>

- [<span data-ttu-id="b3801-117">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="b3801-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
