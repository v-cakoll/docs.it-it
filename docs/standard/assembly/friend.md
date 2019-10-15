---
title: Assembly Friend
ms.date: 08/20/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
dev_langs:
- csharp
- vb
ms.openlocfilehash: 6387e93bcd4efeec57ada9228dcaf015d053dbf7
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70973236"
---
# <a name="friend-assemblies"></a><span data-ttu-id="05615-102">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="05615-102">Friend assemblies</span></span>

<span data-ttu-id="05615-103">Un *assembly Friend* può accedere ai tipi e ai membri [internal](../../csharp/language-reference/keywords/internal.md) (C#) o [Friend](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) di un altro assembly.</span><span class="sxs-lookup"><span data-stu-id="05615-103">A *friend assembly* is an assembly that can access another assembly's [internal](../../csharp/language-reference/keywords/internal.md) (C#) or [Friend](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) types and members.</span></span> <span data-ttu-id="05615-104">Se un assembly viene riconosciuto di tipo Friend, non è più necessario contrassegnare tipi e membri come pubblici perché altri assembly possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="05615-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="05615-105">Questo metodo è particolarmente utile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="05615-105">This is especially convenient in the following scenarios:</span></span>

- <span data-ttu-id="05615-106">Durante il testing unità, quando il codice di test viene eseguito in un assembly separato ma richiede l'accesso ai membri dell'assembly sottoposto a test che sono contrassegnati come `internal` in C# o come `Friend` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="05615-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

- <span data-ttu-id="05615-107">Quando si sviluppa una libreria di classi e le aggiunte alla libreria sono contenute in assembly separati ma richiedono l'accesso ai membri degli assembly esistenti che sono contrassegnati come `internal` in C# o come `Friend` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="05615-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

## <a name="remarks"></a><span data-ttu-id="05615-108">Note</span><span class="sxs-lookup"><span data-stu-id="05615-108">Remarks</span></span>

<span data-ttu-id="05615-109">È possibile usare l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per identificare uno o più assembly Friend per un determinato assembly.</span><span class="sxs-lookup"><span data-stu-id="05615-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="05615-110">Nell'esempio seguente viene usato <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> l'attributo nell' *assembly a* e viene specificato *AssemblyB* dell'assembly come assembly Friend.</span><span class="sxs-lookup"><span data-stu-id="05615-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in *Assembly A* and specifies assembly *AssemblyB* as a friend assembly.</span></span> <span data-ttu-id="05615-111">Questo consente all'assembly *AssemblyB* l'accesso a tutti i tipi e membri nell' *assembly a* contrassegnati `internal` come C# in `Friend` o in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="05615-111">This gives assembly *AssemblyB* access to all types and members in *Assembly A* that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

> [!NOTE]
> <span data-ttu-id="05615-112">Quando si compila un assembly come *AssemblyB* che accede ai tipi interni o ai membri interni di un altro assembly come *assembly A*, è necessario specificare in modo esplicito il nome del file di output (con*estensione exe* o *dll*) tramite **/out** opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="05615-112">When you compile an assembly like *AssemblyB* that will access internal types or internal members of another assembly like *Assembly A*, you must explicitly specify the name of the output file (*.exe* or *.dll*) by using the **/out** compiler option.</span></span> <span data-ttu-id="05615-113">Il compilatore non ha infatti ancora generato il nome dell'assembly in fase di compilazione quando crea l'associazione a riferimenti esterni.</span><span class="sxs-lookup"><span data-stu-id="05615-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="05615-114">Per altre informazioni, vedere [/out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [/out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="05615-114">For more information, see [/out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [/out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span></span>

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

<span data-ttu-id="05615-115">Solo gli assembly specificati in modo esplicito come Friends `internal` possonoC#accedere ai `Friend` tipi e ai membri () o (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="05615-115">Only assemblies that you explicitly specify as friends can access `internal` (C#) or `Friend` (Visual Basic) types and members.</span></span> <span data-ttu-id="05615-116">Ad esempio, se *AssemblyB* è un elemento Friend dell' *assembly a* e l' *assembly c* fa riferimento a *AssemblyB*, l' *assembly c* nonC#ha accesso `Friend` ai `internal` tipi () o (Visual Basic) nell' *assembly a* .</span><span class="sxs-lookup"><span data-stu-id="05615-116">For example, if *AssemblyB* is a friend of *Assembly A* and *Assembly C* references *AssemblyB*, *Assembly C* does not have access to `internal` (C#) or `Friend` (Visual Basic) types in *Assembly A*.</span></span>

<span data-ttu-id="05615-117">Il compilatore esegue alcune operazioni di convalida di base del nome dell'assembly Friend che viene passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="05615-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="05615-118">Se l' *assembly A* dichiara *AssemblyB* come assembly Friend, le regole di convalida sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="05615-118">If *Assembly A* declares *AssemblyB* as a friend assembly, the validation rules are as follows:</span></span>

- <span data-ttu-id="05615-119">Se *l'assembly A* è con nome sicuro, *AssemblyB* deve anche essere con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="05615-119">If *Assembly A* is strong named, *AssemblyB* must also be strong named.</span></span> <span data-ttu-id="05615-120">Il nome dell'assembly Friend che viene passato all'attributo deve essere costituito dal nome dell'assembly e dalla chiave pubblica della chiave con nome sicuro usata per firmare *AssemblyB*.</span><span class="sxs-lookup"><span data-stu-id="05615-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign *AssemblyB*.</span></span>

     <span data-ttu-id="05615-121">Il nome dell'assembly Friend passato all' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributo non può essere il nome sicuro *AssemblyB*.</span><span class="sxs-lookup"><span data-stu-id="05615-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of *AssemblyB*.</span></span> <span data-ttu-id="05615-122">Non includere la versione, le impostazioni cultura, l'architettura o il token di chiave pubblica dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="05615-122">Don't include the assembly version, culture, architecture, or public key token.</span></span>

- <span data-ttu-id="05615-123">Se l' *assembly A* non è con nome sicuro, il nome dell'assembly Friend deve essere costituito solo dal nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="05615-123">If *Assembly A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="05615-124">Per altre informazioni, vedere [Procedura: Creare assembly](create-unsigned-friend.md)Friend non firmati.</span><span class="sxs-lookup"><span data-stu-id="05615-124">For more information, see [How to: Create unsigned friend assemblies](create-unsigned-friend.md).</span></span>

- <span data-ttu-id="05615-125">Se *AssemblyB* è un nome sicuro, è necessario specificare la chiave con nome sicuro per *AssemblyB* usando l'impostazione del progetto o l'opzione del `/keyfile` compilatore da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="05615-125">If *AssemblyB* is strong named, you must specify the strong-name key for *AssemblyB* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="05615-126">Per altre informazioni, vedere [Procedura: Crea assembly](create-signed-friend.md)Friend firmati.</span><span class="sxs-lookup"><span data-stu-id="05615-126">For more information, see [How to: Create signed friend assemblies](create-signed-friend.md).</span></span>

 <span data-ttu-id="05615-127">La classe <xref:System.Security.Permissions.StrongNameIdentityPermission> consente anche la condivisione dei tipi, con le differenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="05615-127">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>

- <span data-ttu-id="05615-128"><xref:System.Security.Permissions.StrongNameIdentityPermission> si applica a un singolo tipo, mentre un assembly Friend si applica all'intero assembly.</span><span class="sxs-lookup"><span data-stu-id="05615-128"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>

- <span data-ttu-id="05615-129">Se sono presenti centinaia di tipi nell' *assembly a* che si desidera condividere con *AssemblyB*, è necessario aggiungerli <xref:System.Security.Permissions.StrongNameIdentityPermission> a tutti.</span><span class="sxs-lookup"><span data-stu-id="05615-129">If there are hundreds of types in *Assembly A* that you want to share with *AssemblyB*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="05615-130">Se invece si usa un assembly Friend, è sufficiente dichiarare una volta che si tratta di una relazione di tipo Friend.</span><span class="sxs-lookup"><span data-stu-id="05615-130">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>

- <span data-ttu-id="05615-131">Se si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, i tipi da condividere devono essere dichiarati come pubblici.</span><span class="sxs-lookup"><span data-stu-id="05615-131">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="05615-132">Se si usa un assembly Friend, i tipi condivisi vengono `internal` dichiaratiC#come () o `Friend` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="05615-132">If you use a friend assembly, the shared types are declared as `internal` (C#) or `Friend` (Visual Basic).</span></span>

<span data-ttu-id="05615-133">Per informazioni su come accedere ai tipi e ai `internal` metodiC#di un `Friend` assembly () o (Visual Basic) da un file di modulo (un file con estensione *netmodule* ), vedere [/moduleassemblynameC#()](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) o [/ moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span><span class="sxs-lookup"><span data-stu-id="05615-133">For information about how to access an assembly's `internal` (C#) or `Friend` (Visual Basic) types and methods from a module file (a file with the *.netmodule* extension), see [/moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) or [/moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="05615-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05615-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [<span data-ttu-id="05615-135">Procedura: Crea assembly Friend non firmati</span><span class="sxs-lookup"><span data-stu-id="05615-135">How to: Create unsigned friend assemblies</span></span>](create-unsigned-friend.md)
- [<span data-ttu-id="05615-136">Procedura: Crea assembly Friend firmati</span><span class="sxs-lookup"><span data-stu-id="05615-136">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="05615-137">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="05615-137">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="05615-138">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="05615-138">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="05615-139">Concetti di programmazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05615-139">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
