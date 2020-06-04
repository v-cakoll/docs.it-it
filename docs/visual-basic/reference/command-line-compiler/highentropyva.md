---
title: -highentropyva
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 9501ea46eb13baa171208e20d0c9645d118c4301
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408621"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="9e50b-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e50b-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="9e50b-103">Indica se un eseguibile a 64 bit o un eseguibile contrassegnato dall'opzione del compilatore [-Platform: anycpu](platform.md) supporta la sequenza casuale del layout dello spazio degli indirizzi a entropia elevata (ASLR).</span><span class="sxs-lookup"><span data-stu-id="9e50b-103">Indicates whether a 64-bit executable or an executable that's marked by the [-platform:anycpu](platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e50b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e50b-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9e50b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9e50b-105">Arguments</span></span>  
 <span data-ttu-id="9e50b-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="9e50b-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="9e50b-107">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="9e50b-107">Optional.</span></span> <span data-ttu-id="9e50b-108">L'opzione è disattivata per impostazione predefinita o se si specifica `-highentropyva-` .</span><span class="sxs-lookup"><span data-stu-id="9e50b-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="9e50b-109">L'opzione è attiva se si specifica `-highentropyva` o `-highentropyva+` .</span><span class="sxs-lookup"><span data-stu-id="9e50b-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e50b-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="9e50b-110">Remarks</span></span>  
 <span data-ttu-id="9e50b-111">Se si specifica questa opzione, le versioni compatibili del kernel di Windows possono usare livelli di entropia più elevati quando il kernel esegue in modo casuale il layout dello spazio degli indirizzi di un processo come parte di ASLR.</span><span class="sxs-lookup"><span data-stu-id="9e50b-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="9e50b-112">Se il kernel usa livelli di entropia più elevati, è possibile allocare un numero maggiore di indirizzi alle aree di memoria quali stack e heap.</span><span class="sxs-lookup"><span data-stu-id="9e50b-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="9e50b-113">Di conseguenza, è più difficile indovinare la posizione di una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="9e50b-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="9e50b-114">Quando l'opzione è impostata su on, l'eseguibile di destinazione e tutti i moduli da cui dipende devono essere in grado di gestire valori di puntatore maggiori di 4 gigabyte (GB) quando tali moduli sono in esecuzione come processi a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="9e50b-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e50b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e50b-115">See also</span></span>

- [<span data-ttu-id="9e50b-116">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e50b-116">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="9e50b-117">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="9e50b-117">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
