---
title: -out (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /out
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
ms.openlocfilehash: 6c8408c0c613e361dae0c1db19f854e9421ca467
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970371"
---
# <a name="-out-c-compiler-options"></a><span data-ttu-id="79c91-102">-out (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="79c91-102">-out (C# Compiler Options)</span></span>
<span data-ttu-id="79c91-103">L'opzione **-out** specifica il nome del file di output.</span><span class="sxs-lookup"><span data-stu-id="79c91-103">The **-out** option specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79c91-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79c91-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="79c91-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="79c91-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="79c91-106">Il nome del file di output creato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="79c91-106">The name of the output file created by the compiler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79c91-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="79c91-107">Remarks</span></span>  
 <span data-ttu-id="79c91-108">Nella riga di comando è possibile specificare più file di output per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="79c91-108">On the command line, it is possible to specify multiple output files for your compilation.</span></span> <span data-ttu-id="79c91-109">Dopo l'opzione **-out** è prevista la presenza di uno o più file di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="79c91-109">The compiler expects to find one or more source code files following the **-out** option.</span></span> <span data-ttu-id="79c91-110">Tutti i file di codice sorgente verranno quindi compilati nel file di output specificato con l'opzione **-out**.</span><span class="sxs-lookup"><span data-stu-id="79c91-110">Then, all source code files will be compiled into the output file specified by that **-out** option.</span></span>  
  
 <span data-ttu-id="79c91-111">Specificare il nome completo e l'estensione del file che si vuole creare.</span><span class="sxs-lookup"><span data-stu-id="79c91-111">Specify the full name and extension of the file you want to create.</span></span>  
  
 <span data-ttu-id="79c91-112">Se non si specifica il nome del file di output:</span><span class="sxs-lookup"><span data-stu-id="79c91-112">If you do not specify the name of the output file:</span></span>  
  
- <span data-ttu-id="79c91-113">Un file con estensione exe corrisponderà al nome del file di codice sorgente che contiene il metodo **Main**.</span><span class="sxs-lookup"><span data-stu-id="79c91-113">An .exe will take its name from the source code file that contains the **Main** method.</span></span>  
  
- <span data-ttu-id="79c91-114">Un file con estensione dll o netmodule corrisponderà al nome del primo file di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="79c91-114">A .dll or .netmodule will take its name from the first source code file.</span></span>  
  
 <span data-ttu-id="79c91-115">Non è possibile usare per la compilazione di un file di output un file di codice sorgente già usato per compilare un altro file di output nella stessa compilazione.</span><span class="sxs-lookup"><span data-stu-id="79c91-115">A source code file used to compile one output file cannot be used in the same compilation for the compilation of another output file.</span></span>  
  
 <span data-ttu-id="79c91-116">Quando si generano più file di output in una compilazione da riga di comando, tenere presente che solo uno dei file di output può essere un assembly e che l'assembly può essere solo il primo file di output specificato (in modo implicito o esplicito con l'opzione **-out**).</span><span class="sxs-lookup"><span data-stu-id="79c91-116">When producing multiple output files in a command-line compilation, keep in mind that only one of the output files can be an assembly and that only the first output file specified (implicitly or explicitly with **-out**) can be the assembly.</span></span>  
  
 <span data-ttu-id="79c91-117">I moduli prodotti durante una compilazione diventano file associati a un assembly prodotto anch'esso in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="79c91-117">Any modules produced as part of a compilation become files associated with any assembly also produced in the compilation.</span></span> <span data-ttu-id="79c91-118">Per visualizzare il manifesto dell'assembly e i file associati, usare [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="79c91-118">Use [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) to view the assembly manifest to see the associated files.</span></span>  
  
 <span data-ttu-id="79c91-119">L'opzione del compilatore -out è necessaria perché un file eseguibile sia la destinazione di un assembly Friend.</span><span class="sxs-lookup"><span data-stu-id="79c91-119">The -out compiler option is required in order for an exe to be the target of a friend assembly.</span></span> <span data-ttu-id="79c91-120">Per altre informazioni, vedere [Assembly Friend](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="79c91-120">For more information see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="79c91-121">Per impostare l'opzione del compilatore nell'ambiente di sviluppo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="79c91-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="79c91-122">Aprire la pagina **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="79c91-122">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="79c91-123">Fare clic sulla pagina delle proprietà **Applicazione**.</span><span class="sxs-lookup"><span data-stu-id="79c91-123">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="79c91-124">Modificare la proprietà **Nome assembly**.</span><span class="sxs-lookup"><span data-stu-id="79c91-124">Modify the **Assembly name** property.</span></span>  
  
     <span data-ttu-id="79c91-125">Per impostare l'opzione del compilatore a livello di codice: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> è una proprietà di sola lettura caratterizzata dalla combinazione del tipo di progetto (file eseguibile, libreria e così via) e del nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="79c91-125">To set this compiler option programmatically: the <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> is a read-only property, which is determined by a combination of the project type (exe, library, and so forth) and the assembly name.</span></span> <span data-ttu-id="79c91-126">Per impostare il nome del file di output sarà necessario modificare una o entrambe queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="79c91-126">Modifying one or both of these properties will be necessary to set the output file name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79c91-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="79c91-127">Example</span></span>  
 <span data-ttu-id="79c91-128">Per compilare `t.cs` e creare il file di output `t.exe`, nonché per generare `t2.cs` e creare il file di output del modulo `mymodule.netmodule`:</span><span class="sxs-lookup"><span data-stu-id="79c91-128">Compile `t.cs` and create output file `t.exe`, as well as build `t2.cs` and create module output file `mymodule.netmodule`:</span></span>  
  
```console  
csc t.cs -out:mymodule.netmodule -target:module t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="79c91-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79c91-129">See also</span></span>

- [<span data-ttu-id="79c91-130">Opzioni del compilatore C</span><span class="sxs-lookup"><span data-stu-id="79c91-130">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="79c91-131">Assemblaggi amici</span><span class="sxs-lookup"><span data-stu-id="79c91-131">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
- [<span data-ttu-id="79c91-132">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="79c91-132">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
