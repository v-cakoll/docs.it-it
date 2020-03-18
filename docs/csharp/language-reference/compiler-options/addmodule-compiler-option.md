---
title: -addmodule (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
ms.openlocfilehash: 148a63c37cfbc4c60448adccde10947e91e22bb9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970180"
---
# <a name="-addmodule-c-compiler-options"></a><span data-ttu-id="f964c-102">-addmodule (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f964c-102">-addmodule (C# Compiler Options)</span></span>
<span data-ttu-id="f964c-103">Questa opzione aggiunge un modulo creato con l'opzione target:module nella compilazione in corso.</span><span class="sxs-lookup"><span data-stu-id="f964c-103">This option adds a module that was created with the target:module switch to the current compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f964c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f964c-104">Syntax</span></span>  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f964c-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f964c-105">Arguments</span></span>  
 <span data-ttu-id="f964c-106">`file`, `file2`</span><span class="sxs-lookup"><span data-stu-id="f964c-106">`file`, `file2`</span></span>  
 <span data-ttu-id="f964c-107">Un file di output che contiene i metadati.</span><span class="sxs-lookup"><span data-stu-id="f964c-107">An output file that contains metadata.</span></span> <span data-ttu-id="f964c-108">Il file non può contenere un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f964c-108">The file cannot contain an assembly manifest.</span></span> <span data-ttu-id="f964c-109">Per importare più di un file, separare i nomi dei file con una virgola o con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="f964c-109">To import more than one file, separate file names with either a comma or a semicolon.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f964c-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f964c-110">Remarks</span></span>  
 <span data-ttu-id="f964c-111">In fase di esecuzione tutti i moduli aggiunti con **-addmodule** devono essere nella stessa directory del file di output.</span><span class="sxs-lookup"><span data-stu-id="f964c-111">All modules added with **-addmodule** must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="f964c-112">Ovvero, è possibile specificare un modulo in una directory in fase di compilazione, ma il modulo deve essere nella directory dell'applicazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f964c-112">That is, you can specify a module in any directory at compile time but the module must be in the application directory at run time.</span></span> <span data-ttu-id="f964c-113">Se il modulo non è nella directory dell'applicazione in fase di esecuzione, verrà restituita un'eccezione <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="f964c-113">If the module is not in the application directory at run time, you will get a <xref:System.TypeLoadException>.</span></span>  
  
 <span data-ttu-id="f964c-114">`file` non può contenere un assembly.</span><span class="sxs-lookup"><span data-stu-id="f964c-114">`file` cannot contain an assembly.</span></span> <span data-ttu-id="f964c-115">Ad esempio, se il file di output è stato creato con [-target:module](./target-module-compiler-option.md), i relativi metadati possono essere importati con **-addmodule**.</span><span class="sxs-lookup"><span data-stu-id="f964c-115">For example, if the output file was created with [-target:module](./target-module-compiler-option.md), its metadata can be imported with **-addmodule**.</span></span>  
  
 <span data-ttu-id="f964c-116">Se il file di output è stato creato con un'opzione **-target** diversa da **-target:module**, i relativi metadati non possono essere importati con l'opzione **-addmodule**, ma possono essere impostati con l'opzione [-reference](./reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f964c-116">If the output file was created with a **-target** option other than **-target:module**, its metadata cannot be imported with **-addmodule** but can be imported with [-reference](./reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="f964c-117">L'opzione del compilatore non è disponibile in Visual Studio. Un progetto non può fare riferimento a un modulo.</span><span class="sxs-lookup"><span data-stu-id="f964c-117">This compiler option is unavailable in Visual Studio; a project cannot reference a module.</span></span> <span data-ttu-id="f964c-118">Inoltre, l'opzione del compilatore non può essere modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="f964c-118">In addition, this compiler option cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f964c-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="f964c-119">Example</span></span>  
 <span data-ttu-id="f964c-120">Compilare un file di origine `input.cs` e aggiungere i metadati da `metad1.netmodule` e `metad2.netmodule` per creare `out.exe`:</span><span class="sxs-lookup"><span data-stu-id="f964c-120">Compile source file `input.cs` and add metadata from `metad1.netmodule` and `metad2.netmodule` to produce `out.exe`:</span></span>  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="f964c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f964c-121">See also</span></span>

- [<span data-ttu-id="f964c-122">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="f964c-122">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="f964c-123">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="f964c-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="f964c-124">Assiemi multifile</span><span class="sxs-lookup"><span data-stu-id="f964c-124">Multifile Assemblies</span></span>](../../../framework/app-domains/multifile-assemblies.md)
- [<span data-ttu-id="f964c-125">Procedura: Compilare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="f964c-125">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
