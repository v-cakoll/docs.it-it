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
ms.openlocfilehash: 633b457106203e213f5d30003e576b7e8132f4d2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400487"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="ea743-102">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea743-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="ea743-103">Fa in modo che il compilatore renda le informazioni sul tipo negli assembly specificati disponibili per il progetto attualmente in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="ea743-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea743-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea743-104">Syntax</span></span>  
  
```console  
-reference:fileList  
```

<span data-ttu-id="ea743-105">Oppure</span><span class="sxs-lookup"><span data-stu-id="ea743-105">or</span></span>

```console
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="ea743-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ea743-106">Arguments</span></span>  
  
|<span data-ttu-id="ea743-107">Termine</span><span class="sxs-lookup"><span data-stu-id="ea743-107">Term</span></span>|<span data-ttu-id="ea743-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="ea743-108">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="ea743-109">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="ea743-109">Required.</span></span> <span data-ttu-id="ea743-110">Elenco di nomi di file di assembly delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="ea743-110">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="ea743-111">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="ea743-111">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea743-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="ea743-112">Remarks</span></span>  
 <span data-ttu-id="ea743-113">I file importati devono contenere i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ea743-113">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="ea743-114">Solo i tipi pubblici sono visibili all'esterno dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ea743-114">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="ea743-115">L'opzione [-addmodule](addmodule.md) importa i metadati da un modulo.</span><span class="sxs-lookup"><span data-stu-id="ea743-115">The [-addmodule](addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="ea743-116">Se si fa riferimento a un assembly (assembly A) che a sua volta fa riferimento a un altro assembly (assembly B), è necessario fare riferimento all'assembly B se:</span><span class="sxs-lookup"><span data-stu-id="ea743-116">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
- <span data-ttu-id="ea743-117">Un tipo dell'assembly A eredita da un tipo o implementa un'interfaccia dall'assembly B.</span><span class="sxs-lookup"><span data-stu-id="ea743-117">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
- <span data-ttu-id="ea743-118">Viene richiamato un campo, una proprietà, un evento o un metodo che presenta un tipo restituito o un tipo di parametro proveniente dall'assembly B.</span><span class="sxs-lookup"><span data-stu-id="ea743-118">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="ea743-119">Usare [-LIBPATH](libpath.md) per specificare la directory in cui si trova uno o più riferimenti ad assembly.</span><span class="sxs-lookup"><span data-stu-id="ea743-119">Use [-libpath](libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="ea743-120">Affinché il compilatore riconosca un tipo in un assembly (non un modulo), è necessario forzare la risoluzione del tipo.</span><span class="sxs-lookup"><span data-stu-id="ea743-120">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="ea743-121">Un esempio di come è possibile eseguire questa operazione consiste nel definire un'istanza del tipo.</span><span class="sxs-lookup"><span data-stu-id="ea743-121">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="ea743-122">Sono disponibili altri modi per risolvere i nomi dei tipi in un assembly per il compilatore.</span><span class="sxs-lookup"><span data-stu-id="ea743-122">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="ea743-123">Se, ad esempio, si eredita da un tipo in un assembly, il nome del tipo diventa noto al compilatore.</span><span class="sxs-lookup"><span data-stu-id="ea743-123">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="ea743-124">Per impostazione predefinita, viene usato il file di risposta vbc. rsp, che fa riferimento a assembly .NET Framework di uso comune.</span><span class="sxs-lookup"><span data-stu-id="ea743-124">The Vbc.rsp response file, which references commonly used .NET Framework assemblies, is used by default.</span></span> <span data-ttu-id="ea743-125">Usare `-noconfig` se non si vuole che il compilatore usi vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="ea743-125">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="ea743-126">La forma breve di `-reference` è `-r`.</span><span class="sxs-lookup"><span data-stu-id="ea743-126">The short form of `-reference` is `-r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea743-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="ea743-127">Example</span></span>  
 <span data-ttu-id="ea743-128">Il comando seguente compila il file di origine `Input.vb` e gli assembly di riferimento da `Metad1.dll` e `Metad2.dll` per produrre `Out.exe` .</span><span class="sxs-lookup"><span data-stu-id="ea743-128">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea743-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ea743-129">See also</span></span>

- [<span data-ttu-id="ea743-130">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea743-130">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="ea743-131">-noconfig</span><span class="sxs-lookup"><span data-stu-id="ea743-131">-noconfig</span></span>](noconfig.md)
- [<span data-ttu-id="ea743-132">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea743-132">-target (Visual Basic)</span></span>](target.md)
- [<span data-ttu-id="ea743-133">Pubblica</span><span class="sxs-lookup"><span data-stu-id="ea743-133">Public</span></span>](../../language-reference/modifiers/public.md)
- [<span data-ttu-id="ea743-134">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="ea743-134">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
