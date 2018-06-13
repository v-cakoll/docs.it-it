---
title: 'Procedura: compilare un assembly su singolo file'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6aa39671da519ebf54dad52638ab940897209517
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744317"
---
# <a name="how-to-build-a-single-file-assembly"></a><span data-ttu-id="21487-102">Procedura: compilare un assembly su singolo file</span><span class="sxs-lookup"><span data-stu-id="21487-102">How to: Build a Single-File Assembly</span></span>
<span data-ttu-id="21487-103">Un assembly su singolo file, che rappresenta il tipo di assembly più semplice, contiene le informazioni e l'implementazione relative al tipo, oltre al [manifesto dell'assembly](../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="21487-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md).</span></span> <span data-ttu-id="21487-104">Per creare un assembly su singolo file, è possibile usare i compilatori della riga di comando o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21487-104">You can use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] to create a single-file assembly.</span></span> <span data-ttu-id="21487-105">Per impostazione predefinita, il file di assembly creato dal compilatore ha l'estensione exe.</span><span class="sxs-lookup"><span data-stu-id="21487-105">By default, the compiler creates an assembly file with an .exe extension.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21487-106">È possibile usare [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] per C# e Visual Basic solo per la creazione di assembly su singolo file.</span><span class="sxs-lookup"><span data-stu-id="21487-106">[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="21487-107">Per creare assembly su più file, è necessario usare i compilatori della riga di comando o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] per Visual C++.</span><span class="sxs-lookup"><span data-stu-id="21487-107">If you want to create multifile assemblies, you must use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] for Visual C++.</span></span>  
  
 <span data-ttu-id="21487-108">Le procedure seguenti illustrano come creare assembly su singolo file usando i compilatori della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="21487-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>  
  
### <a name="to-create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="21487-109">Per creare un assembly con estensione exe</span><span class="sxs-lookup"><span data-stu-id="21487-109">To create an assembly with an .exe extension</span></span>  
  
1.  <span data-ttu-id="21487-110">Al prompt dei comandi digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="21487-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="21487-111">\<*comando compilatore*> \<*nome modulo*></span><span class="sxs-lookup"><span data-stu-id="21487-111">\<*compiler command*> \<*module name*></span></span>  
  
     <span data-ttu-id="21487-112">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="21487-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="21487-113">L'esempio seguente crea un assembly denominato `myCode.exe` da un modulo di codice denominato `myCode`.</span><span class="sxs-lookup"><span data-stu-id="21487-113">The following example creates an assembly named `myCode.exe` from a code module called `myCode`.</span></span>  
  
```console
csc myCode.cs  
```  

```console
vbc myCode.vb  
```  
  
#### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="21487-114">Per creare un assembly con estensione exe e specificare il nome del file di output</span><span class="sxs-lookup"><span data-stu-id="21487-114">To create an assembly with an .exe extension and specify the output file name</span></span>  
  
1.  <span data-ttu-id="21487-115">Al prompt dei comandi digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="21487-115">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="21487-116">\<*comando compilatore*> **/out:**\<*nome file*> \<*nome modulo*></span><span class="sxs-lookup"><span data-stu-id="21487-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>  
  
     <span data-ttu-id="21487-117">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice, *nome file* è il nome del file di output e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="21487-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="21487-118">L'esempio seguente crea un assembly denominato `myAssembly.exe` da un modulo di codice denominato `myCode`.</span><span class="sxs-lookup"><span data-stu-id="21487-118">The following example creates an assembly named `myAssembly.exe` from a code module called `myCode`.</span></span>  
  
```console  
csc -out:myAssembly.exe myCode.cs  
```  
  
```console
vbc -out:myAssembly.exe myCode.vb  
```  
  
## <a name="creating-library-assemblies"></a><span data-ttu-id="21487-119">Creazione di assembly di librerie</span><span class="sxs-lookup"><span data-stu-id="21487-119">Creating Library Assemblies</span></span>  
 <span data-ttu-id="21487-120">Un assembly di librerie è simile a una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="21487-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="21487-121">L'assembly contiene tipi a cui altri assembly faranno riferimento, ma non ha alcun punto di ingresso per avviare l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21487-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>  
  
#### <a name="to-create-a-library-assembly"></a><span data-ttu-id="21487-122">Per creare un assembly di librerie</span><span class="sxs-lookup"><span data-stu-id="21487-122">To create a library assembly</span></span>  
  
1.  <span data-ttu-id="21487-123">Al prompt dei comandi digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="21487-123">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="21487-124">\<*comando compilatore*> **-t:library** \<*nome modulo*></span><span class="sxs-lookup"><span data-stu-id="21487-124">\<*compiler command*> **-t:library** \<*module name*></span></span>  
  
     <span data-ttu-id="21487-125">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="21487-125">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="21487-126">È possibile usare anche altre opzioni del compilatore, ad esempio l'opzione **-out:**.</span><span class="sxs-lookup"><span data-stu-id="21487-126">You can also use other compiler options, such as the **-out:** option.</span></span>  
  
 <span data-ttu-id="21487-127">L'esempio seguente crea un assembly di librerie denominato `myCodeAssembly.dll` da un modulo di codice denominato `myCode`.</span><span class="sxs-lookup"><span data-stu-id="21487-127">The following example creates a library assembly named `myCodeAssembly.dll` from a code module called `myCode`.</span></span>  
  
```console  
csc -out:myCodeLibrary.dll -t:library myCode.cs  
```  
  
```console
vbc -out:myCodeLibrary.dll -t:library myCode.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="21487-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21487-128">See Also</span></span>  
 [<span data-ttu-id="21487-129">Creazione degli assembly</span><span class="sxs-lookup"><span data-stu-id="21487-129">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="21487-130">Assembly su più file</span><span class="sxs-lookup"><span data-stu-id="21487-130">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)  
 [<span data-ttu-id="21487-131">Procedura: Compilare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="21487-131">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="21487-132">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="21487-132">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
