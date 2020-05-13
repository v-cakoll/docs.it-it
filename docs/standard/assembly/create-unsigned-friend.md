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
# <a name="how-to-create-unsigned-friend-assemblies"></a><span data-ttu-id="436ff-104">Procedura: creare assembly Friend non firmati</span><span class="sxs-lookup"><span data-stu-id="436ff-104">How to: Create unsigned friend assemblies</span></span>

<span data-ttu-id="436ff-105">In questo esempio viene illustrato come usare assembly Friend e assembly non firmati.</span><span class="sxs-lookup"><span data-stu-id="436ff-105">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>

## <a name="create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="436ff-106">Creare un assembly e un assembly Friend</span><span class="sxs-lookup"><span data-stu-id="436ff-106">Create an assembly and a friend assembly</span></span>

1. <span data-ttu-id="436ff-107">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="436ff-107">Open a command prompt.</span></span>

2. <span data-ttu-id="436ff-108">Creare un file C# o Visual Basic denominato *friend_unsigned_A* che contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="436ff-108">Create a C# or Visual Basic file named *friend_unsigned_A* that contains the following code.</span></span> <span data-ttu-id="436ff-109">Il codice usa l' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributo per dichiarare *friend_unsigned_B* come assembly Friend.</span><span class="sxs-lookup"><span data-stu-id="436ff-109">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_unsigned_B* as a friend assembly.</span></span>

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

3. <span data-ttu-id="436ff-110">Compilare e firmare *friend_unsigned_A* usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="436ff-110">Compile and sign *friend_unsigned_A* by using the following command:</span></span>

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. <span data-ttu-id="436ff-111">Creare un file C# o Visual Basic denominato *friend_unsigned_B* che contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="436ff-111">Create a C# or Visual Basic file named *friend_unsigned_B* that contains the following code.</span></span> <span data-ttu-id="436ff-112">Poiché *friend_unsigned_A* specifica *friend_unsigned_B* come assembly Friend, il codice in *friend_unsigned_B* può accedere ai `internal` tipi (C#) o `Friend` (Visual Basic) e ai membri da *friend_unsigned_A*.</span><span class="sxs-lookup"><span data-stu-id="436ff-112">Because *friend_unsigned_A* specifies *friend_unsigned_B* as a friend assembly, the code in *friend_unsigned_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_unsigned_A*.</span></span>

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

5. <span data-ttu-id="436ff-113">Compilare *friend_unsigned_B* usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="436ff-113">Compile *friend_unsigned_B* by using the following command.</span></span>

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   <span data-ttu-id="436ff-114">Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="436ff-114">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="436ff-115">È necessario specificare in modo esplicito il nome dell'assembly di output (con*estensione exe* o *dll*) utilizzando l' `-out` opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="436ff-115">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `-out` compiler option.</span></span> <span data-ttu-id="436ff-116">Per ulteriori informazioni, vedere [-out (opzioni del compilatore C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="436ff-116">For more information, see [-out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)..</span></span>

6. <span data-ttu-id="436ff-117">Eseguire il file *friend_unsigned_B. exe* .</span><span class="sxs-lookup"><span data-stu-id="436ff-117">Run the *friend_unsigned_B.exe* file.</span></span>

   <span data-ttu-id="436ff-118">Il programma restituisce due stringhe: **Class1. test** e **Class2. test**.</span><span class="sxs-lookup"><span data-stu-id="436ff-118">The program outputs two strings: **Class1.Test** and **Class2.Test**.</span></span>

## <a name="net-security"></a><span data-ttu-id="436ff-119">Protezione .NET</span><span class="sxs-lookup"><span data-stu-id="436ff-119">.NET security</span></span>

<span data-ttu-id="436ff-120">Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="436ff-120">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="436ff-121">La differenza principale è che <xref:System.Security.Permissions.StrongNameIdentityPermission> può richiedere le autorizzazioni di sicurezza per l'esecuzione di una particolare sezione di codice, mentre l' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributo controlla la visibilità dei `internal` `Friend` tipi e dei membri di o (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="436ff-121">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal`  or `Friend` (Visual Basic) types and members.</span></span>

## <a name="see-also"></a><span data-ttu-id="436ff-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="436ff-122">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="436ff-123">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="436ff-123">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="436ff-124">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="436ff-124">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="436ff-125">Procedura: creare assembly Friend firmati</span><span class="sxs-lookup"><span data-stu-id="436ff-125">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="436ff-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="436ff-126">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="436ff-127">Concetti di programmazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="436ff-127">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
