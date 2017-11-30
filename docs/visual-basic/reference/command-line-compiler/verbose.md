---
title: /verbose
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5480f828fa1f0b6d71fa649bf44513ce806bb440
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="verbose"></a><span data-ttu-id="c75fc-102">/verbose</span><span class="sxs-lookup"><span data-stu-id="c75fc-102">/verbose</span></span>
<span data-ttu-id="c75fc-103">Fa sì che il compilatore genera messaggi di stato e di errore dettagliati.</span><span class="sxs-lookup"><span data-stu-id="c75fc-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c75fc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c75fc-104">Syntax</span></span>  
  
```  
/verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c75fc-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c75fc-105">Arguments</span></span>  
 <span data-ttu-id="c75fc-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c75fc-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="c75fc-107">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c75fc-107">Optional.</span></span> <span data-ttu-id="c75fc-108">Specifica di `/verbose` è lo stesso effetto `/verbose+`, che indica al compilatore di messaggi dettagliati.</span><span class="sxs-lookup"><span data-stu-id="c75fc-108">Specifying `/verbose` is the same as specifying `/verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="c75fc-109">Il valore predefinito per questa opzione è `/verbose-`.</span><span class="sxs-lookup"><span data-stu-id="c75fc-109">The default for this option is `/verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c75fc-110">Note</span><span class="sxs-lookup"><span data-stu-id="c75fc-110">Remarks</span></span>  
 <span data-ttu-id="c75fc-111">Il `/verbose` opzione consente di visualizzare informazioni sul numero totale di errori generati dal compilatore, segnala gli assembly vengono caricati da un modulo e consente di visualizzare i file sono attualmente in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c75fc-111">The `/verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c75fc-112">Il `/verbose` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="c75fc-112">The `/verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c75fc-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="c75fc-113">Example</span></span>  
 <span data-ttu-id="c75fc-114">Il codice seguente Compila `In.vb` e indica al compilatore di visualizzare informazioni dettagliate sullo stato.</span><span class="sxs-lookup"><span data-stu-id="c75fc-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```  
vbc /verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c75fc-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c75fc-115">See Also</span></span>  
 [<span data-ttu-id="c75fc-116">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c75fc-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c75fc-117">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="c75fc-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
