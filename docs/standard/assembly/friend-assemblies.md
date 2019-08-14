---
title: Assembly Friend (C#)
ms.date: 03/03/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
ms.openlocfilehash: 770eb70a5350d7d26e03cb4e605b442100da2a53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "68671196"
---
# <a name="friend-assemblies"></a><span data-ttu-id="651bf-102">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="651bf-102">Friend assemblies</span></span>

<span data-ttu-id="651bf-103">Un *assembly Friend* può accedere ai tipi e ai membri [internal](../../csharp/language-reference/keywords/internal.md) (in C# o [Friend](../../visual-basic/language-reference/modifiers/friend.md) in Visual Basic) di un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="651bf-103">A *friend assembly* is an assembly that can access another assembly's [internal](../../csharp/language-reference/keywords/internal.md) (in C# or [Friend](../../visual-basic/language-reference/modifiers/friend.md) in Visual Basic) types and members.</span></span> <span data-ttu-id="651bf-104">Se un assembly viene riconosciuto di tipo Friend, non è più necessario contrassegnare tipi e membri come pubblici perché altri assembly possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="651bf-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="651bf-105">Questo metodo è particolarmente utile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="651bf-105">This is especially convenient in the following scenarios:</span></span>

- <span data-ttu-id="651bf-106">Durante il testing unità, quando il codice di test viene eseguito in un assembly separato ma richiede l'accesso ai membri dell'assembly sottoposto a test che sono contrassegnati come `internal` in C# o come `Friend` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="651bf-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

- <span data-ttu-id="651bf-107">Quando si sviluppa una libreria di classi e le aggiunte alla libreria sono contenute in assembly separati ma richiedono l'accesso ai membri degli assembly esistenti che sono contrassegnati come `internal` in C# o come `Friend` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="651bf-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

## <a name="remarks"></a><span data-ttu-id="651bf-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="651bf-108">Remarks</span></span>

<span data-ttu-id="651bf-109">È possibile usare l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per identificare uno o più assembly Friend per un determinato assembly.</span><span class="sxs-lookup"><span data-stu-id="651bf-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="651bf-110">L'esempio seguente usa l'attributo `AssemblyB` nell'assembly A e specifica l'assembly <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> come assembly Friend.</span><span class="sxs-lookup"><span data-stu-id="651bf-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="651bf-111">In questo modo l'assembly `AssemblyB` può accedere a tutti i tipi e i membri dell'assembly A che sono contrassegnati come `internal` in C# o come `Friend` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="651bf-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

> [!NOTE]
> <span data-ttu-id="651bf-112">Quando si compila un assembly (assembly `AssemblyB`) che deve accedere ai tipi o ai membri interni di un altro assembly (assembly *A*), è necessario specificare in modo esplicito il nome del file di output (con estensione exe o dll) usando l'opzione del compilatore **/out**.</span><span class="sxs-lookup"><span data-stu-id="651bf-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="651bf-113">Il compilatore non ha infatti ancora generato il nome dell'assembly in fase di compilazione quando crea l'associazione a riferimenti esterni.</span><span class="sxs-lookup"><span data-stu-id="651bf-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="651bf-114">Per altre informazioni, vedere [/out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [/out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="651bf-114">For more information, see [/out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [/out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="651bf-115">C#</span><span class="sxs-lookup"><span data-stu-id="651bf-115">C#</span></span>](#tab/csharp)

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

# <a name="visual-basictabvb"></a>[<span data-ttu-id="651bf-116">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="651bf-116">Visual Basic</span></span>](#tab/vb)

```vb
Imports System.Runtime.CompilerServices
Imports System
<Assembly: InternalsVisibleTo("AssemblyB")>

' Friend class.
Friend Class FriendClass
    Public Sub Test()
        Console.WriteLine("Sample Class")
    End Sub
End Class

' Public class with a Friend method.
Public Class ClassWithFriendMethod
    Friend Sub Test()
        Console.WriteLine("Sample Method")
    End Sub
End Class
```

---

<span data-ttu-id="651bf-117">Solo gli assembly che sono stati definiti come Friend in modo esplicito possono accedere ai tipi e ai membri `internal` (in C# o `Friend` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="651bf-117">Only assemblies that you explicitly specify as friends can access `internal` (in C# or `Friend` in Visual Basic) types and members.</span></span> <span data-ttu-id="651bf-118">Se, ad esempio, l'assembly B è un elemento di tipo Friend per l'assembly A e l'assembly C fa riferimento all'assembly B, l'assembly C non può accedere ai tipi `internal` (in C# o `Friend` in Visual Basic) in A.</span><span class="sxs-lookup"><span data-stu-id="651bf-118">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `internal` (in C# or `Friend` in Visual Basic) types in A.</span></span>

<span data-ttu-id="651bf-119">Il compilatore esegue alcune operazioni di convalida di base del nome dell'assembly Friend che viene passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="651bf-119">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="651bf-120">Se l'assembly *A* dichiara che *B* è un assembly Friend, le regole di convalida sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="651bf-120">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>

- <span data-ttu-id="651bf-121">Se *A* è un assembly con nome sicuro, anche *B* deve essere un assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="651bf-121">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="651bf-122">Il nome dell'assembly Friend passato all'attributo deve includere il nome dell'assembly e la chiave pubblica della chiave con nome sicuro usata per firmare l'assembly *B*.</span><span class="sxs-lookup"><span data-stu-id="651bf-122">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>

     <span data-ttu-id="651bf-123">Il nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> non può essere il nome sicuro dell'assembly *B*. Non includere la versione dell'assembly, le impostazioni cultura, l'architettura o il token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="651bf-123">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>

- <span data-ttu-id="651bf-124">Se *A* non è un assembly con nome sicuro, il nome dell'assembly Friend deve comprendere solo il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="651bf-124">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="651bf-125">Per altre informazioni, vedere [Procedura: Creare assembly Friend non firmati (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) oppure [Procedura: Creare assembly Friend non firmati (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="651bf-125">For more information, see [How to: Create Unsigned Friend Assemblies (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) or [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>

- <span data-ttu-id="651bf-126">Se *B* è un assembly con nome sicuro, è necessario specificare la chiave con nome sicuro per l'assembly *B* usando l'impostazione di progetto o l'opzione del compilatore `/keyfile` della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="651bf-126">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="651bf-127">Per altre informazioni, vedere [Procedura: Creare assembly Friend firmati (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) oppure [Procedura: Creare assembly Friend firmati (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="651bf-127">For more information, see [How to: Create Signed Friend Assemblies (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) or [How to: Create Signed Friend Assemblies (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>

 <span data-ttu-id="651bf-128">La classe <xref:System.Security.Permissions.StrongNameIdentityPermission> consente anche la condivisione dei tipi, con le differenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="651bf-128">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>

- <span data-ttu-id="651bf-129"><xref:System.Security.Permissions.StrongNameIdentityPermission> si applica a un singolo tipo, mentre un assembly Friend si applica all'intero assembly.</span><span class="sxs-lookup"><span data-stu-id="651bf-129"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>

- <span data-ttu-id="651bf-130">Se un assembly *A* contiene centinaia di tipi che si vuole condividere con l'assembly *B*, è necessario aggiungere <xref:System.Security.Permissions.StrongNameIdentityPermission> a tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="651bf-130">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="651bf-131">Se invece si usa un assembly Friend, è sufficiente dichiarare una volta che si tratta di una relazione di tipo Friend.</span><span class="sxs-lookup"><span data-stu-id="651bf-131">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>

- <span data-ttu-id="651bf-132">Se si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, i tipi da condividere devono essere dichiarati come pubblici.</span><span class="sxs-lookup"><span data-stu-id="651bf-132">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="651bf-133">Se si usa un assembly Friend, i tipi condivisi vengono dichiarati come `internal` (in C# o come `Friend` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="651bf-133">If you use a friend assembly, the shared types are declared as `internal` (in C# or `Friend` in Visual Basic).</span></span>

<span data-ttu-id="651bf-134">Per informazioni su come accedere ai tipi e ai metodi `internal` (in C# o `Friend` in Visual Basic) di un assembly da un file di modulo, ovvero un file con estensione netmodule, vedere [/moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) o [/moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span><span class="sxs-lookup"><span data-stu-id="651bf-134">For information about how to access an assembly's `internal` (in C# or `Friend` in Visual Basic) types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) or [/moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="651bf-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="651bf-135">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [<span data-ttu-id="651bf-136">Procedura: Creare assembly Friend non firmati (C#)</span><span class="sxs-lookup"><span data-stu-id="651bf-136">How to: Create Unsigned Friend Assemblies (C#)</span></span>](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="651bf-137">Procedura: Creare assembly Friend non firmati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="651bf-137">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="651bf-138">Procedura: Creare assembly Friend firmati (C#)</span><span class="sxs-lookup"><span data-stu-id="651bf-138">How to: Create Signed Friend Assemblies (C#)</span></span>](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [<span data-ttu-id="651bf-139">Procedura: Creare assembly Friend firmati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="651bf-139">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [<span data-ttu-id="651bf-140">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="651bf-140">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="651bf-141">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="651bf-141">C# Programming Guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="651bf-142">Nozioni di base sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="651bf-142">Programming Concepts</span></span>](../../visual-basic/programming-guide/concepts/index.md)
