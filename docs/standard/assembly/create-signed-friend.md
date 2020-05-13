---
title: 'Procedura: creare assembly Friend firmati'
description: Questo articolo illustra come usare assembly Friend con assembly con nomi sicuri. Sono incluse informazioni sulla sicurezza di .NET.
ms.date: 08/19/2019
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
dev_langs:
- csharp
- vb
ms.openlocfilehash: b6176afed44e32911a37a0d753cea2bae7d8554e
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378535"
---
# <a name="how-to-create-signed-friend-assemblies"></a><span data-ttu-id="57c3d-104">Procedura: creare assembly Friend firmati</span><span class="sxs-lookup"><span data-stu-id="57c3d-104">How to: Create signed friend assemblies</span></span>
<span data-ttu-id="57c3d-105">In questo esempio viene illustrato come usare assembly Friend e assembly con nomi sicuri.</span><span class="sxs-lookup"><span data-stu-id="57c3d-105">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="57c3d-106">È necessario che entrambi i tipi di assembly abbiano un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="57c3d-106">Both assemblies must be strong named.</span></span> <span data-ttu-id="57c3d-107">Gli assembly in questo esempio usano le stesse chiavi. È comunque possibile usare chiavi diverse per i due assembly.</span><span class="sxs-lookup"><span data-stu-id="57c3d-107">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
## <a name="create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="57c3d-108">Creare un assembly firmato e un assembly Friend</span><span class="sxs-lookup"><span data-stu-id="57c3d-108">Create a signed assembly and a friend assembly</span></span>  
  
