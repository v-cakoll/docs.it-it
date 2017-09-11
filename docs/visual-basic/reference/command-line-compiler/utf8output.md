---
title: /utf8output (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 45361fb1dca34f2cdc849184d0e316b27d9545b6
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="utf8output-visual-basic"></a><span data-ttu-id="920b5-102">/utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="920b5-102">/utf8output (Visual Basic)</span></span>
<span data-ttu-id="920b5-103">Visualizza l'output del compilatore usando la codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="920b5-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="920b5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="920b5-104">Syntax</span></span>  
  
```  
/utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="920b5-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="920b5-105">Arguments</span></span>  
 <span data-ttu-id="920b5-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="920b5-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="920b5-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="920b5-107">Optional.</span></span> <span data-ttu-id="920b5-108">Il valore predefinito per questa opzione è `/utf8output-`, pertanto non verrà utilizzata la codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="920b5-108">The default for this option is `/utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="920b5-109">Specifica di `/utf8output` equivale a specificare `/utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="920b5-109">Specifying `/utf8output` is the same as specifying `/utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="920b5-110">Note</span><span class="sxs-lookup"><span data-stu-id="920b5-110">Remarks</span></span>  
 <span data-ttu-id="920b5-111">In alcune configurazioni internazionali, output del compilatore non può essere visualizzato correttamente nella console.</span><span class="sxs-lookup"><span data-stu-id="920b5-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="920b5-112">In tali situazioni, utilizzare `/utf8output` e reindirizzare l'output del compilatore a un file.</span><span class="sxs-lookup"><span data-stu-id="920b5-112">In such situations, use `/utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="920b5-113">Il `/utf8output` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="920b5-113">The `/utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="920b5-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="920b5-114">Example</span></span>  
 <span data-ttu-id="920b5-115">Il codice seguente Compila `In.vb` e indica al compilatore di visualizzare l'output utilizzando la codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="920b5-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```  
vbc /utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="920b5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="920b5-116">See Also</span></span>  
 <span data-ttu-id="920b5-117">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="920b5-117">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="920b5-118"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="920b5-118"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
