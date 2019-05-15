---
title: 'Procedura: Creare assembly Friend firmati (C#)'
ms.date: 07/20/2015
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
ms.openlocfilehash: df04f6f5a006c7eea7984004e20578c85e51efe0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64582974"
---
# <a name="how-to-create-signed-friend-assemblies-c"></a><span data-ttu-id="e2497-102">Procedura: Creare assembly Friend firmati (C#)</span><span class="sxs-lookup"><span data-stu-id="e2497-102">How to: Create Signed Friend Assemblies (C#)</span></span>
<span data-ttu-id="e2497-103">In questo esempio viene illustrato come usare assembly Friend e assembly con nomi sicuri.</span><span class="sxs-lookup"><span data-stu-id="e2497-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="e2497-104">È necessario che entrambi i tipi di assembly abbiano un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="e2497-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="e2497-105">Gli assembly in questo esempio usano le stesse chiavi. È comunque possibile usare chiavi diverse per i due assembly.</span><span class="sxs-lookup"><span data-stu-id="e2497-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="e2497-106">Per creare un assembly firmato e un assembly friend</span><span class="sxs-lookup"><span data-stu-id="e2497-106">To create a signed assembly and a friend assembly</span></span>  
  
1. <span data-ttu-id="e2497-107">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="e2497-107">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="e2497-108">Eseguire la sequenza di comandi seguente con lo strumento Nome sicuro per generare un keyfile e per visualizzare la relativa chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="e2497-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="e2497-109">Per altre informazioni, vedere [Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="e2497-109">For more information, see [Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
    1. <span data-ttu-id="e2497-110">Generare una chiave con nome sicuro per questo esempio e archiviarla nel file FriendAssemblies.snk:</span><span class="sxs-lookup"><span data-stu-id="e2497-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2. <span data-ttu-id="e2497-111">Estrarre la chiave pubblica da FriendAssemblies.snk e inserirla in FriendAssemblies.publickey:</span><span class="sxs-lookup"><span data-stu-id="e2497-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3. <span data-ttu-id="e2497-112">Visualizzare la chiave pubblica archiviata nel file FriendAssemblies.publickey:</span><span class="sxs-lookup"><span data-stu-id="e2497-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. <span data-ttu-id="e2497-113">Creare un file C# denominato `friend_signed_A` contenente il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e2497-113">Create a C# file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="e2497-114">Il codice usa l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per dichiarare friend_signed_B come assembly Friend.</span><span class="sxs-lookup"><span data-stu-id="e2497-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="e2497-115">Ogni volta che viene eseguito, lo strumento Nome sicuro genera una chiave pubblica nuova.</span><span class="sxs-lookup"><span data-stu-id="e2497-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="e2497-116">È pertanto necessario sostituire la chiave pubblica nel codice seguente con la chiave pubblica appena generata, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e2497-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
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
  
4. <span data-ttu-id="e2497-117">Compilare e firmare friend_signed_A usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="e2497-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```csharp  
    csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    ```  
  
5. <span data-ttu-id="e2497-118">Creare un file C# denominato `friend_signed_B` contenente il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e2497-118">Create a C# file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="e2497-119">Poiché friend_signed_A specifica che friend_signed_B è un assembly Friend, il codice in friend_signed_B può accedere ai tipi e ai membri `internal` da friend_signed_A.</span><span class="sxs-lookup"><span data-stu-id="e2497-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `internal` types and members from friend_signed_A.</span></span> <span data-ttu-id="e2497-120">Il file contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e2497-120">The file contains the following code.</span></span>  
  
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
  
6. <span data-ttu-id="e2497-121">Compilare e firmare friend_signed_B usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="e2497-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```csharp  
    csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    ```  
  
     <span data-ttu-id="e2497-122">Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e2497-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="e2497-123">È necessario specificare in modo esplicito il nome dell'assembly di output (con estensione exe o dll) usando il compilatore `/out`.</span><span class="sxs-lookup"><span data-stu-id="e2497-123">You must explicitly specify the name of the output assembly (.exe or .dll) by using the `/out` compiler option.</span></span>  <span data-ttu-id="e2497-124">Per altre informazioni, vedere [/out (Opzioni del compilatore C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e2497-124">For more information, see [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span></span>  
  
7. <span data-ttu-id="e2497-125">Eseguire il file friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="e2497-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="e2497-126">Il programma stampa la stringa "Class1.Test".</span><span class="sxs-lookup"><span data-stu-id="e2497-126">The program prints the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e2497-127">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e2497-127">.NET Framework Security</span></span>  
 <span data-ttu-id="e2497-128">Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="e2497-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="e2497-129">La differenza principale è che <xref:System.Security.Permissions.StrongNameIdentityPermission> può chiedere le autorizzazioni di sicurezza per l'esecuzione di una particolare sezione di codice, mentre l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controlla la visibilità dei membri e dei tipi `internal`.</span><span class="sxs-lookup"><span data-stu-id="e2497-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2497-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2497-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="e2497-131">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="e2497-131">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="e2497-132">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="e2497-132">Friend Assemblies</span></span>](../../../../standard/assembly/friend-assemblies.md)
- [<span data-ttu-id="e2497-133">Procedura: Creare assembly Friend non firmati (C#)</span><span class="sxs-lookup"><span data-stu-id="e2497-133">How to: Create Unsigned Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="e2497-134">/keyfile</span><span class="sxs-lookup"><span data-stu-id="e2497-134">/keyfile</span></span>](../../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)
- [<span data-ttu-id="e2497-135">Sn.exe (strumento Nome sicuro)</span><span class="sxs-lookup"><span data-stu-id="e2497-135">Sn.exe (Strong Name Tool)</span></span>](../../../../framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="e2497-136">Creazione e utilizzo degli assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="e2497-136">Creating and Using Strong-Named Assemblies</span></span>](../../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
- [<span data-ttu-id="e2497-137">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e2497-137">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
