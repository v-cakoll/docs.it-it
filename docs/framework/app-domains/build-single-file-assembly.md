---
title: 'Procedura: compilare un assembly a file singolo .NET Framework'
description: Informazioni su come creare un assembly su singolo file in .NET. Un assembly con un solo file può essere una libreria (. dll) destinata a .NET oppure un file eseguibile (exe).
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
ms.openlocfilehash: 482a973631e899b8d4bfc4640eef1ea26173605e
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104918"
---
# <a name="how-to-build-a-net-framework-single-file-assembly"></a><span data-ttu-id="1386e-104">Procedura: compilare un assembly a file singolo .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1386e-104">How to: Build a .NET Framework single-file assembly</span></span>

<span data-ttu-id="1386e-105">Un assembly su singolo file, che rappresenta il tipo di assembly più semplice, contiene le informazioni e l'implementazione relative al tipo, oltre al [manifesto dell'assembly](../../standard/assembly/manifest.md).</span><span class="sxs-lookup"><span data-stu-id="1386e-105">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../standard/assembly/manifest.md).</span></span> <span data-ttu-id="1386e-106">È possibile usare i compilatori della riga di comando o Visual Studio per creare un assembly a file singolo destinato al .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1386e-106">You can use command-line compilers or Visual Studio to create a single-file assembly that targets the .NET Framework.</span></span> <span data-ttu-id="1386e-107">Per impostazione predefinita, il compilatore crea un file di assembly con estensione *exe* .</span><span class="sxs-lookup"><span data-stu-id="1386e-107">By default, the compiler creates an assembly file with an *.exe* extension.</span></span>

> [!NOTE]
> <span data-ttu-id="1386e-108">È possibile usare Visual Studio per C# e Visual Basic solo per creare assembly con un singolo file.</span><span class="sxs-lookup"><span data-stu-id="1386e-108">Visual Studio for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="1386e-109">Per creare assembly con più file, è necessario usare i compilatori della riga di comando o Visual C++.</span><span class="sxs-lookup"><span data-stu-id="1386e-109">If you want to create multifile assemblies, you must use command-line compilers or Visual C++.</span></span>

<span data-ttu-id="1386e-110">Le procedure seguenti illustrano come creare assembly su singolo file usando i compilatori della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="1386e-110">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>

## <a name="create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="1386e-111">Creare un assembly con estensione exe</span><span class="sxs-lookup"><span data-stu-id="1386e-111">Create an assembly with an .exe extension</span></span>

<span data-ttu-id="1386e-112">Al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1386e-112">At the command prompt, type the following command:</span></span>

<span data-ttu-id="1386e-113">\<*compiler command*> \<*module name*></span><span class="sxs-lookup"><span data-stu-id="1386e-113">\<*compiler command*> \<*module name*></span></span>

<span data-ttu-id="1386e-114">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1386e-114">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="1386e-115">Nell'esempio seguente viene creato un assembly denominato *myCode.exe* da un modulo di codice denominato `myCode` .</span><span class="sxs-lookup"><span data-stu-id="1386e-115">The following example creates an assembly named *myCode.exe* from a code module called `myCode`.</span></span>

```csharp
csc myCode.cs
```

```vb
vbc myCode.vb
```

## <a name="create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="1386e-116">Creare un assembly con estensione exe e specificare il nome del file di output</span><span class="sxs-lookup"><span data-stu-id="1386e-116">Create an assembly with an .exe extension and specify the output file name</span></span>

<span data-ttu-id="1386e-117">Al prompt dei comandi digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1386e-117">At the command prompt, type the following command:</span></span>

<span data-ttu-id="1386e-118">\<*compiler command*>**/out:** \<*file name*>\<*module name*></span><span class="sxs-lookup"><span data-stu-id="1386e-118">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>

<span data-ttu-id="1386e-119">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice, *nome file* è il nome del file di output e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1386e-119">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="1386e-120">Nell'esempio seguente viene creato un assembly denominato *myAssembly.exe* da un modulo di codice denominato `myCode` .</span><span class="sxs-lookup"><span data-stu-id="1386e-120">The following example creates an assembly named *myAssembly.exe* from a code module called `myCode`.</span></span>

```csharp
csc -out:myAssembly.exe myCode.cs
```

```vb
vbc -out:myAssembly.exe myCode.vb
```

## <a name="create-library-assemblies"></a><span data-ttu-id="1386e-121">Creazione di assembly di librerie</span><span class="sxs-lookup"><span data-stu-id="1386e-121">Create library assemblies</span></span>
 <span data-ttu-id="1386e-122">Un assembly di librerie è simile a una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="1386e-122">A library assembly is similar to a class library.</span></span> <span data-ttu-id="1386e-123">L'assembly contiene tipi a cui altri assembly faranno riferimento, ma non ha alcun punto di ingresso per avviare l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1386e-123">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>

<span data-ttu-id="1386e-124">Per creare un assembly di librerie, digitare il comando seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="1386e-124">To create a library assembly, at the command prompt, type the following command:</span></span>

<span data-ttu-id="1386e-125">\<*compiler command*>**-t:Library**\<*module name*></span><span class="sxs-lookup"><span data-stu-id="1386e-125">\<*compiler command*> **-t:library** \<*module name*></span></span>

<span data-ttu-id="1386e-126">In questo comando *comando compilatore* è il comando del compilatore per il linguaggio usato nel modulo di codice e *nome modulo* è il nome del modulo di codice da compilare nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1386e-126">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="1386e-127">È possibile usare anche altre opzioni del compilatore, ad esempio l'opzione **-out:**.</span><span class="sxs-lookup"><span data-stu-id="1386e-127">You can also use other compiler options, such as the **-out:** option.</span></span>

<span data-ttu-id="1386e-128">Nell'esempio seguente viene creato un assembly di libreria denominato *myCodeAssembly.dll* da un modulo di codice denominato `myCode` .</span><span class="sxs-lookup"><span data-stu-id="1386e-128">The following example creates a library assembly named *myCodeAssembly.dll* from a code module called `myCode`.</span></span>

```csharp
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```vb
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a><span data-ttu-id="1386e-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1386e-129">See also</span></span>

- [<span data-ttu-id="1386e-130">Creare assembly</span><span class="sxs-lookup"><span data-stu-id="1386e-130">Create assemblies</span></span>](../../standard/assembly/create.md)
- [<span data-ttu-id="1386e-131">Assembly su più file</span><span class="sxs-lookup"><span data-stu-id="1386e-131">Multifile assemblies</span></span>](multifile-assemblies.md)
- [<span data-ttu-id="1386e-132">Procedura: Creare un assembly su più file</span><span class="sxs-lookup"><span data-stu-id="1386e-132">How to: Build a multifile assembly</span></span>](build-multifile-assembly.md)
- [<span data-ttu-id="1386e-133">Programmare con gli assembly</span><span class="sxs-lookup"><span data-stu-id="1386e-133">Program with assemblies</span></span>](../../standard/assembly/index.md)
