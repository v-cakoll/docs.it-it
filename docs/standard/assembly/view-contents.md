---
title: "Procedura: visualizzare il contenuto dell'assembly"
description: È possibile usare il disassembler IL per visualizzare gli attributi e i riferimenti di un assembly ad altri moduli e assembly.
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: aed490459252466c6da06e5422b83b1bc20fb885
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380061"
---
# <a name="how-to-view-assembly-contents"></a><span data-ttu-id="88c26-103">Procedura: visualizzare il contenuto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="88c26-103">How to: View assembly contents</span></span>

<span data-ttu-id="88c26-104">È possibile usare [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) per visualizzare informazioni di Microsoft Intermediate Language (MSIL) in un file.</span><span class="sxs-lookup"><span data-stu-id="88c26-104">You can use the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in a file.</span></span> <span data-ttu-id="88c26-105">Se il file esaminato è un assembly, queste informazioni possono includere gli attributi dell'assembly e i riferimenti ad altri moduli e assembly.</span><span class="sxs-lookup"><span data-stu-id="88c26-105">If the file being examined is an assembly, this information can include the assembly's attributes and references to other modules and assemblies.</span></span> <span data-ttu-id="88c26-106">Queste informazioni possono essere utili per determinare se un file è un assembly o una parte di un assembly e se il file contiene riferimenti ad altri moduli o assembly.</span><span class="sxs-lookup"><span data-stu-id="88c26-106">This information can be helpful in determining whether a file is an assembly or part of an assembly and whether the file has references to other modules or assemblies.</span></span>

<span data-ttu-id="88c26-107">Per visualizzare il contenuto di un assembly tramite *Ildasm. exe*, immettere **il \< nome dell'assembly Ildasm>** al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="88c26-107">To display the contents of an assembly using *Ildasm.exe*, enter **ildasm \<assembly name>** at a command prompt.</span></span> <span data-ttu-id="88c26-108">Ad esempio, il comando seguente Disassembla l'assembly *Hello. exe* .</span><span class="sxs-lookup"><span data-stu-id="88c26-108">For example, the following command disassembles the *Hello.exe* assembly.</span></span>

```cmd
ildasm Hello.exe
```

<span data-ttu-id="88c26-109">Per visualizzare le informazioni del manifesto dell'assembly, fare doppio clic sull'icona del **manifesto** nella finestra del disassembler MSIL.</span><span class="sxs-lookup"><span data-stu-id="88c26-109">To view assembly manifest information, double-click the **Manifest** icon in the MSIL Disassembler window.</span></span>

## <a name="example"></a><span data-ttu-id="88c26-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="88c26-110">Example</span></span>

<span data-ttu-id="88c26-111">L'esempio seguente inizia con un programma "Hello World" di base.</span><span class="sxs-lookup"><span data-stu-id="88c26-111">The following example starts with a basic "Hello World" program.</span></span> <span data-ttu-id="88c26-112">Dopo la compilazione del programma, utilizzare *Ildasm. exe* per disassemblare l'assembly *Hello. exe* e visualizzare il manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="88c26-112">After compiling the program, use *Ildasm.exe* to disassemble the *Hello.exe* assembly and view the assembly manifest.</span></span>

```cpp
using namespace System;

class MainApp
{
public:
    static void Main()
    {
        Console::WriteLine("Hello World using C++/CLI!");
    }
};

int main()
{
    MainApp::Main();
}
```

```csharp
using System;

class MainApp
{
    public static void Main()
    {
        Console.WriteLine("Hello World using C#!");
    }
}
```

```vb
Class MainApp
    Public Shared Sub Main()
        Console.WriteLine("Hello World using Visual Basic!")
    End Sub
End Class
```

<span data-ttu-id="88c26-113">Se si esegue il comando *Ildasm. exe* nell'assembly *Hello. exe* e si fa doppio clic sull'icona del **manifesto** nella finestra del disassembler MSIL, viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="88c26-113">Running the command *ildasm.exe* on the *Hello.exe* assembly and double-clicking the **Manifest** icon in the MSIL Disassembler window produces the following output:</span></span>

```output
// Metadata version: v4.0.30319
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 4:0:0:0
}
.assembly Hello
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .custom instance void [mscorlib]System.Runtime.CompilerServices.RuntimeCompatibilityAttribute::.ctor() = ( 01 00 01 00 54 02 16 57 72 61 70 4E 6F 6E 45 78   // ....T..WrapNonEx
                                                                                                             63 65 70 74 69 6F 6E 54 68 72 6F 77 73 01 )       // ceptionThrows.
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module Hello.exe
// MVID: {7C2770DB-1594-438D-BAE5-98764C39CCCA}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x00600000
```

<span data-ttu-id="88c26-114">Nella tabella seguente vengono descritte le singole direttive del manifesto dell'assembly dell'assembly *Hello. exe* utilizzato nell'esempio:</span><span class="sxs-lookup"><span data-stu-id="88c26-114">The following table describes each directive in the assembly manifest of the *Hello.exe* assembly used in the example:</span></span>

