---
title: -reference
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 35e02d1ad4409e754c2466f7d0ae7e68214772e6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716696"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="0b6d6-102">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b6d6-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="0b6d6-103">Fa in modo che il compilatore renda le informazioni sul tipo negli assembly specificati disponibili per il progetto attualmente in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b6d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b6d6-104">Syntax</span></span>  
  
```console  
-reference:fileList  
```

<span data-ttu-id="0b6d6-105">oppure</span><span class="sxs-lookup"><span data-stu-id="0b6d6-105">or</span></span>

```console
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="0b6d6-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0b6d6-106">Arguments</span></span>  
  
|<span data-ttu-id="0b6d6-107">Termine</span><span class="sxs-lookup"><span data-stu-id="0b6d6-107">Term</span></span>|<span data-ttu-id="0b6d6-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="0b6d6-108">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="0b6d6-109">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-109">Required.</span></span> <span data-ttu-id="0b6d6-110">Elenco di nomi di file di assembly delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-110">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="0b6d6-111">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-111">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b6d6-112">Note</span><span class="sxs-lookup"><span data-stu-id="0b6d6-112">Remarks</span></span>  
 <span data-ttu-id="0b6d6-113">I file importati devono contenere i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-113">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="0b6d6-114">Solo i tipi pubblici sono visibili all'esterno dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-114">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="0b6d6-115">L'opzione [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) importa i metadati da un modulo.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-115">The [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="0b6d6-116">Se si fa riferimento a un assembly (assembly A) che a sua volta fa riferimento a un altro assembly (assembly B), è necessario fare riferimento all'assembly B se:</span><span class="sxs-lookup"><span data-stu-id="0b6d6-116">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="0b6d6-117">Un tipo dell'assembly A eredita da un tipo o implementa un'interfaccia dall'assembly B.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-117">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="0b6d6-118">Viene richiamato un campo, una proprietà, un evento o un metodo che presenta un tipo restituito o un tipo di parametro proveniente dall'assembly B.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-118">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="0b6d6-119">Usare [-LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) per specificare la directory in cui si trova uno o più riferimenti ad assembly.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-119">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="0b6d6-120">Affinché il compilatore riconosca un tipo in un assembly (non un modulo), è necessario forzare la risoluzione del tipo.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-120">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="0b6d6-121">Un esempio di come è possibile eseguire questa operazione consiste nel definire un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-121">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="0b6d6-122">Sono disponibili altri modi per risolvere i nomi dei tipi in un assembly per il compilatore.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-122">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="0b6d6-123">Se, ad esempio, si eredita da un tipo in un assembly, il nome del tipo diventa noto al compilatore.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-123">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="0b6d6-124">Per impostazione predefinita, viene usato il file di risposta vbc. rsp, che fa riferimento a assembly .NET Framework di uso comune.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-124">The Vbc.rsp response file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="0b6d6-125">Usare `-noconfig` se non si vuole che il compilatore usi vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-125">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="0b6d6-126">La forma breve di `-reference` è `-r`.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-126">The short form of `-reference` is `-r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b6d6-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="0b6d6-127">Example</span></span>  
 <span data-ttu-id="0b6d6-128">Il comando seguente compila `Input.vb` di file di origine e gli assembly di riferimento da `Metad1.dll` e `Metad2.dll` per produrre `Out.exe`.</span><span class="sxs-lookup"><span data-stu-id="0b6d6-128">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b6d6-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b6d6-129">See also</span></span>

- [<span data-ttu-id="0b6d6-130">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0b6d6-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="0b6d6-131">-noconfig</span><span class="sxs-lookup"><span data-stu-id="0b6d6-131">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="0b6d6-132">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b6d6-132">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="0b6d6-133">Public</span><span class="sxs-lookup"><span data-stu-id="0b6d6-133">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="0b6d6-134">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="0b6d6-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
