---
title: "Procedura: Visualizzare il contenuto dell'assembly"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abe4c130fb5da49ed0f53c776e23dba8fb5b15f7
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "46585336"
---
# <a name="how-to-view-assembly-contents"></a><span data-ttu-id="e5b68-102">Procedura: Visualizzare il contenuto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="e5b68-102">How to: View Assembly Contents</span></span>
<span data-ttu-id="e5b68-103">È possibile usare [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) per visualizzare informazioni di Microsoft Intermediate Language (MSIL) in un file.</span><span class="sxs-lookup"><span data-stu-id="e5b68-103">You can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in a file.</span></span> <span data-ttu-id="e5b68-104">Se il file esaminato è un assembly, è possibile che le informazioni includano gli attributi dell'assembly, oltre a riferimenti ad altri moduli e assembly.</span><span class="sxs-lookup"><span data-stu-id="e5b68-104">If the file being examined is an assembly, this information can include the assembly's attributes, as well as references to other modules and assemblies.</span></span> <span data-ttu-id="e5b68-105">Queste informazioni possono risultare utili nel determinare se un file è un assembly o se è parte di un assembly e se il file contiene riferimenti ad altri moduli o assembly.</span><span class="sxs-lookup"><span data-stu-id="e5b68-105">This information can be helpful in determining whether a file is an assembly or part of an assembly, and whether the file has references to other modules or assemblies.</span></span>  
  
### <a name="to-display-the-contents-of-an-assembly-using-ildasmexe"></a><span data-ttu-id="e5b68-106">Per visualizzare il contenuto di un assembly usando Ildasm.exe</span><span class="sxs-lookup"><span data-stu-id="e5b68-106">To display the contents of an assembly using Ildasm.exe</span></span>  
  
1.  <span data-ttu-id="e5b68-107">Al prompt dei comandi digitare **ildasm** \<*nome assembly*>.</span><span class="sxs-lookup"><span data-stu-id="e5b68-107">Type **ildasm** \<*assembly name*> at the command prompt.</span></span> <span data-ttu-id="e5b68-108">Ad esempio, il comando seguente esegue il disassemblaggio dell'assembly `Hello.exe`.</span><span class="sxs-lookup"><span data-stu-id="e5b68-108">For example, the following command disassembles the `Hello.exe` assembly.</span></span>  
  
    ```  
    ildasm Hello.exe  
    ```  
  
### <a name="to-view-assembly-manifest-information"></a><span data-ttu-id="e5b68-109">Per visualizzare informazioni del manifesto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="e5b68-109">To view assembly manifest information</span></span>  
  
1.  <span data-ttu-id="e5b68-110">Fare doppio clic sull'icona MANIFESTO nella finestra Disassembler MSIL.</span><span class="sxs-lookup"><span data-stu-id="e5b68-110">Double-click the MANIFEST icon in the MSIL Disassembler window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5b68-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="e5b68-111">Example</span></span>  
 <span data-ttu-id="e5b68-112">L'esempio seguente avvia un programma "Hello, World" di base.</span><span class="sxs-lookup"><span data-stu-id="e5b68-112">The following example starts with a basic "Hello, World" program.</span></span> <span data-ttu-id="e5b68-113">Dopo aver compilato il programma usare Ildasm.exe per disassemblare l'assembly Hello.exe e visualizzarne il manifesto.</span><span class="sxs-lookup"><span data-stu-id="e5b68-113">After compiling the program, use Ildasm.exe to disassemble the Hello.exe assembly and view the assembly manifest.</span></span>  
  
 [!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)]
 [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]  
  
 <span data-ttu-id="e5b68-114">Se si esegue il comando ildasm.exe nell'assembly Hello.exe e si fa doppio clic sull'icona MANIFESTO nella finestra IL DASM, viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="e5b68-114">Running the command ildasm.exe on the Hello.exe assembly and double-clicking the MANIFEST icon in the IL DASM window produces the following output:</span></span>  
  
