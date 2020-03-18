---
title: 'Procedura: creare assembly friend non firmatiHow to: Create unsigned Friend assemblies'
ms.date: 08/19/2019
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
dev_langs:
- csharp
- vb
ms.openlocfilehash: f8fec064507553b8208083578165965de2303a33
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74352442"
---
# <a name="how-to-create-unsigned-friend-assemblies"></a>Procedura: creare assembly friend non firmatiHow to: Create unsigned Friend assemblies

In questo esempio viene illustrato come usare assembly Friend e assembly non firmati.

## <a name="create-an-assembly-and-a-friend-assembly"></a>Creare un assieme e un assieme friend

1. Aprire un prompt dei comandi.

2. Creare un file di C o Visual Basic denominato *friend_unsigned_A* che contiene il codice seguente. Il codice <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> utilizza l'attributo per dichiarare *friend_unsigned_B* come assembly Friend.

   ```csharp
   // friend_unsigned_A.cs
   // Compile with:
   // csc /target:library friend_unsigned_A.cs
   using System.Runtime.CompilerServices;
   using System;

   [assembly: InternalsVisibleTo("friend_unsigned_B")]

   // Type is internal by default.
   class Class1
   {
       public void Test()
       {
           Console.WriteLine("Class1.Test");
       }
   }

   // Public type with internal member.
   public class Class2
   {
       internal void Test()
       {
           Console.WriteLine("Class2.Test");
       }
   }
   ```

   ```vb
   ' friend_unsigned_A.vb
   ' Compile with:
   ' vbc -target:library friend_unsigned_A.vb
   Imports System.Runtime.CompilerServices

   <Assembly: InternalsVisibleTo("friend_unsigned_B")>

   ' Friend type.
   Friend Class Class1
       Public Sub Test()
           Console.WriteLine("Class1.Test")
       End Sub
   End Class

   ' Public type with Friend member.
   Public Class Class2
       Friend Sub Test()
           Console.WriteLine("Class2.Test")
       End Sub
   End Class
   ```

3. Compilare e firmare *friend_unsigned_A* utilizzando il comando seguente:

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. Creare un file di Visual Basic denominato *friend_unsigned_B* che contiene il codice seguente. Poiché *friend_unsigned_A* specifica *friend_unsigned_B* come assembly Friend, `internal` il codice in `Friend` *friend_unsigned_B* può accedere ai tipi e ai membri (C) o (Visual Basic) da *friend_unsigned_A*.

   ```csharp
   // friend_unsigned_B.cs
   // Compile with:
   // csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   public class Program
   {
       static void Main()
       {
           // Access an internal type.
           Class1 inst1 = new Class1();
           inst1.Test();

           Class2 inst2 = new Class2();
           // Access an internal member of a public type.
           inst2.Test();

           System.Console.ReadLine();
       }
   }
   ```

   ```vb
   ' friend_unsigned_B.vb
   ' Compile with:
   ' vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   Module Module1
       Sub Main()
           ' Access a Friend type.
           Dim inst1 As New Class1()
           inst1.Test()

           Dim inst2 As New Class2()
           ' Access a Friend member of a public type.
           inst2.Test()

           System.Console.ReadLine()
       End Sub
   End Module
   ```

5. Compilare *friend_unsigned_B* utilizzando il comando seguente.

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. È necessario specificare in modo esplicito il nome dell'assembly di output (*.exe* o *.dll*) utilizzando l'opzione del `-out` compilatore. Per altre informazioni, vedere [-out (opzioni del compilatore C)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)..

6. Eseguire il file *friend_unsigned_B.exe.*

   Il programma genera due stringhe: **Class1.Test** e **Class2.Test**.

## <a name="net-security"></a>Protezione .NET

Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>. La differenza principale <xref:System.Security.Permissions.StrongNameIdentityPermission> è che può richiedere autorizzazioni di sicurezza <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per eseguire `internal` una `Friend` particolare sezione di codice, mentre l'attributo controlla la visibilità di o (Visual Basic) tipi e membri.

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Assembly in .NET](index.md)
- [Assembly Friend](friend.md)
- [Procedura: creare assembly friend firmatiHow to: Create signed friend assemblies](create-signed-friend.md)
- [Guida alla programmazione in C](../../csharp/programming-guide/index.md)
- [Concetti di programmazione (Visual Basic)Programming concepts (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