|<span data-ttu-id="88c26-115">Direttiva</span><span class="sxs-lookup"><span data-stu-id="88c26-115">Directive</span></span>|<span data-ttu-id="88c26-116">Description</span><span class="sxs-lookup"><span data-stu-id="88c26-116">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="88c26-117">**. assembly extern \< nome assembly>**</span><span class="sxs-lookup"><span data-stu-id="88c26-117">**.assembly extern \<assembly name>**</span></span>|<span data-ttu-id="88c26-118">Specifica un altro assembly contenente elementi a cui il modulo corrente fa riferimento (in questo esempio `mscorlib`).</span><span class="sxs-lookup"><span data-stu-id="88c26-118">Specifies another assembly that contains items referenced by the current module (in this example, `mscorlib`).</span></span>|
|<span data-ttu-id="88c26-119">**\<>token. PublicKeyToken**</span><span class="sxs-lookup"><span data-stu-id="88c26-119">**.publickeytoken \<token>**</span></span>|<span data-ttu-id="88c26-120">Specifica il token della chiave effettiva dell'assembly a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="88c26-120">Specifies the token of the actual key of the referenced assembly.</span></span>|
|<span data-ttu-id="88c26-121">**. ver \< numero di versione>**</span><span class="sxs-lookup"><span data-stu-id="88c26-121">**.ver \<version number>**</span></span>|<span data-ttu-id="88c26-122">Specifica il numero di versione dell'assembly a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="88c26-122">Specifies the version number of the referenced assembly.</span></span>|
|<span data-ttu-id="88c26-123">**. \< nome assembly assembly>**</span><span class="sxs-lookup"><span data-stu-id="88c26-123">**.assembly \<assembly name>**</span></span>|<span data-ttu-id="88c26-124">Specifica il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="88c26-124">Specifies the assembly name.</span></span>|
|<span data-ttu-id="88c26-125">**. valore Int32 dell'algoritmo hash \<>**</span><span class="sxs-lookup"><span data-stu-id="88c26-125">**.hash algorithm \<int32 value>**</span></span>|<span data-ttu-id="88c26-126">Specifica l'algoritmo hash usato.</span><span class="sxs-lookup"><span data-stu-id="88c26-126">Specifies the hash algorithm used.</span></span>|
|<span data-ttu-id="88c26-127">**. ver \< numero di versione>**</span><span class="sxs-lookup"><span data-stu-id="88c26-127">**.ver \<version number>**</span></span>|<span data-ttu-id="88c26-128">Specifica il numero di versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="88c26-128">Specifies the version number of the assembly.</span></span>|
|<span data-ttu-id="88c26-129">**\<nome file. modulo>**</span><span class="sxs-lookup"><span data-stu-id="88c26-129">**.module \<file name>**</span></span>|<span data-ttu-id="88c26-130">Specifica il nome dei moduli che costituiscono l'assembly.</span><span class="sxs-lookup"><span data-stu-id="88c26-130">Specifies the name of the modules that make up the assembly.</span></span> <span data-ttu-id="88c26-131">In questo esempio l'assembly è costituito da un unico file.</span><span class="sxs-lookup"><span data-stu-id="88c26-131">In this example, the assembly consists of only one file.</span></span>|
|<span data-ttu-id="88c26-132">**. valore del sottosistema \<>**</span><span class="sxs-lookup"><span data-stu-id="88c26-132">**.subsystem \<value>**</span></span>|<span data-ttu-id="88c26-133">Specifica l'ambiente di applicazione necessario per il programma.</span><span class="sxs-lookup"><span data-stu-id="88c26-133">Specifies the application environment required for the program.</span></span> <span data-ttu-id="88c26-134">In questo esempio il valore 3 indica che il file eseguibile viene eseguito da una console.</span><span class="sxs-lookup"><span data-stu-id="88c26-134">In this example, the value 3 indicates that this executable is run from a console.</span></span>|
|<span data-ttu-id="88c26-135">**.corflags**</span><span class="sxs-lookup"><span data-stu-id="88c26-135">**.corflags**</span></span>|<span data-ttu-id="88c26-136">Attualmente, campo riservato nei metadati.</span><span class="sxs-lookup"><span data-stu-id="88c26-136">Currently a reserved field in the metadata.</span></span>|

<span data-ttu-id="88c26-137">Il manifesto di un assembly può contenere diverse direttive, a seconda del contenuto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="88c26-137">An assembly manifest can contain a number of different directives, depending on the contents of the assembly.</span></span> <span data-ttu-id="88c26-138">Per un elenco completo delle direttive nel manifesto dell'assembly, vedere la documentazione relativa a ECMA, in particolare "Partition II: Metadata Definition and Semantics" e "Partition III: CIL instruction set":</span><span class="sxs-lookup"><span data-stu-id="88c26-138">For an extensive list of the directives in the assembly manifest, see the Ecma documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set":</span></span>

- [<span data-ttu-id="88c26-139">Standard ECMA C# e Common Language Infrastructure</span><span class="sxs-lookup"><span data-stu-id="88c26-139">ECMA C# and Common Language Infrastructure standards</span></span>](../components.md#applicable-standards)
- [<span data-ttu-id="88c26-140">ECMA-335-Common Language Infrastructure standard (CLI)</span><span class="sxs-lookup"><span data-stu-id="88c26-140">Standard ECMA-335 - Common Language Infrastructure (CLI)</span></span>](http://www.ecma-international.org/publications/standards/Ecma-335.htm)

## <a name="see-also"></a><span data-ttu-id="88c26-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88c26-141">See also</span></span>

- [<span data-ttu-id="88c26-142">Domini applicazione e assembly</span><span class="sxs-lookup"><span data-stu-id="88c26-142">Application domains and assemblies</span></span>](../../framework/app-domains/application-domains.md#application-domains-and-assemblies)
- [<span data-ttu-id="88c26-143">Procedure per i domini applicazione e gli assembly</span><span class="sxs-lookup"><span data-stu-id="88c26-143">Application domains and assemblies how-to topics</span></span>](../../framework/app-domains/application-domains-and-assemblies-how-to-topics.md)
- [<span data-ttu-id="88c26-144">Ildasm. exe (disassembler IL)</span><span class="sxs-lookup"><span data-stu-id="88c26-144">Ildasm.exe (IL Disassembler)</span></span>](../../framework/tools/ildasm-exe-il-disassembler.md)
