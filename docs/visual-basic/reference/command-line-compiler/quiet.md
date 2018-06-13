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
ms.openlocfilehash: e67fe05507c8cb3edd7f46cad19211ba11e3b054
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652396"
---
# <a name="-quiet"></a><span data-ttu-id="64222-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="64222-102">-quiet</span></span>
<span data-ttu-id="64222-103">Impedisce al compilatore di visualizzare codice per avvisi ed errori relativi alla sintassi.</span><span class="sxs-lookup"><span data-stu-id="64222-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64222-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64222-104">Syntax</span></span>  
  
```  
-quiet  
```  
  
## <a name="remarks"></a><span data-ttu-id="64222-105">Note</span><span class="sxs-lookup"><span data-stu-id="64222-105">Remarks</span></span>  
 <span data-ttu-id="64222-106">Per impostazione predefinita, l'opzione `-quiet` non è attiva.</span><span class="sxs-lookup"><span data-stu-id="64222-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="64222-107">Quando il compilatore segnala un errore di sintassi o di un avviso, viene visualizzata anche la riga del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="64222-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="64222-108">Per le applicazioni che analizzano l'output del compilatore, potrebbe essere più utile per il compilatore di generare solo il testo della diagnostica.</span><span class="sxs-lookup"><span data-stu-id="64222-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>  
  
 <span data-ttu-id="64222-109">Nell'esempio seguente, `Module1` genera un errore che include il codice sorgente quando viene compilato senza `-quiet`.</span><span class="sxs-lookup"><span data-stu-id="64222-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="64222-110">Output:</span><span class="sxs-lookup"><span data-stu-id="64222-110">Output:</span></span>  
 
```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
``` 
 <span data-ttu-id="64222-111">Compilato con `-quiet`, il compilatore restituisce solo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="64222-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  <span data-ttu-id="64222-112">Il `-quiet` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="64222-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64222-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="64222-113">Example</span></span>  
 <span data-ttu-id="64222-114">Il codice seguente Compila `T2.vb` non visualizzare il codice per la diagnostica del compilatore relativi alla sintassi:</span><span class="sxs-lookup"><span data-stu-id="64222-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>  
  
```  
vbc -quiet t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="64222-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64222-115">See Also</span></span>  
 [<span data-ttu-id="64222-116">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="64222-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="64222-117">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="64222-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
