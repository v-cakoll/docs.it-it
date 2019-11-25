---
title: Assembly Friend
ms.date: 08/20/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
dev_langs:
- csharp
- vb
ms.openlocfilehash: a74d4b74ead8492028a092e090f9281231802a87
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348171"
---
# <a name="friend-assemblies"></a>Assembly Friend

A *friend assembly* is an assembly that can access another assembly's [internal](../../csharp/language-reference/keywords/internal.md) (C#) or [Friend](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) types and members. Se un assembly viene riconosciuto di tipo Friend, non è più necessario contrassegnare tipi e membri come pubblici perché altri assembly possano accedervi. Questo metodo è particolarmente utile negli scenari seguenti:

- Durante il testing unità, quando il codice di test viene eseguito in un assembly separato ma richiede l'accesso ai membri dell'assembly sottoposto a test che sono contrassegnati come `internal` in C# o come `Friend` in Visual Basic.

- Quando si sviluppa una libreria di classi e le aggiunte alla libreria sono contenute in assembly separati ma richiedono l'accesso ai membri degli assembly esistenti che sono contrassegnati come `internal` in C# o come `Friend` in Visual Basic.

## <a name="remarks"></a>Note

È possibile usare l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per identificare uno o più assembly Friend per un determinato assembly. The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in *Assembly A* and specifies assembly *AssemblyB* as a friend assembly. This gives assembly *AssemblyB* access to all types and members in *Assembly A* that are marked as `internal` in C# or `Friend` in Visual Basic.

> [!NOTE]
> When you compile an assembly like *AssemblyB* that will access internal types or internal members of another assembly like *Assembly A*, you must explicitly specify the name of the output file ( *.exe* or *.dll*) by using the **-out** compiler option. Il compilatore non ha infatti ancora generato il nome dell'assembly in fase di compilazione quando crea l'associazione a riferimenti esterni. For more information, see [-out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).

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

Only assemblies that you explicitly specify as friends can access `internal` (C#) or `Friend` (Visual Basic) types and members. For example, if *AssemblyB* is a friend of *Assembly A* and *Assembly C* references *AssemblyB*, *Assembly C* does not have access to `internal` (C#) or `Friend` (Visual Basic) types in *Assembly A*.

Il compilatore esegue alcune operazioni di convalida di base del nome dell'assembly Friend che viene passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. If *Assembly A* declares *AssemblyB* as a friend assembly, the validation rules are as follows:

- If *Assembly A* is strong named, *AssemblyB* must also be strong named. The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign *AssemblyB*.

     The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of *AssemblyB*. Don't include the assembly version, culture, architecture, or public key token.

- If *Assembly A* is not strong named, the friend assembly name should consist of only the assembly name. For more information, see [How to: Create unsigned friend assemblies](create-unsigned-friend.md).

- If *AssemblyB* is strong named, you must specify the strong-name key for *AssemblyB* by using the project setting or the command-line `/keyfile` compiler option. For more information, see [How to: Create signed friend assemblies](create-signed-friend.md).

 La classe <xref:System.Security.Permissions.StrongNameIdentityPermission> consente anche la condivisione dei tipi, con le differenze seguenti:

- <xref:System.Security.Permissions.StrongNameIdentityPermission> si applica a un singolo tipo, mentre un assembly Friend si applica all'intero assembly.

- If there are hundreds of types in *Assembly A* that you want to share with *AssemblyB*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them. Se invece si usa un assembly Friend, è sufficiente dichiarare una volta che si tratta di una relazione di tipo Friend.

- Se si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, i tipi da condividere devono essere dichiarati come pubblici. If you use a friend assembly, the shared types are declared as `internal` (C#) or `Friend` (Visual Basic).

For information about how to access an assembly's `internal` (C#) or `Friend` (Visual Basic) types and methods from a module file (a file with the *.netmodule* extension), see [-moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) or [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [How to: Create unsigned friend assemblies](create-unsigned-friend.md)
- [How to: Create signed friend assemblies](create-signed-friend.md)
- [Assembly in .NET](index.md)
- [Guida per programmatori C#](../../csharp/programming-guide/index.md)
- [Programming concepts (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
