---
title: -riferimenti (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 2394a23ddd59d09ce53c78fc4486fc5bae9e8516
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583364"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="7514d-102">-riferimenti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7514d-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="7514d-103">Indica al compilatore di rendere disponibili per il progetto in corso di compilazione informazioni sui tipi negli assembly specificati.</span><span class="sxs-lookup"><span data-stu-id="7514d-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7514d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7514d-104">Syntax</span></span>  
  
```  
-reference:fileList  
' -or-  
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="7514d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7514d-105">Arguments</span></span>  
  
|<span data-ttu-id="7514d-106">Termine</span><span class="sxs-lookup"><span data-stu-id="7514d-106">Term</span></span>|<span data-ttu-id="7514d-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="7514d-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="7514d-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7514d-108">Required.</span></span> <span data-ttu-id="7514d-109">Elenco di nomi di file di assembly delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="7514d-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="7514d-110">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="7514d-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7514d-111">Note</span><span class="sxs-lookup"><span data-stu-id="7514d-111">Remarks</span></span>  
 <span data-ttu-id="7514d-112">I file importati devono contenere i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="7514d-112">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="7514d-113">Solo i tipi pubblici sono visibili all'esterno dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="7514d-113">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="7514d-114">Il [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) opzione Importa i metadati da un modulo.</span><span class="sxs-lookup"><span data-stu-id="7514d-114">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="7514d-115">Se si fa riferimento a un assembly (Assembly A) che a sua volta fa riferimento a un altro assembly (Assembly B), è necessario fare riferimento all'Assembly B se:</span><span class="sxs-lookup"><span data-stu-id="7514d-115">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="7514d-116">Un tipo dell'assembly A eredita da un tipo o implementa un'interfaccia dall'assembly B.</span><span class="sxs-lookup"><span data-stu-id="7514d-116">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="7514d-117">Viene richiamato un campo, una proprietà, un evento o un metodo che presenta un tipo restituito o un tipo di parametro proveniente dall'assembly B.</span><span class="sxs-lookup"><span data-stu-id="7514d-117">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="7514d-118">Uso [- libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) per specificare la directory in cui si trovano uno o più riferimenti agli assembly.</span><span class="sxs-lookup"><span data-stu-id="7514d-118">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="7514d-119">Per il compilatore di riconoscere un tipo in un assembly (non un modulo), è necessario imporre la risoluzione del tipo.</span><span class="sxs-lookup"><span data-stu-id="7514d-119">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="7514d-120">Un esempio di come è possibile eseguire questa operazione consiste nel definire un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="7514d-120">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="7514d-121">Esistono altri modi risolvere i nomi dei tipi in un assembly per consentire al compilatore.</span><span class="sxs-lookup"><span data-stu-id="7514d-121">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="7514d-122">Ad esempio, se si eredita da un tipo in un assembly, il nome del tipo quindi diventa noto al compilatore.</span><span class="sxs-lookup"><span data-stu-id="7514d-122">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="7514d-123">Il file di risposta Vbc. rsp, che fa riferimento agli assembly di .NET Framework comunemente utilizzati, viene usato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7514d-123">The Vbc.rsp response file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="7514d-124">Usare `-noconfig` se non si desidera al compilatore di utilizzare vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="7514d-124">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="7514d-125">La forma breve di `-reference` è `/r`.</span><span class="sxs-lookup"><span data-stu-id="7514d-125">The short form of `-reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7514d-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="7514d-126">Example</span></span>  
 <span data-ttu-id="7514d-127">Il comando seguente consente di compilare file di origine `Input.vb` e fare riferimento agli assembly da `Metad1.dll` e `Metad2.dll` produrre `Out.exe`.</span><span class="sxs-lookup"><span data-stu-id="7514d-127">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7514d-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7514d-128">See also</span></span>

- [<span data-ttu-id="7514d-129">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7514d-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7514d-130">-noconfig</span><span class="sxs-lookup"><span data-stu-id="7514d-130">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="7514d-131">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7514d-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="7514d-132">Public</span><span class="sxs-lookup"><span data-stu-id="7514d-132">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="7514d-133">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="7514d-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
