---
title: Assembly Friend
description: Un assembly Friend è un assembly .NET che può accedere ai tipi e ai membri interni (C#) o Friend (Visual Basic) di un altro assembly.
ms.date: 08/20/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
dev_langs:
- csharp
- vb
ms.openlocfilehash: 105621da2bd418c6294fa2bbec474809599cb6a5
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378925"
---
# <a name="friend-assemblies"></a>Assembly Friend

Un *assembly Friend* è un assembly che può accedere ai tipi e ai membri [interni](../../csharp/language-reference/keywords/internal.md) (C#) o [Friend](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) di un altro assembly. Se un assembly viene riconosciuto di tipo Friend, non è più necessario contrassegnare tipi e membri come pubblici perché altri assembly possano accedervi. Questo metodo è particolarmente utile negli scenari seguenti:

- Durante il testing unità, quando il codice di test viene eseguito in un assembly separato ma richiede l'accesso ai membri dell'assembly sottoposto a test che sono contrassegnati come `internal` in C# o come `Friend` in Visual Basic.

- Quando si sviluppa una libreria di classi e le aggiunte alla libreria sono contenute in assembly separati ma richiedono l'accesso ai membri degli assembly esistenti che sono contrassegnati come `internal` in C# o come `Friend` in Visual Basic.

## <a name="remarks"></a>Osservazioni

È possibile usare l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per identificare uno o più assembly Friend per un determinato assembly. Nell'esempio seguente viene usato l' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributo nell' *assembly a* e viene specificato *AssemblyB* dell'assembly come assembly Friend. Questo consente all'assembly *AssemblyB* l'accesso a tutti i tipi e membri nell' *assembly a* contrassegnati come `internal` in C# o `Friend` in Visual Basic.

> [!NOTE]
> Quando si compila un assembly come *AssemblyB* che accede ai tipi interni o ai membri interni di un altro assembly come *assembly A*, è necessario specificare in modo esplicito il nome del file di output (con*estensione exe* o *dll*) utilizzando l'opzione **-out** del compilatore. Il compilatore non ha infatti ancora generato il nome dell'assembly in fase di compilazione quando crea l'associazione a riferimenti esterni. Per ulteriori informazioni, vedere [-out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).

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

Solo gli assembly specificati in modo esplicito come Friend possono accedere ai `internal` `Friend` tipi e ai membri (C#) o (Visual Basic). Ad esempio, se *AssemblyB* è un elemento Friend dell' *assembly a* e l' *assembly c* fa riferimento a *AssemblyB*, l' *assembly c* non ha accesso ai `internal` tipi (C#) o `Friend` (Visual Basic) nell' *assembly a*.

Il compilatore esegue alcune operazioni di convalida di base del nome dell'assembly Friend che viene passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Se l' *assembly A* dichiara *AssemblyB* come assembly Friend, le regole di convalida sono le seguenti:

- Se *l'assembly A* è con nome sicuro, *AssemblyB* deve anche essere con nome sicuro. Il nome dell'assembly Friend che viene passato all'attributo deve essere costituito dal nome dell'assembly e dalla chiave pubblica della chiave con nome sicuro usata per firmare *AssemblyB*.

     Il nome dell'assembly Friend passato all' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributo non può essere il nome sicuro *AssemblyB*. Non includere la versione, le impostazioni cultura, l'architettura o il token di chiave pubblica dell'assembly.

- Se l' *assembly A* non è con nome sicuro, il nome dell'assembly Friend deve essere costituito solo dal nome dell'assembly. Per altre informazioni, vedere [procedura: creare assembly Friend non firmati](create-unsigned-friend.md).

- Se *AssemblyB* è un nome sicuro, è necessario specificare la chiave con nome sicuro per *AssemblyB* usando l'impostazione del progetto o l'opzione del compilatore da riga di comando `/keyfile` . Per altre informazioni, vedere [procedura: creare assembly Friend firmati](create-signed-friend.md).

 La classe <xref:System.Security.Permissions.StrongNameIdentityPermission> consente anche la condivisione dei tipi, con le differenze seguenti:

- <xref:System.Security.Permissions.StrongNameIdentityPermission> si applica a un singolo tipo, mentre un assembly Friend si applica all'intero assembly.

- Se sono presenti centinaia di tipi nell' *assembly a* che si desidera condividere con *AssemblyB*, è necessario aggiungerli <xref:System.Security.Permissions.StrongNameIdentityPermission> a tutti. Se invece si usa un assembly Friend, è sufficiente dichiarare una volta che si tratta di una relazione di tipo Friend.

- Se si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, i tipi da condividere devono essere dichiarati come pubblici. Se si usa un assembly Friend, i tipi condivisi vengono dichiarati come `internal` (C#) o `Friend` (Visual Basic).

Per informazioni su come accedere ai tipi e ai metodi di un assembly `internal` (c#) o `Friend` (Visual Basic) da un file di modulo (un file con estensione *netmodule* ), vedere [-moduleassemblyname (c#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) o [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [Procedura: creare assembly Friend non firmati](create-unsigned-friend.md)
- [Procedura: creare assembly Friend firmati](create-signed-friend.md)
- [Assembly in .NET](index.md)
- [Guida per programmatori C#](../../csharp/programming-guide/index.md)
- [Concetti di programmazione (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
