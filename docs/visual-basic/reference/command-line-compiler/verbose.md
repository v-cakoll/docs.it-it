---
title: l&quot;opzione /verbose | Documenti di Microsoft
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
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
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
ms.openlocfilehash: 62285a727217aa897a83a9e746588c80a2c519c0
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="verbose"></a><span data-ttu-id="1e380-102">/verbose</span><span class="sxs-lookup"><span data-stu-id="1e380-102">/verbose</span></span>
<span data-ttu-id="1e380-103">Indica al compilatore di generare messaggi di stato e di errore dettagliati.</span><span class="sxs-lookup"><span data-stu-id="1e380-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e380-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e380-104">Syntax</span></span>  
  
```  
/verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1e380-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1e380-105">Arguments</span></span>  
 <span data-ttu-id="1e380-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="1e380-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="1e380-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1e380-107">Optional.</span></span> <span data-ttu-id="1e380-108">Specifica di `/verbose` equivale a specificare `/verbose+`, che indica al compilatore di messaggi dettagliati.</span><span class="sxs-lookup"><span data-stu-id="1e380-108">Specifying `/verbose` is the same as specifying `/verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="1e380-109">Il valore predefinito per questa opzione è `/verbose-`.</span><span class="sxs-lookup"><span data-stu-id="1e380-109">The default for this option is `/verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e380-110">Note</span><span class="sxs-lookup"><span data-stu-id="1e380-110">Remarks</span></span>  
 <span data-ttu-id="1e380-111">Il `/verbose` opzione Visualizza informazioni sul numero totale di errori generati dal compilatore, sugli assembly che vengono caricati da un modulo e quali file sono attualmente in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="1e380-111">The `/verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e380-112">Il `/verbose` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="1e380-112">The `/verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e380-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="1e380-113">Example</span></span>  
 <span data-ttu-id="1e380-114">Il codice seguente Compila `In.vb` e indica al compilatore di visualizzare informazioni dettagliate sullo stato.</span><span class="sxs-lookup"><span data-stu-id="1e380-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```  
vbc /verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e380-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e380-115">See Also</span></span>  
 <span data-ttu-id="1e380-116">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="1e380-116">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="1e380-117"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="1e380-117"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
