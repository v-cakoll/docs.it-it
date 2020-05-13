---
title: 'Procedura: creare assembly Friend non firmati'
description: Questo articolo illustra come usare assembly Friend con assembly senza segno. Sono incluse informazioni sulla sicurezza di .NET.
ms.date: 08/19/2019
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
dev_langs:
- csharp
- vb
ms.openlocfilehash: 8d3e13669c36048759fedeb3df1bfb59fd476317
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378976"
---
# <a name="how-to-create-unsigned-friend-assemblies"></a>Procedura: creare assembly Friend non firmati

In questo esempio viene illustrato come usare assembly Friend e assembly non firmati.

## <a name="create-an-assembly-and-a-friend-assembly"></a>Creare un assembly e un assembly Friend

1. Aprire un prompt dei comandi.

2. Creare un file C# o Visual Basic denominato *friend_unsigned_A* che contiene il codice seguente. Il codice usa l' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributo per dichiarare *friend_unsigned_B* come assembly Friend.

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

3. Compilare e firmare *friend_unsigned_A* usando il comando seguente:

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. Creare un file C# o Visual Basic denominato *friend_unsigned_B* che contiene il codice seguente. Poiché *friend_unsigned_A* specifica *friend_unsigned_B* come assembly Friend, il codice in *friend_unsigned_B* può accedere ai `internal` tipi (C#) o `Friend` (Visual Basic) e ai membri da *friend_unsigned_A*.

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

5. Compilare *friend_unsigned_B* usando il comando seguente.

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. È necessario specificare in modo esplicito il nome dell'assembly di output (con*estensione exe* o *dll*) utilizzando l' `-out` opzione del compilatore. Per ulteriori informazioni, vedere [-out (opzioni del compilatore C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).

6. Eseguire il file *friend_unsigned_B. exe* .

   Il programma restituisce due stringhe: **Class1. test** e **Class2. test**.

## <a name="net-security"></a>Protezione .NET

Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>. La differenza principale è che <xref:System.Security.Permissions.StrongNameIdentityPermission> può richiedere le autorizzazioni di sicurezza per l'esecuzione di una particolare sezione di codice, mentre l' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributo controlla la visibilità dei `internal` `Friend` tipi e dei membri di o (Visual Basic).

## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Assembly in .NET](index.md)
- [Assembly Friend](friend.md)
- [Procedura: creare assembly Friend firmati](create-signed-friend.md)
- [Guida per programmatori C#](../../csharp/programming-guide/index.md)
- [Concetti di programmazione (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