```  
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
  
 <span data-ttu-id="e5b68-115">La tabella seguente descrive ogni direttiva del manifesto dell'assembly relativo all'assembly Hello.exe usato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="e5b68-115">The following table describes each directive in the assembly manifest of the Hello.exe assembly used in the example.</span></span>  
  
|<span data-ttu-id="e5b68-116">Direttiva</span><span class="sxs-lookup"><span data-stu-id="e5b68-116">Directive</span></span>|<span data-ttu-id="e5b68-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5b68-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5b68-118">**.assembly extern \<** *nome assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="e5b68-118">**.assembly extern \<** *assembly name* **>**</span></span>|<span data-ttu-id="e5b68-119">Specifica un altro assembly contenente elementi a cui il modulo corrente fa riferimento (in questo esempio `mscorlib`).</span><span class="sxs-lookup"><span data-stu-id="e5b68-119">Specifies another assembly that contains items referenced by the current module (in this example, `mscorlib`).</span></span>|  
|<span data-ttu-id="e5b68-120">**.publickeytoken \<** *token* **>**</span><span class="sxs-lookup"><span data-stu-id="e5b68-120">**.publickeytoken \<** *token* **>**</span></span>|<span data-ttu-id="e5b68-121">Specifica il token della chiave effettiva dell'assembly a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="e5b68-121">Specifies the token of the actual key of the referenced assembly.</span></span>|  
|<span data-ttu-id="e5b68-122">**.ver \<** *numero versione* **>**</span><span class="sxs-lookup"><span data-stu-id="e5b68-122">**.ver \<** *version number* **>**</span></span>|<span data-ttu-id="e5b68-123">Specifica il numero di versione dell'assembly a cui viene fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="e5b68-123">Specifies the version number of the referenced assembly.</span></span>|  
|<span data-ttu-id="e5b68-124">**.assembly \<** *nome assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="e5b68-124">**.assembly \<** *assembly name* **>**</span></span>|<span data-ttu-id="e5b68-125">Specifica il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e5b68-125">Specifies the assembly name.</span></span>|  
|<span data-ttu-id="e5b68-126">**.hash algorithm \<** *valore int32* **>**</span><span class="sxs-lookup"><span data-stu-id="e5b68-126">**.hash algorithm \<** *int32 value* **>**</span></span>|<span data-ttu-id="e5b68-127">Specifica l'algoritmo hash usato.</span><span class="sxs-lookup"><span data-stu-id="e5b68-127">Specifies the hash algorithm used.</span></span>|  
|<span data-ttu-id="e5b68-128">**.ver \<** *numero versione* **>**</span><span class="sxs-lookup"><span data-stu-id="e5b68-128">**.ver \<** *version number* **>**</span></span>|<span data-ttu-id="e5b68-129">Specifica il numero di versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e5b68-129">Specifies the version number of the assembly.</span></span>|  
|<span data-ttu-id="e5b68-130">**.module \<** *nome file* **>**</span><span class="sxs-lookup"><span data-stu-id="e5b68-130">**.module \<** *file name* **>**</span></span>|<span data-ttu-id="e5b68-131">Specifica il nome dei moduli che costituiscono l'assembly.</span><span class="sxs-lookup"><span data-stu-id="e5b68-131">Specifies the name of the modules that make up the assembly.</span></span> <span data-ttu-id="e5b68-132">In questo esempio l'assembly è costituito da un unico file.</span><span class="sxs-lookup"><span data-stu-id="e5b68-132">In this example, the assembly consists of only one file.</span></span>|  
|<span data-ttu-id="e5b68-133">**.subsystem \<** *valore* **>**</span><span class="sxs-lookup"><span data-stu-id="e5b68-133">**.subsystem \<** *value* **>**</span></span>|<span data-ttu-id="e5b68-134">Specifica l'ambiente di applicazione necessario per il programma.</span><span class="sxs-lookup"><span data-stu-id="e5b68-134">Specifies the application environment required for the program.</span></span> <span data-ttu-id="e5b68-135">In questo esempio il valore 3 indica che il file eseguibile viene eseguito da una console.</span><span class="sxs-lookup"><span data-stu-id="e5b68-135">In this example, the value 3 indicates that this executable is run from a console.</span></span>|  
|<span data-ttu-id="e5b68-136">**.corflags**</span><span class="sxs-lookup"><span data-stu-id="e5b68-136">**.corflags**</span></span>|<span data-ttu-id="e5b68-137">Attualmente, campo riservato nei metadati.</span><span class="sxs-lookup"><span data-stu-id="e5b68-137">Currently a reserved field in the metadata.</span></span>|  
  
 <span data-ttu-id="e5b68-138">Il manifesto di un assembly può contenere diverse direttive, a seconda del contenuto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e5b68-138">An assembly manifest can contain a number of different directives, depending on the contents of the assembly.</span></span> <span data-ttu-id="e5b68-139">Per un elenco completo delle direttive del manifesto dell'assembly, vedere la documentazione ECMA, in particolare "Partition II: Metadata Definition and Semantics" (Partizione II: Definizione dei metadati e semantica) e "Partition III: CIL Instruction Set" (Partizione III: Set di istruzioni CIL).</span><span class="sxs-lookup"><span data-stu-id="e5b68-139">For an extensive list of the directives in the assembly manifest, see the ECMA documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="e5b68-140">La documentazione è disponibile online; vedere [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) (ECMA C# e standard di Common Language Infrastructure) in MSDN e [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) nel sito Web internazionale Ecma.</span><span class="sxs-lookup"><span data-stu-id="e5b68-140">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b68-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5b68-141">See Also</span></span>  
 [<span data-ttu-id="e5b68-142">Domini applicazione e assembly</span><span class="sxs-lookup"><span data-stu-id="e5b68-142">Application Domains and Assemblies</span></span>](https://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)  
 [<span data-ttu-id="e5b68-143">Argomenti relativi alle procedure per domini applicazione e assembly</span><span class="sxs-lookup"><span data-stu-id="e5b68-143">Application Domains and Assemblies How-to Topics</span></span>](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 [<span data-ttu-id="e5b68-144">Ildasm.exe (Disassembler IL)</span><span class="sxs-lookup"><span data-stu-id="e5b68-144">Ildasm.exe (IL Disassembler)</span></span>](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)
