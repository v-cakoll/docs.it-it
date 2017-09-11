---
title: -moduleassemblyname (opzione del compilatore C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /moduleassemblyname
dev_langs:
- CSharp
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
caps.latest.revision: 10
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
ms.openlocfilehash: 2522609aa41ad944b37a8882c1cc56cd5967b330
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="moduleassemblyname-c-compiler-option"></a><span data-ttu-id="74d42-102">/moduleassemblyname (opzione del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="74d42-102">/moduleassemblyname (C# Compiler Option)</span></span>
<span data-ttu-id="74d42-103">Specifica l'assembly i cui tipi non pubblici sono accessibili da un file con estensione NETMODULE.</span><span class="sxs-lookup"><span data-stu-id="74d42-103">Specifies an assembly whose non-public types a .netmodule can access.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74d42-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74d42-104">Syntax</span></span>  
  
```console  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="74d42-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="74d42-105">Arguments</span></span>  
 `assembly_name`  
 <span data-ttu-id="74d42-106">Nome dell'assembly i cui tipi non pubblici sono accessibili dal file con estensione netmodule.</span><span class="sxs-lookup"><span data-stu-id="74d42-106">The name of the assembly whose non-public types the .netmodule can access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74d42-107">Note</span><span class="sxs-lookup"><span data-stu-id="74d42-107">Remarks</span></span>  
 <span data-ttu-id="74d42-108">**/moduleassemblyname** deve essere usato quando si compila un file con estensione netmodule e vengono soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="74d42-108">**/moduleassemblyname** should be used when building a .netmodule, and where the following conditions are true:</span></span>  
  
-   <span data-ttu-id="74d42-109">Tramite il file con estensione netmodule deve essere possibile accedere a tipi non pubblici in un assembly esistente.</span><span class="sxs-lookup"><span data-stu-id="74d42-109">The .netmodule needs access to non-public types in an existing assembly.</span></span>  
  
-   <span data-ttu-id="74d42-110">L'utente conosce il nome dell'assembly in cui verrà compilato il file con estensione netmodule.</span><span class="sxs-lookup"><span data-stu-id="74d42-110">You know the name of the assembly into which the .netmodule will be built.</span></span>  
  
-   <span data-ttu-id="74d42-111">L'assembly esistente ha concesso l'accesso assembly Friend all'assembly in cui verrà compilato il file con estensione netmodule.</span><span class="sxs-lookup"><span data-stu-id="74d42-111">The existing assembly has granted friend assembly access to the assembly into which the .netmodule will be built.</span></span>  
  
 <span data-ttu-id="74d42-112">Per altre informazioni sulla compilazione di un file con estensione netmodule, vedere [/target:module (opzione del compilatore C#)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="74d42-112">For more information on building a .netmodule, see [/target:module (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="74d42-113">Per altre informazioni sugli assembly Friend, vedere [Assembly Friend ](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span><span class="sxs-lookup"><span data-stu-id="74d42-113">For more information on friend assemblies, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
 <span data-ttu-id="74d42-114">L'opzione non è disponibile all'interno dell'ambiente di sviluppo, ma soltanto durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="74d42-114">This option is not available from within the development environment; it is only available when compiling from the command line.</span></span>  
  
 <span data-ttu-id="74d42-115">Questa opzione del compilatore non è disponibile in Visual Studio e non può essere modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="74d42-115">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74d42-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="74d42-116">Example</span></span>  
 <span data-ttu-id="74d42-117">In questo esempio viene generato un assembly con un tipo privato e viene concesso all'assembly Friend l'accesso a un assembly denominato csman_an_assembly.</span><span class="sxs-lookup"><span data-stu-id="74d42-117">This sample builds an assembly with a private type, and that gives friend assembly access to an assembly called csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: /target:library  
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
  
## <a name="example"></a><span data-ttu-id="74d42-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="74d42-118">Example</span></span>  
 <span data-ttu-id="74d42-119">In questo esempio viene compilato un file con estensione netmodule tramite cui si accede a un tipo non pubblico nel file moduleassemblyname_1.dll dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="74d42-119">This sample builds a .netmodule that accesses a non-public type in the assembly moduleassemblyname_1.dll.</span></span> <span data-ttu-id="74d42-120">Sapendo che questo file con estensione netmodule verrà compilato in un assembly denominato csman_an_assembly, è possibile specificare **/moduleassemblyname** per consentire al file con estensione netmodule di accedere a tipi non pubblici nell'assembly che ha concesso all'assembly Friend l'accesso a csman_an_assembly.</span><span class="sxs-lookup"><span data-stu-id="74d42-120">By knowing that this .netmodule will be built into an assembly called csman_an_assembly, we can specify **/moduleassemblyname**, allowing the .netmodule to access non-public types in an assembly that has granted friend assembly access to csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: /moduleassemblyname:csman_an_assembly /target:module /reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="74d42-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="74d42-121">Example</span></span>  
 <span data-ttu-id="74d42-122">In questo esempio di codice viene compilato l'assembly csman_an_assembly, facendo riferimento all'assembly e al file con estensione netmodule compilati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="74d42-122">This code sample builds the assembly csman_an_assembly, referencing the previously-built assembly and .netmodule.</span></span>  
  
```csharp  
// csman_an_assembly.cs  
// compile with: /addmodule:moduleassemblyname_2.netmodule /reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
 <span data-ttu-id="74d42-123">**An_Internal_Class.Test called**</span><span class="sxs-lookup"><span data-stu-id="74d42-123">**An_Internal_Class.Test called**</span></span>   
## <a name="see-also"></a><span data-ttu-id="74d42-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74d42-124">See Also</span></span>  
 <span data-ttu-id="74d42-125">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)  (Opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="74d42-125">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="74d42-126">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="74d42-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

