---
title: -addmodule (opzioni del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /addmodule
dev_langs:
- CSharp
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 79fdad111b1f059e6a3b00e393ea2474f71db947
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="addmodule-c-compiler-options"></a><span data-ttu-id="f8f6b-102">/addmodule (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f8f6b-102">/addmodule (C# Compiler Options)</span></span>
<span data-ttu-id="f8f6b-103">Questa opzione aggiunge un modulo creato con l'opzione target:module nella compilazione in corso.</span><span class="sxs-lookup"><span data-stu-id="f8f6b-103">This option adds a module that was created with the target:module switch to the current compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8f6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8f6b-104">Syntax</span></span>  
  
```console  
/addmodule:file[;file2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f8f6b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f8f6b-105">Arguments</span></span>  
 <span data-ttu-id="f8f6b-106">`file`, `file2`</span><span class="sxs-lookup"><span data-stu-id="f8f6b-106">`file`, `file2`</span></span>  
 <span data-ttu-id="f8f6b-107">Un file di output che contiene i metadati.</span><span class="sxs-lookup"><span data-stu-id="f8f6b-107">An output file that contains metadata.</span></span> <span data-ttu-id="f8f6b-108">Il file non può contenere un manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f8f6b-108">The file cannot contain an assembly manifest.</span></span> <span data-ttu-id="f8f6b-109">Per importare più di un file, separare i nomi dei file con una virgola o con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="f8f6b-109">To import more than one file, separate file names with either a comma or a semicolon.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8f6b-110">Note</span><span class="sxs-lookup"><span data-stu-id="f8f6b-110">Remarks</span></span>  
 <span data-ttu-id="f8f6b-111">Tutti i moduli aggiunti con **/addmodule** devono essere nella stessa directory del file di output in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f8f6b-111">All modules added with **/addmodule** must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="f8f6b-112">Ovvero, è possibile specificare un modulo in una directory in fase di compilazione, ma il modulo deve essere nella directory dell'applicazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f8f6b-112">That is, you can specify a module in any directory at compile time but the module must be in the application directory at run time.</span></span> <span data-ttu-id="f8f6b-113">Se il modulo non è nella directory dell'applicazione in fase di esecuzione, verrà restituita un'eccezione <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="f8f6b-113">If the module is not in the application directory at run time, you will get a <xref:System.TypeLoadException>.</span></span>  
  
 <span data-ttu-id="f8f6b-114">`file` non può contenere un assembly.</span><span class="sxs-lookup"><span data-stu-id="f8f6b-114">`file` cannot contain an assembly.</span></span> <span data-ttu-id="f8f6b-115">Ad esempio, se il file di output è stato creato con [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), i relativi metadati possono essere importati con **/addmodule**.</span><span class="sxs-lookup"><span data-stu-id="f8f6b-115">For example, if the output file was created with [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), its metadata can be imported with **/addmodule**.</span></span>  
  
 <span data-ttu-id="f8f6b-116">Se il file di output è stato creato con un'opzione **/target** e non con un'opzione **/target:module**, i relativi metadati non possono essere importati con l'opzione **/addmodule**, ma con l'opzione [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f8f6b-116">If the output file was created with a **/target** option other than **/target:module**, its metadata cannot be imported with **/addmodule** but can be imported with [/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="f8f6b-117">L'opzione del compilatore non è disponibile in Visual Studio. Un progetto non può fare riferimento a un modulo.</span><span class="sxs-lookup"><span data-stu-id="f8f6b-117">This compiler option is unavailable in Visual Studio; a project cannot reference a module.</span></span> <span data-ttu-id="f8f6b-118">Inoltre, l'opzione del compilatore non può essere modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="f8f6b-118">In addition, this compiler option cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8f6b-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8f6b-119">Example</span></span>  
 <span data-ttu-id="f8f6b-120">Compilare un file di origine `input.cs` e aggiungere i metadati da `metad1.netmodule` e `metad2.netmodule` per creare `out.exe`:</span><span class="sxs-lookup"><span data-stu-id="f8f6b-120">Compile source file `input.cs` and add metadata from `metad1.netmodule` and `metad2.netmodule` to produce `out.exe`:</span></span>  
  
```console  
csc /addmodule:metad1.netmodule;metad2.netmodule /out:out.exe input.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8f6b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8f6b-121">See Also</span></span>  
 <span data-ttu-id="f8f6b-122">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f8f6b-122">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="f8f6b-123">[Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties) </span><span class="sxs-lookup"><span data-stu-id="f8f6b-123">[Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties) </span></span>  
 <span data-ttu-id="f8f6b-124">[Multifile Assemblies](../../../framework/app-domains/multifile-assemblies.md)  (Assembly su più file)</span><span class="sxs-lookup"><span data-stu-id="f8f6b-124">[Multifile Assemblies](../../../framework/app-domains/multifile-assemblies.md) </span></span>  
 [<span data-ttu-id="f8f6b-125">Procedura: Compilare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="f8f6b-125">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)

