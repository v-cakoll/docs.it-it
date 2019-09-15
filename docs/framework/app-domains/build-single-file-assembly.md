---
title: 'Procedura: Compilazione di un .NET Framework assembly a file singolo'
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
dev_langs:
- csharp
- vb
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98f06e62e1070f78faa77ef7d83fd80a62984684
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991240"
---
# <a name="how-to-build-a-net-framework-single-file-assembly"></a><span data-ttu-id="0de89-102">Procedura: Compilazione di un .NET Framework assembly a file singolo</span><span class="sxs-lookup"><span data-stu-id="0de89-102">How to: Build a .NET Framework single-file assembly</span></span>

<span data-ttu-id="0de89-103">Un assembly su singolo file, che rappresenta il tipo di assembly più semplice, contiene le informazioni e l'implementazione relative al tipo, oltre al [manifesto dell'assembly](../../standard/assembly/manifest.md).</span><span class="sxs-lookup"><span data-stu-id="0de89-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../standard/assembly/manifest.md).</span></span> <span data-ttu-id="0de89-104">È possibile usare i compilatori della riga di comando o Visual Studio per creare un assembly a file singolo destinato al .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0de89-104">You can use command-line compilers or Visual Studio to create a single-file assembly that targets the .NET Framework.</span></span> <span data-ttu-id="0de89-105">Per impostazione predefinita, il compilatore crea un file di assembly con estensione *exe* .</span><span class="sxs-lookup"><span data-stu-id="0de89-105">By default, the compiler creates an assembly file with an *.exe* extension.</span></span>

> [!NOTE]
> <span data-ttu-id="0de89-106">È possibile usare Visual Studio per C# e Visual Basic solo per creare assembly con un singolo file.</span><span class="sxs-lookup"><span data-stu-id="0de89-106">Visual Studio for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="0de89-107">Per creare assembly con più file, è necessario usare i compilatori della riga di comando o Visual C++.</span><span class="sxs-lookup"><span data-stu-id="0de89-107">If you want to create multifile assemblies, you must use command-line compilers or Visual C++.</span></span>

<span data-ttu-id="0de89-108">Le procedure seguenti illustrano come creare assembly su singolo file usando i compilatori della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0de89-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>

## <a name="create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="0de89-109">Creare un assembly con estensione exe</span><span class="sxs-lookup"><span data-stu-id="0de89-109">Create an assembly with an .exe extension</span></span>

<span data-ttu-id="0de89-110">Al prompt dei comandi digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="0de89-110">At the command prompt, type the following command:</span></span>

<span data-ttu-id="0de89-111">\<*comando compilatore*> \<*nome modulo*></span><span class="sxs-lookup"><span data-stu-id="0de89-111">\<*compiler command*> \<*module name*></span></span>

<span data-ttu-id="0de89-112">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0de89-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="0de89-113">Nell'esempio seguente viene creato un assembly denominato *Decode. exe* da un modulo di codice `myCode`denominato.</span><span class="sxs-lookup"><span data-stu-id="0de89-113">The following example creates an assembly named *myCode.exe* from a code module called `myCode`.</span></span>

```csharp
csc myCode.cs
```

```vb
vbc myCode.vb
```

## <a name="create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="0de89-114">Creare un assembly con estensione exe e specificare il nome del file di output</span><span class="sxs-lookup"><span data-stu-id="0de89-114">Create an assembly with an .exe extension and specify the output file name</span></span>

<span data-ttu-id="0de89-115">Al prompt dei comandi digitare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="0de89-115">At the command prompt, type the following command:</span></span>

<span data-ttu-id="0de89-116">\<*comando compilatore*>  **/out:** \<*nome file*> \<*nome modulo*></span><span class="sxs-lookup"><span data-stu-id="0de89-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>

<span data-ttu-id="0de89-117">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice, *nome file* è il nome del file di output e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0de89-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="0de89-118">Nell'esempio seguente viene creato un assembly denominato MyAssembly *. exe* da un modulo di codice `myCode`denominato.</span><span class="sxs-lookup"><span data-stu-id="0de89-118">The following example creates an assembly named *myAssembly.exe* from a code module called `myCode`.</span></span>

```csharp
csc -out:myAssembly.exe myCode.cs
```

```vb
vbc -out:myAssembly.exe myCode.vb
```

## <a name="create-library-assemblies"></a><span data-ttu-id="0de89-119">Creazione di assembly di librerie</span><span class="sxs-lookup"><span data-stu-id="0de89-119">Create library assemblies</span></span>
 <span data-ttu-id="0de89-120">Un assembly di librerie è simile a una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="0de89-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="0de89-121">L'assembly contiene tipi a cui altri assembly faranno riferimento, ma non ha alcun punto di ingresso per avviare l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0de89-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>

<span data-ttu-id="0de89-122">Per creare un assembly di librerie, digitare il comando seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="0de89-122">To create a library assembly, at the command prompt, type the following command:</span></span>

<span data-ttu-id="0de89-123">\<*comando compilatore*>  **-t:library** \<*nome modulo*></span><span class="sxs-lookup"><span data-stu-id="0de89-123">\<*compiler command*> **-t:library** \<*module name*></span></span>

<span data-ttu-id="0de89-124">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0de89-124">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="0de89-125">È possibile usare anche altre opzioni del compilatore, ad esempio l'opzione **-out:** .</span><span class="sxs-lookup"><span data-stu-id="0de89-125">You can also use other compiler options, such as the **-out:** option.</span></span>

<span data-ttu-id="0de89-126">Nell'esempio seguente viene creato un assembly di libreria denominato *myCodeAssembly. dll* da un modulo `myCode`di codice denominato.</span><span class="sxs-lookup"><span data-stu-id="0de89-126">The following example creates a library assembly named *myCodeAssembly.dll* from a code module called `myCode`.</span></span>

```csharp
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```vb
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a><span data-ttu-id="0de89-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0de89-127">See also</span></span>

- [<span data-ttu-id="0de89-128">Creazione di assembly</span><span class="sxs-lookup"><span data-stu-id="0de89-128">Create assemblies</span></span>](../../standard/assembly/create.md)
- [<span data-ttu-id="0de89-129">Assembly su più file</span><span class="sxs-lookup"><span data-stu-id="0de89-129">Multifile assemblies</span></span>](multifile-assemblies.md)
- [<span data-ttu-id="0de89-130">Procedura: Compilare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="0de89-130">How to: Build a multifile assembly</span></span>](build-multifile-assembly.md)
- [<span data-ttu-id="0de89-131">Programma con assembly</span><span class="sxs-lookup"><span data-stu-id="0de89-131">Program with assemblies</span></span>](../../standard/assembly/program.md)
