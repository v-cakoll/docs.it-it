---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: a612a68cffd927f3e360406cca6d9daae4f66c86
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775629"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="9a37d-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="9a37d-102">-moduleassemblyname</span></span>
<span data-ttu-id="9a37d-103">Specifica il nome dell'assembly di cui fa parte il modulo.</span><span class="sxs-lookup"><span data-stu-id="9a37d-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a37d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a37d-104">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="9a37d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9a37d-105">Arguments</span></span>  
  
|<span data-ttu-id="9a37d-106">Termine</span><span class="sxs-lookup"><span data-stu-id="9a37d-106">Term</span></span>|<span data-ttu-id="9a37d-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="9a37d-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="9a37d-108">Nome dell'assembly di cui questo modulo farà parte.</span><span class="sxs-lookup"><span data-stu-id="9a37d-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a37d-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9a37d-109">Remarks</span></span>  
 <span data-ttu-id="9a37d-110">Il compilatore elabora l' `-moduleassemblyname` opzione solo se è `-target:module` stata specificata l'opzione.</span><span class="sxs-lookup"><span data-stu-id="9a37d-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="9a37d-111">In questo modo il compilatore crea un modulo.</span><span class="sxs-lookup"><span data-stu-id="9a37d-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="9a37d-112">Il modulo creato dal compilatore è valido solo per l'assembly specificato con l' `-moduleassemblyname` opzione.</span><span class="sxs-lookup"><span data-stu-id="9a37d-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="9a37d-113">Se si inserisce il modulo in un assembly diverso, si verificheranno errori di run-time.</span><span class="sxs-lookup"><span data-stu-id="9a37d-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="9a37d-114">L' `-moduleassemblyname` opzione è necessaria solo quando sono soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a37d-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="9a37d-115">Un tipo di dati nel modulo deve accedere a un `Friend` tipo in un assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="9a37d-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="9a37d-116">L'assembly a cui si fa riferimento ha concesso l'accesso dell'assembly Friend all'assembly in cui verrà compilato il modulo.</span><span class="sxs-lookup"><span data-stu-id="9a37d-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="9a37d-117">Per ulteriori informazioni sulla creazione di un modulo, vedere [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="9a37d-117">For more information about creating a module, see [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="9a37d-118">Per ulteriori informazioni sugli assembly Friend, vedere [assembly Friend](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="9a37d-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9a37d-119">L' `-moduleassemblyname` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si compila da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9a37d-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a37d-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="9a37d-120">See also</span></span>

- [<span data-ttu-id="9a37d-121">Procedura: compilare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="9a37d-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="9a37d-122">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9a37d-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9a37d-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a37d-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="9a37d-124">-main</span><span class="sxs-lookup"><span data-stu-id="9a37d-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="9a37d-125">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a37d-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="9a37d-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="9a37d-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="9a37d-127">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="9a37d-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="9a37d-128">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="9a37d-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="9a37d-129">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="9a37d-129">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
