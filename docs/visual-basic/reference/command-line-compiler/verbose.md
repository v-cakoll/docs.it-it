---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 8c5bc1d2ce331b8fe9461f91d64fbeab5a070b59
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004979"
---
# <a name="-verbose"></a><span data-ttu-id="072c4-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="072c4-102">-verbose</span></span>
<span data-ttu-id="072c4-103">Fa in modo che il compilatore generi messaggi di errore e di stato dettagliati.</span><span class="sxs-lookup"><span data-stu-id="072c4-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="072c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="072c4-104">Syntax</span></span>  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="072c4-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="072c4-105">Arguments</span></span>  
 <span data-ttu-id="072c4-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="072c4-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="072c4-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="072c4-107">Optional.</span></span> <span data-ttu-id="072c4-108">Specificare `-verbose` equivale a specificare `-verbose+`, che determina la generazione di messaggi dettagliati da parte del compilatore.</span><span class="sxs-lookup"><span data-stu-id="072c4-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="072c4-109">Il valore predefinito per questa opzione `-verbose-`è.</span><span class="sxs-lookup"><span data-stu-id="072c4-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="072c4-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="072c4-110">Remarks</span></span>  
 <span data-ttu-id="072c4-111">L' `-verbose` opzione Visualizza informazioni sul numero totale di errori emessi dal compilatore, segnala gli assembly caricati da un modulo e Visualizza i file attualmente in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="072c4-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="072c4-112">L' `-verbose` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="072c4-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="072c4-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="072c4-113">Example</span></span>  
 <span data-ttu-id="072c4-114">Il codice seguente compila `In.vb` e indirizza il compilatore per visualizzare informazioni dettagliate sullo stato.</span><span class="sxs-lookup"><span data-stu-id="072c4-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="072c4-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="072c4-115">See also</span></span>

- [<span data-ttu-id="072c4-116">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="072c4-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="072c4-117">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="072c4-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
