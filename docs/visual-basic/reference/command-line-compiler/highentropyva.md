---
title: /highentropyva (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: 12
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
ms.openlocfilehash: ef482f142e07e96eabf93bd2223b0d24f351553b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="highentropyva-visual-basic"></a><span data-ttu-id="155a4-102">/highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="155a4-102">/highentropyva (Visual Basic)</span></span>
<span data-ttu-id="155a4-103">Indica se un eseguibile a 64 bit o che è contrassegnato per la [/platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) l'opzione del compilatore supporta un'entropia elevata Address Space Layout Randomization (ASLR).</span><span class="sxs-lookup"><span data-stu-id="155a4-103">Indicates whether a 64-bit executable or an executable that's marked by the [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="155a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="155a4-104">Syntax</span></span>  
  
```  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="155a4-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="155a4-105">Arguments</span></span>  
 <span data-ttu-id="155a4-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="155a4-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="155a4-107">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="155a4-107">Optional.</span></span> <span data-ttu-id="155a4-108">L'opzione è disattivata per impostazione predefinita o se si specifica `/highentropyva-`.</span><span class="sxs-lookup"><span data-stu-id="155a4-108">The option is off by default or if you specify `/highentropyva-`.</span></span> <span data-ttu-id="155a4-109">L'opzione è abilitata se si specifica `/highentropyva` o `/highentropyva+`.</span><span class="sxs-lookup"><span data-stu-id="155a4-109">The option is on if you specify `/highentropyva` or `/highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="155a4-110">Note</span><span class="sxs-lookup"><span data-stu-id="155a4-110">Remarks</span></span>  
 <span data-ttu-id="155a4-111">Se si specifica questa opzione, versioni compatibili del kernel di Windows possono utilizzare livelli più elevati di entropia quando il kernel genera casualmente del layout dello spazio di indirizzi di un processo come parte di ASLR.</span><span class="sxs-lookup"><span data-stu-id="155a4-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="155a4-112">Se il kernel utilizza livelli più elevati di entropia, un numero maggiore di indirizzi da allocare aree della memoria quali stack e heap.</span><span class="sxs-lookup"><span data-stu-id="155a4-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="155a4-113">Di conseguenza, è più difficile indovinare la posizione di una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="155a4-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="155a4-114">Quando l'opzione è on, l'eseguibile di destinazione e tutti i moduli in cui esso dipende deve essere in grado di gestire i valori di puntatore sono maggiori di 4 gigabyte (GB) quando questi moduli vengono eseguiti come processi a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="155a4-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="155a4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="155a4-115">See Also</span></span>  
 <span data-ttu-id="155a4-116">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="155a4-116">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="155a4-117"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="155a4-117"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
