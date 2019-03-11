---
title: -moduleassemblyname (opzione del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /moduleassemblyname
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
ms.openlocfilehash: 7d39840f3b12df621a0e8d5fae5725065c295e59
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361265"
---
# <a name="-moduleassemblyname-c-compiler-option"></a><span data-ttu-id="f01c6-102">-moduleassemblyname (opzione del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="f01c6-102">-moduleassemblyname (C# Compiler Option)</span></span>
<span data-ttu-id="f01c6-103">Specifica l'assembly i cui tipi non pubblici sono accessibili da un file con estensione NETMODULE.</span><span class="sxs-lookup"><span data-stu-id="f01c6-103">Specifies an assembly whose non-public types a .netmodule can access.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f01c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f01c6-104">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="f01c6-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f01c6-105">Arguments</span></span>  
 `assembly_name`  
 <span data-ttu-id="f01c6-106">Nome dell'assembly i cui tipi non pubblici sono accessibili dal file con estensione netmodule.</span><span class="sxs-lookup"><span data-stu-id="f01c6-106">The name of the assembly whose non-public types the .netmodule can access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f01c6-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f01c6-107">Remarks</span></span>  
 <span data-ttu-id="f01c6-108">È necessario usare **-moduleassemblyname** quando si compila un file con estensione netmodule, se sono soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f01c6-108">**-moduleassemblyname** should be used when building a .netmodule, and where the following conditions are true:</span></span>  
  
-   <span data-ttu-id="f01c6-109">Tramite il file con estensione netmodule deve essere possibile accedere a tipi non pubblici in un assembly esistente.</span><span class="sxs-lookup"><span data-stu-id="f01c6-109">The .netmodule needs access to non-public types in an existing assembly.</span></span>  
  
-   <span data-ttu-id="f01c6-110">L'utente conosce il nome dell'assembly in cui verrà compilato il file con estensione netmodule.</span><span class="sxs-lookup"><span data-stu-id="f01c6-110">You know the name of the assembly into which the .netmodule will be built.</span></span>  
  
-   <span data-ttu-id="f01c6-111">L'assembly esistente ha concesso l'accesso assembly Friend all'assembly in cui verrà compilato il file con estensione netmodule.</span><span class="sxs-lookup"><span data-stu-id="f01c6-111">The existing assembly has granted friend assembly access to the assembly into which the .netmodule will be built.</span></span>  
  
 <span data-ttu-id="f01c6-112">Per altre informazioni sulla compilazione di un file con estensione netmodule, vedere [-target:module (opzione del compilatore C#)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f01c6-112">For more information on building a .netmodule, see [-target:module (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="f01c6-113">Per altre informazioni sugli assembly Friend, vedere [Assembly Friend ](../../../standard/assembly/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="f01c6-113">For more information on friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="f01c6-114">L'opzione non è disponibile all'interno dell'ambiente di sviluppo, ma soltanto durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f01c6-114">This option is not available from within the development environment; it is only available when compiling from the command line.</span></span>  
  
 <span data-ttu-id="f01c6-115">Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="f01c6-115">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f01c6-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="f01c6-116">Example</span></span>  
 <span data-ttu-id="f01c6-117">In questo esempio viene generato un assembly con un tipo privato e viene concesso all'assembly Friend l'accesso a un assembly denominato csman_an_assembly.</span><span class="sxs-lookup"><span data-stu-id="f01c6-117">This sample builds an assembly with a private type, and that gives friend assembly access to an assembly called csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: -target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class   
{  
    public void Test()   
    {   
        Console.WriteLine("An_Internal_Class.Test called");   
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="f01c6-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="f01c6-118">Example</span></span>  
 <span data-ttu-id="f01c6-119">In questo esempio viene compilato un file con estensione netmodule tramite cui si accede a un tipo non pubblico nel file moduleassemblyname_1.dll dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f01c6-119">This sample builds a .netmodule that accesses a non-public type in the assembly moduleassemblyname_1.dll.</span></span> <span data-ttu-id="f01c6-120">Sapendo che questo file con estensione netmodule verrà compilato in un assembly denominato csman_an_assembly, è possibile specificare **-moduleassemblyname** per consentire al file con estensione netmodule di accedere a tipi non pubblici nell'assembly che ha concesso all'assembly Friend l'accesso a csman_an_assembly.</span><span class="sxs-lookup"><span data-stu-id="f01c6-120">By knowing that this .netmodule will be built into an assembly called csman_an_assembly, we can specify **-moduleassemblyname**, allowing the .netmodule to access non-public types in an assembly that has granted friend assembly access to csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: -moduleassemblyname:csman_an_assembly -target:module -reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="f01c6-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="f01c6-121">Example</span></span>  
 <span data-ttu-id="f01c6-122">In questo esempio di codice viene compilato l'assembly csman_an_assembly, facendo riferimento all'assembly e al file con estensione netmodule compilati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f01c6-122">This code sample builds the assembly csman_an_assembly, referencing the previously-built assembly and .netmodule.</span></span>  
  
```csharp  
// csman_an_assembly.cs  
// compile with: -addmodule:moduleassemblyname_2.netmodule -reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
<span data-ttu-id="f01c6-123">**An_Internal_Class.Test called**</span><span class="sxs-lookup"><span data-stu-id="f01c6-123">**An_Internal_Class.Test called**</span></span>

## <a name="see-also"></a><span data-ttu-id="f01c6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f01c6-124">See also</span></span>

- [<span data-ttu-id="f01c6-125">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="f01c6-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="f01c6-126">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="f01c6-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
