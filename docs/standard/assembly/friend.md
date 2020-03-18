---
title: Assembly Friend
ms.date: 08/20/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
dev_langs:
- csharp
- vb
ms.openlocfilehash: a74d4b74ead8492028a092e090f9281231802a87
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348171"
---
# <a name="friend-assemblies"></a>Assembly Friend

Un *assembly Friend* è un assembly che può accedere ai tipi e ai membri [interni](../../csharp/language-reference/keywords/internal.md) di un altro assembly (C) o [Friend](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic). Se un assembly viene riconosciuto di tipo Friend, non è più necessario contrassegnare tipi e membri come pubblici perché altri assembly possano accedervi. Questo metodo è particolarmente utile negli scenari seguenti:

- Durante il testing unità, quando il codice di test viene eseguito in un assembly separato ma richiede l'accesso ai membri dell'assembly sottoposto a test che sono contrassegnati come `internal` in C# o come `Friend` in Visual Basic.

- Quando si sviluppa una libreria di classi e le aggiunte alla libreria sono contenute in assembly separati ma richiedono l'accesso ai membri degli assembly esistenti che sono contrassegnati come `internal` in C# o come `Friend` in Visual Basic.

## <a name="remarks"></a>Osservazioni

È possibile usare l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per identificare uno o più assembly Friend per un determinato assembly. Nell'esempio riportato di seguito viene utilizzato l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> *nell'assembly A* e viene specificato l'assembly *AssemblyB* come assembly Friend. In questo modo l'assembly *AssemblyB* può accedere a `internal` tutti i `Friend` tipi e membri *nell'assembly A* contrassegnati come in C , o in Visual Basic.

> [!NOTE]
> Quando si compila un assembly come *AssemblyB* che accederà a tipi interni o ai membri interni di un altro assembly, ad esempio *Assembly A*, è necessario specificare in modo esplicito il nome del file di output (*exe* o *dll*) utilizzando l'opzione del compilatore **-out** . Il compilatore non ha infatti ancora generato il nome dell'assembly in fase di compilazione quando crea l'associazione a riferimenti esterni. Per ulteriori informazioni, vedere [-out (C')](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).

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

Solo gli assembly specificati in `internal` modo esplicito `Friend` come friend possono accedere ai tipi e ai membri (C) o (Visual Basic). Se, ad esempio, *AssemblyB* è un friend *dell'Assembly A* e *dell'Assembly C* fa riferimento ad *AssemblyB*, *l'Assembly C* non ha accesso ai `internal` tipi (C) o `Friend` (Visual Basic) *nell'assembly A*.

Il compilatore esegue alcune operazioni di convalida di base del nome dell'assembly Friend che viene passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Se *l'assembly A* dichiara *AssemblyB* come assembly Friend, le regole di convalida sono le seguenti:

- Se *l'assieme A* è denominato con nome sicuro, anche *AssemblyB* deve avere un nome sicuro. Il nome dell'assembly Friend passato all'attributo deve essere costituito dal nome dell'assembly e dalla chiave pubblica della chiave con nome sicuro utilizzata per firmare *AssemblyB*.

     Il nome dell'assembly Friend <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> passato all'attributo non può essere il nome sicuro di *AssemblyB*. Non includere la versione dell'assembly, le impostazioni cultura, l'architettura o il token di chiave pubblica.

- Se *l'assembly A* non è denominato come sicuro, il nome dell'assembly Friend deve essere costituito solo dal nome dell'assembly. Per ulteriori informazioni, vedere [Procedura: creare assembly friend non firmati](create-unsigned-friend.md).

- Se *AssemblyB* ha un nome sicuro, è necessario specificare la chiave con nome `/keyfile` sicuro per *AssemblyB* utilizzando l'impostazione di progetto o l'opzione del compilatore da riga di comando. Per ulteriori informazioni, vedere [Procedura: creare assembly Friend firmati](create-signed-friend.md).

 La classe <xref:System.Security.Permissions.StrongNameIdentityPermission> consente anche la condivisione dei tipi, con le differenze seguenti:

- <xref:System.Security.Permissions.StrongNameIdentityPermission> si applica a un singolo tipo, mentre un assembly Friend si applica all'intero assembly.

- Se *nell'assembly A* sono presenti centinaia di tipi che si <xref:System.Security.Permissions.StrongNameIdentityPermission> desidera condividere con *AssemblyB*, è necessario aggiungerli tutti. Se invece si usa un assembly Friend, è sufficiente dichiarare una volta che si tratta di una relazione di tipo Friend.

- Se si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, i tipi da condividere devono essere dichiarati come pubblici. Se si utilizza un assembly Friend, `internal` i tipi condivisi `Friend` vengono dichiarati come (C) o (Visual Basic).

Per informazioni su come accedere `internal` ai tipi `Friend` e ai metodi di un assembly (C) o (Visual Basic) da un file di modulo (un file con estensione *.netmodule),* vedere [-moduleassemblyname (C'è)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) o [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [Procedura: creare assembly friend non firmatiHow to: Create unsigned Friend assemblies](create-unsigned-friend.md)
- [Procedura: creare assembly friend firmatiHow to: Create signed friend assemblies](create-signed-friend.md)
- [Assembly in .NET](index.md)
- [Guida alla programmazione in C](../../csharp/programming-guide/index.md)
- [Concetti di programmazione (Visual Basic)Programming concepts (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
