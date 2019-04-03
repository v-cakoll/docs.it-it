---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: 32f82eb428c1d3bc427a10b9ca7a1a5feb9e339a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816538"
---
# <a name="-quiet"></a><span data-ttu-id="1fa1c-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="1fa1c-102">-quiet</span></span>
<span data-ttu-id="1fa1c-103">Impedisce al compilatore di visualizzare codice per avvisi ed errori relativi alla sintassi.</span><span class="sxs-lookup"><span data-stu-id="1fa1c-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fa1c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1fa1c-104">Syntax</span></span>  
  
```  
-quiet  
```  
  
## <a name="remarks"></a><span data-ttu-id="1fa1c-105">Note</span><span class="sxs-lookup"><span data-stu-id="1fa1c-105">Remarks</span></span>  
 <span data-ttu-id="1fa1c-106">Per impostazione predefinita, l'opzione `-quiet` non è attiva.</span><span class="sxs-lookup"><span data-stu-id="1fa1c-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="1fa1c-107">Quando il compilatore segnala un errore di sintassi relativa o avviso, viene visualizzata anche la riga di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="1fa1c-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="1fa1c-108">Per le applicazioni che analizzare l'output del compilatore, potrebbe essere più utile per il compilatore di generare solo il testo della diagnostica.</span><span class="sxs-lookup"><span data-stu-id="1fa1c-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>  
  
 <span data-ttu-id="1fa1c-109">Nell'esempio riportato di seguito `Module1` genera un errore che include il codice sorgente quando viene compilato senza `-quiet`.</span><span class="sxs-lookup"><span data-stu-id="1fa1c-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="1fa1c-110">Output:</span><span class="sxs-lookup"><span data-stu-id="1fa1c-110">Output:</span></span>  
 
```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
``` 
 <span data-ttu-id="1fa1c-111">Compilato con `-quiet`, il compilatore genera solo gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1fa1c-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  <span data-ttu-id="1fa1c-112">Il `-quiet` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="1fa1c-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fa1c-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="1fa1c-113">Example</span></span>  
 <span data-ttu-id="1fa1c-114">Il codice seguente Compila `T2.vb` non visualizzare il codice per la diagnostica del compilatore relativi alla sintassi:</span><span class="sxs-lookup"><span data-stu-id="1fa1c-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>  
  
```  
vbc -quiet t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1fa1c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fa1c-115">See also</span></span>

- [<span data-ttu-id="1fa1c-116">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1fa1c-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1fa1c-117">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="1fa1c-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
