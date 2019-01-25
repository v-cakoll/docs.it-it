---
title: '#ExternalSource (direttiva) (Visual Basic)'
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
ms.openlocfilehash: 550934723a5599573be578ce5746ab7520b59dd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705969"
---
# <a name="externalsource-directive"></a><span data-ttu-id="97d81-102">Direttiva #ExternalSource</span><span class="sxs-lookup"><span data-stu-id="97d81-102">#ExternalSource Directive</span></span>
<span data-ttu-id="97d81-103">Indica un mapping tra le righe specifiche del codice sorgente e testo esterno al codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="97d81-103">Indicates a mapping between specific lines of source code and text external to the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97d81-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97d81-104">Syntax</span></span>  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## <a name="parts"></a><span data-ttu-id="97d81-105">Parti</span><span class="sxs-lookup"><span data-stu-id="97d81-105">Parts</span></span>  
 `StringLiteral`  
 <span data-ttu-id="97d81-106">Il percorso all'origine esterna.</span><span class="sxs-lookup"><span data-stu-id="97d81-106">The path to the external source.</span></span>  
  
 `IntLiteral`  
 <span data-ttu-id="97d81-107">Il numero di riga della prima riga dell'origine esterna.</span><span class="sxs-lookup"><span data-stu-id="97d81-107">The line number of the first line of the external source.</span></span>  
  
 `LogicalLine`  
 <span data-ttu-id="97d81-108">La riga in cui l'errore si verifica nell'origine esterna.</span><span class="sxs-lookup"><span data-stu-id="97d81-108">The line where the error occurs in the external source.</span></span>  
  
 `#End ExternalSource`  
 <span data-ttu-id="97d81-109">Termina il blocco `#ExternalSource`.</span><span class="sxs-lookup"><span data-stu-id="97d81-109">Terminates the `#ExternalSource` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97d81-110">Note</span><span class="sxs-lookup"><span data-stu-id="97d81-110">Remarks</span></span>  
 <span data-ttu-id="97d81-111">Questa direttiva viene usata solo dal compilatore e il debugger.</span><span class="sxs-lookup"><span data-stu-id="97d81-111">This directive is used only by the compiler and the debugger.</span></span>  
  
 <span data-ttu-id="97d81-112">Un file di origine può includere le direttive origine esterna, che indicano un mapping tra righe di codice nel file di origine specifiche e testo esterno per l'origine, ad esempio un file con estensione aspx.</span><span class="sxs-lookup"><span data-stu-id="97d81-112">A source file may include external source directives, which indicate a mapping between specific lines of code in the source file and text external to the source, such as an .aspx file.</span></span> <span data-ttu-id="97d81-113">Se si verificano errori nel codice sorgente designata durante la compilazione, sono identificate come provenienti dall'origine esterna.</span><span class="sxs-lookup"><span data-stu-id="97d81-113">If errors are encountered in the designated source code during compilation, they are identified as coming from the external source.</span></span>  
  
 <span data-ttu-id="97d81-114">Direttive origine esterna non hanno alcun effetto sulla compilazione e non possono essere annidate.</span><span class="sxs-lookup"><span data-stu-id="97d81-114">External source directives have no effect on compilation and cannot be nested.</span></span> <span data-ttu-id="97d81-115">Essi sono destinati all'utilizzo interno da parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="97d81-115">They are intended for internal use by the application only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97d81-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97d81-116">See also</span></span>
- [<span data-ttu-id="97d81-117">Compilazione condizionale</span><span class="sxs-lookup"><span data-stu-id="97d81-117">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