1. <span data-ttu-id="57c3d-109">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="57c3d-109">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="57c3d-110">Eseguire la sequenza di comandi seguente con lo strumento Nome sicuro per generare un keyfile e per visualizzare la relativa chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="57c3d-110">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="57c3d-111">Per ulteriori informazioni, vedere [sn. exe (strumento nome sicuro)](../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="57c3d-111">For more information, see [Sn.exe (Strong Name tool)](../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
    1. <span data-ttu-id="57c3d-112">Generare una chiave con nome sicuro per questo esempio e archiviarla nel file *FriendAssemblies. snk*:</span><span class="sxs-lookup"><span data-stu-id="57c3d-112">Generate a strong-name key for this example and store it in the file *FriendAssemblies.snk*:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2. <span data-ttu-id="57c3d-113">Estrarre la chiave pubblica da *FriendAssemblies. snk* e inserirla in *FriendAssemblies. PublicKey*:</span><span class="sxs-lookup"><span data-stu-id="57c3d-113">Extract the public key from *FriendAssemblies.snk* and put it into *FriendAssemblies.publickey*:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3. <span data-ttu-id="57c3d-114">Visualizzare la chiave pubblica archiviata nel file *FriendAssemblies. PublicKey*:</span><span class="sxs-lookup"><span data-stu-id="57c3d-114">Display the public key stored in the file *FriendAssemblies.publickey*:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. <span data-ttu-id="57c3d-115">Creare un file C# o Visual Basic denominato *friend_signed_A* che contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="57c3d-115">Create a C# or Visual Basic file named *friend_signed_A* that contains the following code.</span></span> <span data-ttu-id="57c3d-116">Il codice usa l' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributo per dichiarare *friend_signed_B* come assembly Friend.</span><span class="sxs-lookup"><span data-stu-id="57c3d-116">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_signed_B* as a friend assembly.</span></span>  

   <span data-ttu-id="57c3d-117">Ogni volta che viene eseguito, lo strumento Nome sicuro genera una chiave pubblica nuova.</span><span class="sxs-lookup"><span data-stu-id="57c3d-117">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="57c3d-118">È pertanto necessario sostituire la chiave pubblica nel codice seguente con la chiave pubblica appena generata, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="57c3d-118">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  

   ```csharp  
   // friend_signed_A.cs  
   // Compile with:
   // csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
   using System.Runtime.CompilerServices;  

   [assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")]  
   class Class1  
   {  
       public void Test()  
       {  
           System.Console.WriteLine("Class1.Test");  
           System.Console.ReadLine();  
       }  
   }  
   ```  

   ```vb  
   ' friend_signed_A.vb  
   ' Compile with:
   ' Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
   Imports System.Runtime.CompilerServices  

   <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>
   Public Class Class1  
       Public Sub Test()  
           System.Console.WriteLine("Class1.Test")  
           System.Console.ReadLine()  
       End Sub  
   End Class  
   ```  

4. <span data-ttu-id="57c3d-119">Compilare e firmare *friend_signed_A* usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="57c3d-119">Compile and sign *friend_signed_A* by using the following command.</span></span>  

   ```csharp
   csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
   ```  

   ```vb
   Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
   ```  

5. <span data-ttu-id="57c3d-120">Creare un file C# o Visual Basic denominato *friend_signed_B* che contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="57c3d-120">Create a C# or Visual Basic file named *friend_signed_B* that contains the following code.</span></span> <span data-ttu-id="57c3d-121">Poiché *friend_signed_A* specifica *friend_signed_B* come assembly Friend, il codice in *friend_signed_B* può accedere ai `internal` tipi (C#) o `Friend` (Visual Basic) e ai membri da *friend_signed_A*.</span><span class="sxs-lookup"><span data-stu-id="57c3d-121">Because *friend_signed_A* specifies *friend_signed_B* as a friend assembly, the code in *friend_signed_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_signed_A*.</span></span> <span data-ttu-id="57c3d-122">Il file contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="57c3d-122">The file contains the following code.</span></span>  

   ```csharp  
   // friend_signed_B.cs  
   // Compile with:
   // csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
   public class Program  
   {  
       static void Main()  
       {  
           Class1 inst = new Class1();  
           inst.Test();  
       }  
   }  
   ```  

   ```vb  
   ' friend_signed_B.vb  
   ' Compile with:
   ' Vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
   Module Sample  
       Public Sub Main()  
           Dim inst As New Class1  
           inst.Test()  
       End Sub  
   End Module  
   ```  

6. <span data-ttu-id="57c3d-123">Compilare e firmare *friend_signed_B* usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="57c3d-123">Compile and sign *friend_signed_B* by using the following command.</span></span>  

   ```csharp
   csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
   ```  

   ```vb
   vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
   ```  

   <span data-ttu-id="57c3d-124">Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="57c3d-124">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="57c3d-125">È necessario specificare in modo esplicito il nome dell'assembly di output (con*estensione exe* o *dll*) utilizzando l' `-out` opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="57c3d-125">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `-out` compiler option.</span></span> <span data-ttu-id="57c3d-126">Per ulteriori informazioni, vedere [-out (opzioni del compilatore C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="57c3d-126">For more information, see [-out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span></span>  

7. <span data-ttu-id="57c3d-127">Eseguire il file *friend_signed_B. exe* .</span><span class="sxs-lookup"><span data-stu-id="57c3d-127">Run the *friend_signed_B.exe* file.</span></span>  

   <span data-ttu-id="57c3d-128">Il programma restituisce la stringa **Class1. test**.</span><span class="sxs-lookup"><span data-stu-id="57c3d-128">The program outputs the string **Class1.Test**.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="57c3d-129">Protezione .NET</span><span class="sxs-lookup"><span data-stu-id="57c3d-129">.NET security</span></span>  
 <span data-ttu-id="57c3d-130">Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="57c3d-130">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="57c3d-131">La differenza principale è che <xref:System.Security.Permissions.StrongNameIdentityPermission> può richiedere le autorizzazioni di sicurezza per eseguire una particolare sezione di codice, mentre l' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributo controlla la visibilità dei `internal` tipi e membri (C#) o `Friend` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="57c3d-131">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` (C#) or `Friend` (Visual Basic) types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57c3d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57c3d-132">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="57c3d-133">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="57c3d-133">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="57c3d-134">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="57c3d-134">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="57c3d-135">Procedura: creare assembly Friend non firmati</span><span class="sxs-lookup"><span data-stu-id="57c3d-135">How to: Create unsigned friend assemblies</span></span>](create-unsigned-friend.md)
- [<span data-ttu-id="57c3d-136">-filefile (C#)</span><span class="sxs-lookup"><span data-stu-id="57c3d-136">-keyfile (C#)</span></span>](../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)
- [<span data-ttu-id="57c3d-137">-filefile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57c3d-137">-keyfile (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="57c3d-138">Sn. exe (strumento nome sicuro)</span><span class="sxs-lookup"><span data-stu-id="57c3d-138">Sn.exe (Strong Name tool)</span></span>](../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="57c3d-139">Creare e usare gli assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="57c3d-139">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
- [<span data-ttu-id="57c3d-140">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="57c3d-140">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="57c3d-141">Concetti di programmazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57c3d-141">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
