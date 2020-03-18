---
title: 'Procedura: creare assembly friend firmatiHow to: Create signed friend assemblies'
ms.date: 08/19/2019
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
dev_langs:
- csharp
- vb
ms.openlocfilehash: 9912fa70014a8828e994cf528644aaa7cb351fea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159494"
---
# <a name="how-to-create-signed-friend-assemblies"></a><span data-ttu-id="2aea2-102">Procedura: creare assembly friend firmatiHow to: Create signed friend assemblies</span><span class="sxs-lookup"><span data-stu-id="2aea2-102">How to: Create signed friend assemblies</span></span>
<span data-ttu-id="2aea2-103">In questo esempio viene illustrato come usare assembly Friend e assembly con nomi sicuri.</span><span class="sxs-lookup"><span data-stu-id="2aea2-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="2aea2-104">È necessario che entrambi i tipi di assembly abbiano un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="2aea2-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="2aea2-105">Gli assembly in questo esempio usano le stesse chiavi. È comunque possibile usare chiavi diverse per i due assembly.</span><span class="sxs-lookup"><span data-stu-id="2aea2-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
## <a name="create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="2aea2-106">Creare un assembly firmato e un assembly friendCreate a signed assembly and a friend assembly</span><span class="sxs-lookup"><span data-stu-id="2aea2-106">Create a signed assembly and a friend assembly</span></span>  
  
1. <span data-ttu-id="2aea2-107">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="2aea2-107">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="2aea2-108">Eseguire la sequenza di comandi seguente con lo strumento Nome sicuro per generare un keyfile e per visualizzare la relativa chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="2aea2-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="2aea2-109">Per ulteriori informazioni, vedere [Sn.exe (strumento Nome sicuro)](../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2aea2-109">For more information, see [Sn.exe (Strong Name tool)](../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
    1. <span data-ttu-id="2aea2-110">Generare una chiave con nome sicuro per questo esempio e archiviarla nel file *FriendAssemblies.snk*:</span><span class="sxs-lookup"><span data-stu-id="2aea2-110">Generate a strong-name key for this example and store it in the file *FriendAssemblies.snk*:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2. <span data-ttu-id="2aea2-111">Estrarre la chiave pubblica da *FriendAssemblies.snk* e inserirla in *FriendAssemblies.publickey*:</span><span class="sxs-lookup"><span data-stu-id="2aea2-111">Extract the public key from *FriendAssemblies.snk* and put it into *FriendAssemblies.publickey*:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3. <span data-ttu-id="2aea2-112">Visualizzare la chiave pubblica archiviata nel file *FriendAssemblies.publickey*:</span><span class="sxs-lookup"><span data-stu-id="2aea2-112">Display the public key stored in the file *FriendAssemblies.publickey*:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. <span data-ttu-id="2aea2-113">Creare un file di Visual Basic denominato *friend_signed_A* che contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2aea2-113">Create a C# or Visual Basic file named *friend_signed_A* that contains the following code.</span></span> <span data-ttu-id="2aea2-114">Il codice <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> utilizza l'attributo per dichiarare *friend_signed_B* come assembly Friend.</span><span class="sxs-lookup"><span data-stu-id="2aea2-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_signed_B* as a friend assembly.</span></span>  

   <span data-ttu-id="2aea2-115">Ogni volta che viene eseguito, lo strumento Nome sicuro genera una chiave pubblica nuova.</span><span class="sxs-lookup"><span data-stu-id="2aea2-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="2aea2-116">È pertanto necessario sostituire la chiave pubblica nel codice seguente con la chiave pubblica appena generata, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2aea2-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  

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

4. <span data-ttu-id="2aea2-117">Compilare e firmare *friend_signed_A* utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="2aea2-117">Compile and sign *friend_signed_A* by using the following command.</span></span>  

   ```csharp
   csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
   ```  

   ```vb
   Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
   ```  

5. <span data-ttu-id="2aea2-118">Creare un file di C o Visual Basic denominato *friend_signed_B* che contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2aea2-118">Create a C# or Visual Basic file named *friend_signed_B* that contains the following code.</span></span> <span data-ttu-id="2aea2-119">Poiché *friend_signed_A* specifica *friend_signed_B* come assembly Friend, `internal` il codice in `Friend` *friend_signed_B* può accedere ai tipi e ai membri (C) o (Visual Basic) da *friend_signed_A*.</span><span class="sxs-lookup"><span data-stu-id="2aea2-119">Because *friend_signed_A* specifies *friend_signed_B* as a friend assembly, the code in *friend_signed_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_signed_A*.</span></span> <span data-ttu-id="2aea2-120">Il file contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2aea2-120">The file contains the following code.</span></span>  

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

6. <span data-ttu-id="2aea2-121">Compilare e firmare *friend_signed_B* utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="2aea2-121">Compile and sign *friend_signed_B* by using the following command.</span></span>  

   ```csharp
   csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
   ```  

   ```vb
   vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
   ```  

   <span data-ttu-id="2aea2-122">Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2aea2-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="2aea2-123">È necessario specificare in modo esplicito il nome dell'assembly di output (*.exe* o *.dll*) utilizzando l'opzione del `-out` compilatore.</span><span class="sxs-lookup"><span data-stu-id="2aea2-123">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `-out` compiler option.</span></span> <span data-ttu-id="2aea2-124">Per ulteriori informazioni, vedere [-out (opzioni del compilatore C)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="2aea2-124">For more information, see [-out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span></span>  

7. <span data-ttu-id="2aea2-125">Eseguire il file *friend_signed_B.exe.*</span><span class="sxs-lookup"><span data-stu-id="2aea2-125">Run the *friend_signed_B.exe* file.</span></span>  

   <span data-ttu-id="2aea2-126">Il programma restituisce la stringa **Class1.Test**.</span><span class="sxs-lookup"><span data-stu-id="2aea2-126">The program outputs the string **Class1.Test**.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="2aea2-127">Protezione .NET</span><span class="sxs-lookup"><span data-stu-id="2aea2-127">.NET security</span></span>  
 <span data-ttu-id="2aea2-128">Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="2aea2-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="2aea2-129">La differenza principale <xref:System.Security.Permissions.StrongNameIdentityPermission> è che può richiedere autorizzazioni di sicurezza <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per l'esecuzione di una particolare sezione di codice, mentre l'attributo controlla la visibilità di `internal` (C ) o `Friend` (Visual Basic) tipi e membri.</span><span class="sxs-lookup"><span data-stu-id="2aea2-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` (C#) or `Friend` (Visual Basic) types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aea2-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2aea2-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="2aea2-131">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="2aea2-131">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="2aea2-132">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="2aea2-132">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="2aea2-133">Procedura: creare assembly friend non firmatiHow to: Create unsigned Friend assemblies</span><span class="sxs-lookup"><span data-stu-id="2aea2-133">How to: Create unsigned friend assemblies</span></span>](create-unsigned-friend.md)
- [<span data-ttu-id="2aea2-134">-keyfile (C</span><span class="sxs-lookup"><span data-stu-id="2aea2-134">-keyfile (C#)</span></span>](../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)
- [<span data-ttu-id="2aea2-135">-keyfile (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2aea2-135">-keyfile (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="2aea2-136">Sn.exe (strumento Nome sicuro)</span><span class="sxs-lookup"><span data-stu-id="2aea2-136">Sn.exe (Strong Name tool)</span></span>](../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="2aea2-137">Creare e usare gli assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="2aea2-137">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
- [<span data-ttu-id="2aea2-138">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="2aea2-138">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2aea2-139">Concetti di programmazione (Visual Basic)Programming concepts (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2aea2-139">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
