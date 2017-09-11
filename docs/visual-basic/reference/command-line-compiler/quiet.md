---
title: /quiet | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /quiet
- quiet
dev_langs:
- VB
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
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
ms.openlocfilehash: bc21be8982fea52bf25d0bedeec2b78eee1e705f
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="quiet"></a><span data-ttu-id="33b00-102">/quiet</span><span class="sxs-lookup"><span data-stu-id="33b00-102">/quiet</span></span>
<span data-ttu-id="33b00-103">Impedisce al compilatore di visualizzare codice per avvisi ed errori relativi alla sintassi.</span><span class="sxs-lookup"><span data-stu-id="33b00-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33b00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33b00-104">Syntax</span></span>  
  
```  
/quiet  
```  
  
## <a name="remarks"></a><span data-ttu-id="33b00-105">Note</span><span class="sxs-lookup"><span data-stu-id="33b00-105">Remarks</span></span>  
 <span data-ttu-id="33b00-106">Per impostazione predefinita, l'opzione `/quiet` non è attiva.</span><span class="sxs-lookup"><span data-stu-id="33b00-106">By default, `/quiet` is not in effect.</span></span> <span data-ttu-id="33b00-107">Quando il compilatore segnala un errore di sintassi o un avviso, viene visualizzata anche la riga del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="33b00-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="33b00-108">Per le applicazioni che analizzano l'output del compilatore, potrebbe essere più utile per il compilatore di generare solo il testo della diagnostica.</span><span class="sxs-lookup"><span data-stu-id="33b00-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>  
  
 <span data-ttu-id="33b00-109">Nell'esempio seguente, `Module1` genera un errore che include il codice sorgente se compilato senza `/quiet`.</span><span class="sxs-lookup"><span data-stu-id="33b00-109">In the following example, `Module1` outputs an error that includes source code when compiled without `/quiet`.</span></span>  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="33b00-110">Output:</span><span class="sxs-lookup"><span data-stu-id="33b00-110">Output:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 <span data-ttu-id="33b00-111">Compilato con `/quiet`, il compilatore restituisce solo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33b00-111">Compiled with `/quiet`, the compiler outputs only the following:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  <span data-ttu-id="33b00-112">Il `/quiet` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="33b00-112">The `/quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33b00-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="33b00-113">Example</span></span>  
 <span data-ttu-id="33b00-114">Il codice seguente Compila `T2.vb` e non visualizzare il codice per diagnostica relativa alla sintassi:</span><span class="sxs-lookup"><span data-stu-id="33b00-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>  
  
```  
vbc /quiet t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="33b00-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33b00-115">See Also</span></span>  
 <span data-ttu-id="33b00-116">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="33b00-116">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="33b00-117"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="33b00-117"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
