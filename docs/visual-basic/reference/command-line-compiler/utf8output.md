---
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 0a16cdc535de5ed0619bf080bb4637449b11cfef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403057"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="f3d19-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3d19-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="f3d19-103">Visualizza l'output del compilatore usando la codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f3d19-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3d19-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3d19-104">Syntax</span></span>  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f3d19-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f3d19-105">Arguments</span></span>  
 <span data-ttu-id="f3d19-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="f3d19-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="f3d19-107">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="f3d19-107">Optional.</span></span> <span data-ttu-id="f3d19-108">Il valore predefinito per questa opzione è `-utf8output-` , il che significa che l'output del compilatore non usa la codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f3d19-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="f3d19-109">Specificare `-utf8output` equivale a specificare `-utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="f3d19-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3d19-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="f3d19-110">Remarks</span></span>  
 <span data-ttu-id="f3d19-111">In alcune configurazioni internazionali, l'output del compilatore non può essere visualizzato correttamente nella console.</span><span class="sxs-lookup"><span data-stu-id="f3d19-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="f3d19-112">In tali situazioni, utilizzare `-utf8output` e reindirizzare l'output del compilatore in un file.</span><span class="sxs-lookup"><span data-stu-id="f3d19-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3d19-113">L' `-utf8output` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f3d19-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3d19-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="f3d19-114">Example</span></span>  
 <span data-ttu-id="f3d19-115">Il codice seguente compila `In.vb` e indirizza il compilatore per visualizzare l'output usando la codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f3d19-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3d19-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3d19-116">See also</span></span>

- [<span data-ttu-id="f3d19-117">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f3d19-117">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="f3d19-118">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="f3d19-118">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
