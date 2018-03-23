---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 97f90b39046aebe0cd15c7e033d8e588045491f7
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="e3531-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3531-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="e3531-103">Visualizza l'output del compilatore usando la codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e3531-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3531-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3531-104">Syntax</span></span>  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e3531-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e3531-105">Arguments</span></span>  
 <span data-ttu-id="e3531-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="e3531-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="e3531-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e3531-107">Optional.</span></span> <span data-ttu-id="e3531-108">Il valore predefinito per questa opzione è `-utf8output-`, ovvero non verrà utilizzata la codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e3531-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="e3531-109">Specifica di `-utf8output` è lo stesso effetto `-utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="e3531-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3531-110">Note</span><span class="sxs-lookup"><span data-stu-id="e3531-110">Remarks</span></span>  
 <span data-ttu-id="e3531-111">In alcune configurazioni internazionali, output del compilatore non può essere visualizzato correttamente nella console di.</span><span class="sxs-lookup"><span data-stu-id="e3531-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="e3531-112">In tali situazioni, utilizzare `-utf8output` e reindirizzare l'output del compilatore in un file.</span><span class="sxs-lookup"><span data-stu-id="e3531-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3531-113">Il `-utf8output` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="e3531-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3531-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="e3531-114">Example</span></span>  
 <span data-ttu-id="e3531-115">Il codice seguente Compila `In.vb` e indica al compilatore di visualizzare l'output utilizzando la codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="e3531-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3531-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3531-116">See Also</span></span>  
 [<span data-ttu-id="e3531-117">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e3531-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e3531-118">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="e3531-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
