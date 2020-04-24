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
ms.openlocfilehash: 6e773c60469e8426956c92a5aa377741ba5af4d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005286"
---
# <a name="-quiet"></a><span data-ttu-id="a032a-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="a032a-102">-quiet</span></span>

<span data-ttu-id="a032a-103">Impedisce al compilatore di visualizzare codice per avvisi ed errori relativi alla sintassi.</span><span class="sxs-lookup"><span data-stu-id="a032a-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>

## <a name="syntax"></a><span data-ttu-id="a032a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a032a-104">Syntax</span></span>

```console
-quiet
```

## <a name="remarks"></a><span data-ttu-id="a032a-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a032a-105">Remarks</span></span>

<span data-ttu-id="a032a-106">Per impostazione predefinita, l'opzione `-quiet` non è attiva.</span><span class="sxs-lookup"><span data-stu-id="a032a-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="a032a-107">Quando il compilatore segnala un errore o un avviso correlato alla sintassi, restituisce anche la riga dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="a032a-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="a032a-108">Per le applicazioni che analizzano l'output del compilatore, potrebbe essere più pratico per il compilatore restituire solo il testo della diagnostica.</span><span class="sxs-lookup"><span data-stu-id="a032a-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>

<span data-ttu-id="a032a-109">Nell'esempio seguente viene `Module1` restituito un errore che include il codice sorgente quando viene compilato `-quiet`senza.</span><span class="sxs-lookup"><span data-stu-id="a032a-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

<span data-ttu-id="a032a-110">Output:</span><span class="sxs-lookup"><span data-stu-id="a032a-110">Output:</span></span>

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

<span data-ttu-id="a032a-111">Compilato con `-quiet`, il compilatore restituisce solo quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a032a-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> <span data-ttu-id="a032a-112">L' `-quiet` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="a032a-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="a032a-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="a032a-113">Example</span></span>

<span data-ttu-id="a032a-114">Il codice seguente compila `T2.vb` e non Visualizza il codice per la diagnostica del compilatore correlato alla sintassi:</span><span class="sxs-lookup"><span data-stu-id="a032a-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a><span data-ttu-id="a032a-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a032a-115">See also</span></span>

- [<span data-ttu-id="a032a-116">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a032a-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a032a-117">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="a032a-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
