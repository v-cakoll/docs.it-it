---
title: -highentropyva (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /highentropyva
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
ms.openlocfilehash: b710bb829f6a7591159d2f2e6bacc670d21c42d1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69606854"
---
# <a name="-highentropyva-c-compiler-options"></a><span data-ttu-id="f3ab8-102">-highentropyva (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f3ab8-102">-highentropyva (C# Compiler Options)</span></span>
<span data-ttu-id="f3ab8-103">L'opzione del compilatore **-highentropyva** indica al kernel di Windows se un particolare eseguibile supporta la funzionalità ASLR (Address Space Layout Randomization) a entropia elevata.</span><span class="sxs-lookup"><span data-stu-id="f3ab8-103">The **-highentropyva** compiler option tells the Windows kernel whether a particular executable supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3ab8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3ab8-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f3ab8-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f3ab8-105">Arguments</span></span>  
 <span data-ttu-id="f3ab8-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="f3ab8-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="f3ab8-107">Questa opzione consente di specificare che un eseguibile a 64 bit o un eseguibile contrassegnato dall'opzione del compilatore [-platform:anycpu](./platform-compiler-option.md) supporta uno spazio indirizzi virtuali a entropia elevata.</span><span class="sxs-lookup"><span data-stu-id="f3ab8-107">This option specifies that a 64-bit executable or an executable that is marked by the [-platform:anycpu](./platform-compiler-option.md) compiler option supports a high entropy virtual address space.</span></span> <span data-ttu-id="f3ab8-108">L'opzione è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f3ab8-108">The option is disabled by default.</span></span> <span data-ttu-id="f3ab8-109">Per abilitarla, usare **-highentropyva+** o **-highentropyva**.</span><span class="sxs-lookup"><span data-stu-id="f3ab8-109">Use **-highentropyva+** or **-highentropyva** to enable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3ab8-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f3ab8-110">Remarks</span></span>  
 <span data-ttu-id="f3ab8-111">Con l'opzione **-highentropyva**, nelle versioni compatibili del kernel di Windows è possibile usare livelli di entropia più elevati per la scelta casuale del layout dello spazio degli indirizzi di un processo in quanto parte di ASLR.</span><span class="sxs-lookup"><span data-stu-id="f3ab8-111">The **-highentropyva** option enables compatible versions of the Windows kernel to use higher degrees of entropy when randomizing the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="f3ab8-112">L'utilizzo di livelli più elevati di entropia indica la possibilità di allocare un numero maggiore di indirizzi ad aree della memoria quali stack e heap.</span><span class="sxs-lookup"><span data-stu-id="f3ab8-112">Using higher degrees of entropy means that a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="f3ab8-113">Di conseguenza, è più difficile indovinare la posizione di una determinata area di memoria.</span><span class="sxs-lookup"><span data-stu-id="f3ab8-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="f3ab8-114">Quando l'opzione del compilatore **-highentropyva** è specificata, l'eseguibile di destinazione e tutti i moduli da cui dipende devono essere in grado di gestire valori di puntatore maggiori di 4 gigabyte (GB), quando sono in esecuzione come processi a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="f3ab8-114">When the **-highentropyva** compiler option is specified, the target executable and any modules that it depends on must be able to handle pointer values that are larger than 4 gigabytes (GB) when they are running as a 64-bit process.</span></span>
