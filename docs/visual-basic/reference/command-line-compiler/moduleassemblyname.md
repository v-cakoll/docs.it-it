---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8b579c2c3ae22469706326ee17109b8e39dab60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650790"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="ff538-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="ff538-102">-moduleassemblyname</span></span>
<span data-ttu-id="ff538-103">Specifica il nome dell'assembly di cui fa parte il modulo.</span><span class="sxs-lookup"><span data-stu-id="ff538-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff538-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff538-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="ff538-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ff538-105">Arguments</span></span>  
  
|<span data-ttu-id="ff538-106">Termine</span><span class="sxs-lookup"><span data-stu-id="ff538-106">Term</span></span>|<span data-ttu-id="ff538-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="ff538-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="ff538-108">Il nome dell'assembly che farà parte questo modulo.</span><span class="sxs-lookup"><span data-stu-id="ff538-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff538-109">Note</span><span class="sxs-lookup"><span data-stu-id="ff538-109">Remarks</span></span>  
 <span data-ttu-id="ff538-110">Il compilatore elabora il `-moduleassemblyname` solo se opzione il `-target:module` è stata specificata l'opzione.</span><span class="sxs-lookup"><span data-stu-id="ff538-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="ff538-111">In questo modo il compilatore di creare un modulo.</span><span class="sxs-lookup"><span data-stu-id="ff538-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="ff538-112">Il modulo creato dal compilatore è valido solo per l'assembly specificato con il `-moduleassemblyname` opzione.</span><span class="sxs-lookup"><span data-stu-id="ff538-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="ff538-113">Se si inserisce il modulo in un assembly diverso, si verificheranno errori di runtime.</span><span class="sxs-lookup"><span data-stu-id="ff538-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="ff538-114">Il `-moduleassemblyname` opzione è necessaria solo quando vengono soddisfatte le seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff538-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
-   <span data-ttu-id="ff538-115">Un tipo di dati del modulo deve accedere a un `Friend` tipo in un assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="ff538-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
-   <span data-ttu-id="ff538-116">L'assembly di riferimento ha concesso l'accesso all'assembly friend all'assembly in cui il modulo verrà compilato.</span><span class="sxs-lookup"><span data-stu-id="ff538-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="ff538-117">Per ulteriori informazioni sulla creazione di un modulo, vedere [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="ff538-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="ff538-118">Per ulteriori informazioni sugli assembly friend, vedere [assembly Friend](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span><span class="sxs-lookup"><span data-stu-id="ff538-118">For more information about friend assemblies, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff538-119">Il `-moduleassemblyname` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo quando esegue la compilazione da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="ff538-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff538-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff538-120">See Also</span></span>  
 [<span data-ttu-id="ff538-121">Procedura: Compilare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="ff538-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="ff538-122">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff538-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="ff538-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff538-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="ff538-124">-main</span><span class="sxs-lookup"><span data-stu-id="ff538-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)  
 [<span data-ttu-id="ff538-125">-riferimenti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff538-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="ff538-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="ff538-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [<span data-ttu-id="ff538-127">Assembly e Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="ff538-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="ff538-128">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="ff538-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="ff538-129">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="ff538-129">Friend Assemblies</span></span>](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)
