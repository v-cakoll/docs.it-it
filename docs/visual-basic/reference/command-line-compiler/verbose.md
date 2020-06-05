---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 405b557568a736de3ddc3b51e265261222613131
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403031"
---
# <a name="-verbose"></a><span data-ttu-id="104d1-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="104d1-102">-verbose</span></span>
<span data-ttu-id="104d1-103">Fa in modo che il compilatore generi messaggi di errore e di stato dettagliati.</span><span class="sxs-lookup"><span data-stu-id="104d1-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="104d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="104d1-104">Syntax</span></span>  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="104d1-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="104d1-105">Arguments</span></span>  
 <span data-ttu-id="104d1-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="104d1-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="104d1-107">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="104d1-107">Optional.</span></span> <span data-ttu-id="104d1-108">Specificare `-verbose` equivale `-verbose+` a specificare, che determina la generazione di messaggi dettagliati da parte del compilatore.</span><span class="sxs-lookup"><span data-stu-id="104d1-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="104d1-109">Il valore predefinito per questa opzione è `-verbose-` .</span><span class="sxs-lookup"><span data-stu-id="104d1-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="104d1-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="104d1-110">Remarks</span></span>  
 <span data-ttu-id="104d1-111">L' `-verbose` opzione Visualizza informazioni sul numero totale di errori emessi dal compilatore, segnala gli assembly caricati da un modulo e Visualizza i file attualmente in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="104d1-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="104d1-112">L' `-verbose` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="104d1-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="104d1-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="104d1-113">Example</span></span>  
 <span data-ttu-id="104d1-114">Il codice seguente compila `In.vb` e indirizza il compilatore per visualizzare informazioni dettagliate sullo stato.</span><span class="sxs-lookup"><span data-stu-id="104d1-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="104d1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="104d1-115">See also</span></span>

- [<span data-ttu-id="104d1-116">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="104d1-116">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="104d1-117">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="104d1-117">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
