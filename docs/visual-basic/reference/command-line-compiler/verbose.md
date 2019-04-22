---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: f6d896fb0d41a8fa3ed613d29bc3fca2bd14cc5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832792"
---
# <a name="-verbose"></a><span data-ttu-id="d4bff-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="d4bff-102">-verbose</span></span>
<span data-ttu-id="d4bff-103">Indica al compilatore di generare messaggi di stato e di errore dettagliati.</span><span class="sxs-lookup"><span data-stu-id="d4bff-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4bff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4bff-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d4bff-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d4bff-105">Arguments</span></span>  
 <span data-ttu-id="d4bff-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d4bff-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="d4bff-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d4bff-107">Optional.</span></span> <span data-ttu-id="d4bff-108">Che specifica `-verbose` è uguale a quello ottenuto specificando `-verbose+`, in modo che il compilatore generi i messaggi dettagliati.</span><span class="sxs-lookup"><span data-stu-id="d4bff-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="d4bff-109">Il valore predefinito per questa opzione è `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="d4bff-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4bff-110">Note</span><span class="sxs-lookup"><span data-stu-id="d4bff-110">Remarks</span></span>  
 <span data-ttu-id="d4bff-111">Il `-verbose` opzione Visualizza le informazioni sul numero totale di errori generati dal compilatore, segnala gli assembly vengono caricati da un modulo e consente di visualizzare quali file sono attualmente in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d4bff-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4bff-112">Il `-verbose` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d4bff-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4bff-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4bff-113">Example</span></span>  
 <span data-ttu-id="d4bff-114">Il codice seguente Compila `In.vb` e indica al compilatore di visualizzare informazioni dettagliate sullo stato.</span><span class="sxs-lookup"><span data-stu-id="d4bff-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4bff-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4bff-115">See also</span></span>

- [<span data-ttu-id="d4bff-116">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4bff-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d4bff-117">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="d4bff-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
