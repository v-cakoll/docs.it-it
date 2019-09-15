---
title: 'Procedura: Crea assembly Friend non firmati'
ms.date: 08/19/2019
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
dev_langs:
- csharp
- vb
ms.openlocfilehash: 9d5699f772dba994b10408d15422faa3c5931f45
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991689"
---
# <a name="how-to-create-unsigned-friend-assemblies"></a><span data-ttu-id="a6d93-102">Procedura: Crea assembly Friend non firmati</span><span class="sxs-lookup"><span data-stu-id="a6d93-102">How to: Create unsigned friend assemblies</span></span>

<span data-ttu-id="a6d93-103">In questo esempio viene illustrato come usare assembly Friend e assembly non firmati.</span><span class="sxs-lookup"><span data-stu-id="a6d93-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>

## <a name="create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="a6d93-104">Creare un assembly e un assembly Friend</span><span class="sxs-lookup"><span data-stu-id="a6d93-104">Create an assembly and a friend assembly</span></span>

1. <span data-ttu-id="a6d93-105">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a6d93-105">Open a command prompt.</span></span>

2. <span data-ttu-id="a6d93-106">Creare un C# file o Visual Basic denominato *friend_unsigned_A* contenente il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a6d93-106">Create a C# or Visual Basic file named *friend_unsigned_A* that contains the following code.</span></span> <span data-ttu-id="a6d93-107">Il codice usa l' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributo per dichiarare *friend_unsigned_B* come assembly Friend.</span><span class="sxs-lookup"><span data-stu-id="a6d93-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_unsigned_B* as a friend assembly.</span></span>

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
   Imports System

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

3. <span data-ttu-id="a6d93-108">Compilare e firmare *friend_unsigned_A* usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a6d93-108">Compile and sign *friend_unsigned_A* by using the following command:</span></span>

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. <span data-ttu-id="a6d93-109">Creare un C# file o Visual Basic denominato *friend_unsigned_B* contenente il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a6d93-109">Create a C# or Visual Basic file named *friend_unsigned_B* that contains the following code.</span></span> <span data-ttu-id="a6d93-110">Poiché *friend_unsigned_A* specifica *friend_unsigned_B* come assembly Friend, il codice in *friend_unsigned_B* può accedere ai `internal` tipiC#e ai `Friend` membri () o (Visual Basic) da *friend_unsigned_A* .</span><span class="sxs-lookup"><span data-stu-id="a6d93-110">Because *friend_unsigned_A* specifies *friend_unsigned_B* as a friend assembly, the code in *friend_unsigned_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_unsigned_A*.</span></span>

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

5. <span data-ttu-id="a6d93-111">Compilare *friend_unsigned_B* usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="a6d93-111">Compile *friend_unsigned_B* by using the following command.</span></span>

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   <span data-ttu-id="a6d93-112">Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a6d93-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="a6d93-113">È necessario specificare in modo esplicito il nome dell'assembly di output (con*estensione exe* o *dll*) utilizzando `/out` l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="a6d93-113">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `/out` compiler option.</span></span> <span data-ttu-id="a6d93-114">Per ulteriori informazioni, vedere [/out (C# opzioni del compilatore)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="a6d93-114">For more information, see [/out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)..</span></span>

6. <span data-ttu-id="a6d93-115">Eseguire il file *friend_unsigned_B. exe* .</span><span class="sxs-lookup"><span data-stu-id="a6d93-115">Run the *friend_unsigned_B.exe* file.</span></span>

   <span data-ttu-id="a6d93-116">Il programma restituisce due stringhe: **Class1. test** e **Class2. test**.</span><span class="sxs-lookup"><span data-stu-id="a6d93-116">The program outputs two strings: **Class1.Test** and **Class2.Test**.</span></span>

## <a name="net-security"></a><span data-ttu-id="a6d93-117">Protezione .NET</span><span class="sxs-lookup"><span data-stu-id="a6d93-117">.NET security</span></span>

<span data-ttu-id="a6d93-118">Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="a6d93-118">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="a6d93-119">La differenza principale è che <xref:System.Security.Permissions.StrongNameIdentityPermission> può richiedere le autorizzazioni di sicurezza per l'esecuzione di una particolare sezione di <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> codice, mentre l'attributo `internal` controlla `Friend` la visibilità dei tipi e dei membri di o (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a6d93-119">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal`  or `Friend` (Visual Basic) types and members.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6d93-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6d93-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="a6d93-121">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="a6d93-121">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="a6d93-122">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="a6d93-122">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="a6d93-123">Procedura: Crea assembly Friend firmati</span><span class="sxs-lookup"><span data-stu-id="a6d93-123">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="a6d93-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a6d93-124">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a6d93-125">Concetti di programmazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6d93-125">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
