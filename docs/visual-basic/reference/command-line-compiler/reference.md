---
title: /Reference (Visual Basic) | Documenti di Microsoft
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
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: 16
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
ms.openlocfilehash: 6870c0b6008124bad18f8eba9207d06e085f2307
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="reference-visual-basic"></a><span data-ttu-id="fdfa2-102">/reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdfa2-102">/reference (Visual Basic)</span></span>
<span data-ttu-id="fdfa2-103">Indica al compilatore di rendere disponibili per il progetto in corso di compilazione informazioni sui tipi negli assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdfa2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fdfa2-104">Syntax</span></span>  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="fdfa2-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="fdfa2-105">Arguments</span></span>  
  
|<span data-ttu-id="fdfa2-106">Termine</span><span class="sxs-lookup"><span data-stu-id="fdfa2-106">Term</span></span>|<span data-ttu-id="fdfa2-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="fdfa2-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="fdfa2-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-108">Required.</span></span> <span data-ttu-id="fdfa2-109">Elenco delimitato da virgole di nomi di file di assembly.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="fdfa2-110">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdfa2-111">Note</span><span class="sxs-lookup"><span data-stu-id="fdfa2-111">Remarks</span></span>  
 <span data-ttu-id="fdfa2-112">I file importati devono contenere i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-112">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="fdfa2-113">Solo i tipi pubblici sono visibili all'esterno dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-113">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="fdfa2-114">Il [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) opzione Importa i metadati da un modulo.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-114">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="fdfa2-115">Se si fa riferimento a un assembly (Assembly a) che a sua volta fa riferimento a un altro assembly (Assembly B), è necessario fare riferimento all'Assembly B se:</span><span class="sxs-lookup"><span data-stu-id="fdfa2-115">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
-   <span data-ttu-id="fdfa2-116">Un tipo da Assembly A eredita da un tipo o implementa un'interfaccia dell'Assembly B.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-116">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="fdfa2-117">Un campo, proprietà, evento o metodo che presenta un tipo di parametro o tipo restituito dall'Assembly B viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-117">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="fdfa2-118">Utilizzare [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) per specificare la directory in cui si trova una o più riferimenti agli assembly.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-118">Use [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="fdfa2-119">Per il compilatore di riconoscere un tipo in un assembly (non un modulo), è necessario imporre la risoluzione del tipo.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-119">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="fdfa2-120">Un esempio di come è possibile farlo consiste nel definire un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-120">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="fdfa2-121">Esistono altri modi risolvere i nomi dei tipi in un assembly per il compilatore.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-121">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="fdfa2-122">Ad esempio, se si eredita da un tipo in un assembly, il nome del tipo quindi diventa noto al compilatore.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-122">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="fdfa2-123">Il file di risposta Vbc. rsp, i riferimenti utilizzati comunemente [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assembly, viene utilizzato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-123">The Vbc.rsp response file, which references commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies, is used by default.</span></span> <span data-ttu-id="fdfa2-124">Utilizzare `/noconfig` se non si desidera al compilatore di utilizzare vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-124">Use `/noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="fdfa2-125">La versione abbreviata di `/reference` è `/r`.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-125">The short form of `/reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdfa2-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="fdfa2-126">Example</span></span>  
 <span data-ttu-id="fdfa2-127">Il seguente codice consente di compilare file di origine è`nput.vb` e fare riferimento agli assembly da M`etad1.dll` e M`etad2.dll` per generare O`ut.exe`.</span><span class="sxs-lookup"><span data-stu-id="fdfa2-127">The following code compiles source file I`nput.vb` and reference assemblies from M`etad1.dll` and M`etad2.dll` to produce O`ut.exe`.</span></span>  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fdfa2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdfa2-128">See Also</span></span>  
 <span data-ttu-id="fdfa2-129">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="fdfa2-129">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="fdfa2-130"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="fdfa2-130"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="fdfa2-131"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="fdfa2-131"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="fdfa2-132"> [Pubblica](../../../visual-basic/language-reference/modifiers/public.md) </span><span class="sxs-lookup"><span data-stu-id="fdfa2-132"> [Public](../../../visual-basic/language-reference/modifiers/public.md) </span></span>  
<span data-ttu-id="fdfa2-133"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="fdfa2-133"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
