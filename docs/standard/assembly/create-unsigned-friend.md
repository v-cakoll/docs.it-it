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
# <a name="how-to-create-unsigned-friend-assemblies"></a><span data-ttu-id="f8cee-102">Procedura: creare assembly friend non firmatiHow to: Create unsigned Friend assemblies</span><span class="sxs-lookup"><span data-stu-id="f8cee-102">How to: Create unsigned friend assemblies</span></span>

<span data-ttu-id="f8cee-103">In questo esempio viene illustrato come usare assembly Friend e assembly non firmati.</span><span class="sxs-lookup"><span data-stu-id="f8cee-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>

## <a name="create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="f8cee-104">Creare un assieme e un assieme friend</span><span class="sxs-lookup"><span data-stu-id="f8cee-104">Create an assembly and a friend assembly</span></span>

1. <span data-ttu-id="f8cee-105">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="f8cee-105">Open a command prompt.</span></span>

2. <span data-ttu-id="f8cee-106">Creare un file di C o Visual Basic denominato *friend_unsigned_A* che contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f8cee-106">Create a C# or Visual Basic file named *friend_unsigned_A* that contains the following code.</span></span> <span data-ttu-id="f8cee-107">Il codice <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> utilizza l'attributo per dichiarare *friend_unsigned_B* come assembly Friend.</span><span class="sxs-lookup"><span data-stu-id="f8cee-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_unsigned_B* as a friend assembly.</span></span>

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

3. <span data-ttu-id="f8cee-108">Compilare e firmare *friend_unsigned_A* utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f8cee-108">Compile and sign *friend_unsigned_A* by using the following command:</span></span>

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. <span data-ttu-id="f8cee-109">Creare un file di Visual Basic denominato *friend_unsigned_B* che contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f8cee-109">Create a C# or Visual Basic file named *friend_unsigned_B* that contains the following code.</span></span> <span data-ttu-id="f8cee-110">Poiché *friend_unsigned_A* specifica *friend_unsigned_B* come assembly Friend, `internal` il codice in `Friend` *friend_unsigned_B* può accedere ai tipi e ai membri (C) o (Visual Basic) da *friend_unsigned_A*.</span><span class="sxs-lookup"><span data-stu-id="f8cee-110">Because *friend_unsigned_A* specifies *friend_unsigned_B* as a friend assembly, the code in *friend_unsigned_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_unsigned_A*.</span></span>

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

5. <span data-ttu-id="f8cee-111">Compilare *friend_unsigned_B* utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="f8cee-111">Compile *friend_unsigned_B* by using the following command.</span></span>

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   <span data-ttu-id="f8cee-112">Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f8cee-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="f8cee-113">È necessario specificare in modo esplicito il nome dell'assembly di output (*.exe* o *.dll*) utilizzando l'opzione del `-out` compilatore.</span><span class="sxs-lookup"><span data-stu-id="f8cee-113">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `-out` compiler option.</span></span> <span data-ttu-id="f8cee-114">Per altre informazioni, vedere [-out (opzioni del compilatore C)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)..</span><span class="sxs-lookup"><span data-stu-id="f8cee-114">For more information, see [-out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)..</span></span>

6. <span data-ttu-id="f8cee-115">Eseguire il file *friend_unsigned_B.exe.*</span><span class="sxs-lookup"><span data-stu-id="f8cee-115">Run the *friend_unsigned_B.exe* file.</span></span>

   <span data-ttu-id="f8cee-116">Il programma genera due stringhe: **Class1.Test** e **Class2.Test**.</span><span class="sxs-lookup"><span data-stu-id="f8cee-116">The program outputs two strings: **Class1.Test** and **Class2.Test**.</span></span>

## <a name="net-security"></a><span data-ttu-id="f8cee-117">Protezione .NET</span><span class="sxs-lookup"><span data-stu-id="f8cee-117">.NET security</span></span>

<span data-ttu-id="f8cee-118">Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="f8cee-118">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="f8cee-119">La differenza principale <xref:System.Security.Permissions.StrongNameIdentityPermission> è che può richiedere autorizzazioni di sicurezza <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per eseguire `internal` una `Friend` particolare sezione di codice, mentre l'attributo controlla la visibilità di o (Visual Basic) tipi e membri.</span><span class="sxs-lookup"><span data-stu-id="f8cee-119">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal`  or `Friend` (Visual Basic) types and members.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8cee-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8cee-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="f8cee-121">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="f8cee-121">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="f8cee-122">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="f8cee-122">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="f8cee-123">Procedura: creare assembly friend firmatiHow to: Create signed friend assemblies</span><span class="sxs-lookup"><span data-stu-id="f8cee-123">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="f8cee-124">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="f8cee-124">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f8cee-125">Concetti di programmazione (Visual Basic)Programming concepts (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8cee-125">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
