---
title: Assembly Friend (C#)
ms.date: 07/20/2015
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
ms.openlocfilehash: e464162f12fe386c37262753331635ea82b128b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576980"
---
# <a name="friend-assemblies-c"></a><span data-ttu-id="d61d8-102">Assembly Friend (C#)</span><span class="sxs-lookup"><span data-stu-id="d61d8-102">Friend Assemblies (C#)</span></span>
<span data-ttu-id="d61d8-103">Un *assembly Friend* può accedere ai tipi e ai membri [interni](../../../../csharp/language-reference/keywords/internal.md) di un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="d61d8-103">A *friend assembly* is an assembly that can access another assembly's [internal](../../../../csharp/language-reference/keywords/internal.md) types and members.</span></span> <span data-ttu-id="d61d8-104">Se un assembly viene riconosciuto di tipo Friend, non è più necessario contrassegnare tipi e membri come pubblici perché altri assembly possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="d61d8-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="d61d8-105">Questo metodo è particolarmente utile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="d61d8-105">This is especially convenient in the following scenarios:</span></span>  
  
-   <span data-ttu-id="d61d8-106">Durante il test dell'unità, quando il codice di test eseguito in un assembly separato deve accedere ai membri nell'assembly sottoposto a test che sono contrassegnati come `internal`.</span><span class="sxs-lookup"><span data-stu-id="d61d8-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `internal` .</span></span>  
  
-   <span data-ttu-id="d61d8-107">Quando si sviluppa una libreria di classi e le aggiunte alla libreria sono contenute in assembly separati che devono accedere ai membri negli assembly esistenti che sono contrassegnati come `internal` .</span><span class="sxs-lookup"><span data-stu-id="d61d8-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `internal` .</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d61d8-108">Note</span><span class="sxs-lookup"><span data-stu-id="d61d8-108">Remarks</span></span>  
 <span data-ttu-id="d61d8-109">È possibile usare l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per identificare uno o più assembly Friend per un determinato assembly.</span><span class="sxs-lookup"><span data-stu-id="d61d8-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="d61d8-110">L'esempio seguente usa l'attributo `AssemblyB` nell'assembly A e specifica l'assembly <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> come assembly Friend.</span><span class="sxs-lookup"><span data-stu-id="d61d8-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="d61d8-111">In questo modo l'assembly `AssemblyB` può accedere a tutti i tipi e i membri nell'assembly A che sono contrassegnati come `internal`.</span><span class="sxs-lookup"><span data-stu-id="d61d8-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `internal`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d61d8-112">Quando si compila un assembly (assembly `AssemblyB`) che deve accedere ai tipi o ai membri interni di un altro assembly (assembly *A*), è necessario specificare in modo esplicito il nome del file di output (con estensione exe o dll) usando l'opzione del compilatore **/out**.</span><span class="sxs-lookup"><span data-stu-id="d61d8-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="d61d8-113">Il compilatore non ha infatti ancora generato il nome dell'assembly in fase di compilazione quando crea l'associazione a riferimenti esterni.</span><span class="sxs-lookup"><span data-stu-id="d61d8-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="d61d8-114">Per altre informazioni, vedere [/out (C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="d61d8-114">For more information, see [/out (C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) .</span></span>  
  
```csharp  
using System.Runtime.CompilerServices;  
using System;  
  
[assembly: InternalsVisibleTo("AssemblyB")]  
  
// The class is internal by default.  
class FriendClass  
{  
    public void Test()  
    {  
        Console.WriteLine("Sample Class");  
    }  
}  
  
// Public class that has an internal method.  
public class ClassWithFriendMethod  
{  
    internal void Test()  
    {  
        Console.WriteLine("Sample Method");  
    }  
  
}  
```  
  
 <span data-ttu-id="d61d8-115">Possono accedere ai tipi e ai membri `internal` solo gli assembly che sono stati definiti di tipo Friend in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="d61d8-115">Only assemblies that you explicitly specify as friends can access `internal` types and members.</span></span> <span data-ttu-id="d61d8-116">Ad esempio, se l'assembly B è un elemento di tipo Friend per l'assembly A e l'assembly C fa riferimento all'assembly B, l'assembly C non può accedere ai tipi `internal` in A.</span><span class="sxs-lookup"><span data-stu-id="d61d8-116">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `internal` types in A.</span></span>  
  
 <span data-ttu-id="d61d8-117">Il compilatore esegue alcune operazioni di convalida di base del nome dell'assembly Friend che viene passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d61d8-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="d61d8-118">Se l'assembly *A* dichiara che *B* è un assembly Friend, le regole di convalida sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="d61d8-118">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>  
  
-   <span data-ttu-id="d61d8-119">Se *A* è un assembly con nome sicuro, anche *B* deve essere un assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="d61d8-119">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="d61d8-120">Il nome dell'assembly Friend passato all'attributo deve includere il nome dell'assembly e la chiave pubblica della chiave con nome sicuro usata per firmare l'assembly *B*.</span><span class="sxs-lookup"><span data-stu-id="d61d8-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>  
  
     <span data-ttu-id="d61d8-121">Il nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> non può essere il nome sicuro dell'assembly *B*. Non includere la versione dell'assembly, le impostazioni cultura, l'architettura o il token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="d61d8-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>  
  
-   <span data-ttu-id="d61d8-122">Se *A* non è un assembly con nome sicuro, il nome dell'assembly Friend deve comprendere solo il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="d61d8-122">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="d61d8-123">Per altre informazioni, vedere [Procedura: Creare assembly Friend non firmati (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="d61d8-123">For more information, see [How to: Create Unsigned Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>  
  
-   <span data-ttu-id="d61d8-124">Se *B* è un assembly con nome sicuro, è necessario specificare la chiave con nome sicuro per l'assembly *B* usando l'impostazione di progetto o l'opzione del compilatore `/keyfile` della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d61d8-124">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="d61d8-125">Per altre informazioni, vedere [Procedura: Creare assembly Friend firmati (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="d61d8-125">For more information, see [How to: Create Signed Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="d61d8-126">La classe <xref:System.Security.Permissions.StrongNameIdentityPermission> consente anche la condivisione dei tipi, con le differenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="d61d8-126">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>  
  
-   <span data-ttu-id="d61d8-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> si applica a un singolo tipo, mentre un assembly Friend si applica all'intero assembly.</span><span class="sxs-lookup"><span data-stu-id="d61d8-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>  
  
-   <span data-ttu-id="d61d8-128">Se un assembly *A* contiene centinaia di tipi che si vuole condividere con l'assembly *B*, è necessario aggiungere <xref:System.Security.Permissions.StrongNameIdentityPermission> a tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="d61d8-128">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="d61d8-129">Se invece si usa un assembly Friend, è sufficiente dichiarare una volta che si tratta di una relazione di tipo Friend.</span><span class="sxs-lookup"><span data-stu-id="d61d8-129">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>  
  
-   <span data-ttu-id="d61d8-130">Se si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, i tipi da condividere devono essere dichiarati come pubblici.</span><span class="sxs-lookup"><span data-stu-id="d61d8-130">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="d61d8-131">Se si usa un assembly Friend, i tipi condivisi vengono dichiarati `internal`.</span><span class="sxs-lookup"><span data-stu-id="d61d8-131">If you use a friend assembly, the shared types are declared as `internal`.</span></span>  
  
 <span data-ttu-id="d61d8-132">Per informazioni su come accedere ai tipi e ai metodi `internal` di un assembly da un file di modulo, vale a dire un file con estensione netmodule, vedere [/moduleassemblyname (C#)](../../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="d61d8-132">For information about how to access an assembly's `internal` types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (C#)](../../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d61d8-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d61d8-133">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [<span data-ttu-id="d61d8-134">Procedura: Creare assembly Friend non firmati (C#)</span><span class="sxs-lookup"><span data-stu-id="d61d8-134">How to: Create Unsigned Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="d61d8-135">Procedura: Creare assembly Friend firmati (C#)</span><span class="sxs-lookup"><span data-stu-id="d61d8-135">How to: Create Signed Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [<span data-ttu-id="d61d8-136">Assembly e Global Assembly Cache (C#)</span><span class="sxs-lookup"><span data-stu-id="d61d8-136">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)
- [<span data-ttu-id="d61d8-137">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="d61d8-137">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
