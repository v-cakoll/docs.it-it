---
title: 'Procedura: Creare assembly Friend firmati (Visual Basic)'
ms.date: 03/14/2018
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
ms.openlocfilehash: 20d1bb571d9cd354ea3f3dba560743da00c8bf22
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359016"
---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a><span data-ttu-id="bdcc6-102">Procedura: Creare assembly Friend firmati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdcc6-102">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="bdcc6-103">In questo esempio viene illustrato come usare assembly Friend e assembly con nomi sicuri.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="bdcc6-104">È necessario che entrambi i tipi di assembly abbiano un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="bdcc6-105">Gli assembly in questo esempio usano le stesse chiavi. È comunque possibile usare chiavi diverse per i due assembly.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="bdcc6-106">Per creare un assembly firmato e un assembly friend</span><span class="sxs-lookup"><span data-stu-id="bdcc6-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="bdcc6-107">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="bdcc6-108">Eseguire la sequenza di comandi seguente con lo strumento Nome sicuro per generare un keyfile e per visualizzare la relativa chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="bdcc6-109">Per altre informazioni, vedere [Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="bdcc6-109">For more information, see [Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
    1.  <span data-ttu-id="bdcc6-110">Generare una chiave con nome sicuro per questo esempio e archiviarla nel file FriendAssemblies.snk:</span><span class="sxs-lookup"><span data-stu-id="bdcc6-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="bdcc6-111">Estrarre la chiave pubblica da FriendAssemblies.snk e inserirla in FriendAssemblies.publickey:</span><span class="sxs-lookup"><span data-stu-id="bdcc6-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="bdcc6-112">Visualizzare la chiave pubblica archiviata nel file FriendAssemblies.publickey:</span><span class="sxs-lookup"><span data-stu-id="bdcc6-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="bdcc6-113">Creare un file di Visual Basic denominato `friend_signed_A` che contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-113">Create a Visual Basic file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="bdcc6-114">Il codice usa l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per dichiarare friend_signed_B come assembly Friend.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="bdcc6-115">Ogni volta che viene eseguito, lo strumento Nome sicuro genera una chiave pubblica nuova.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="bdcc6-116">È pertanto necessario sostituire la chiave pubblica nel codice seguente con la chiave pubblica appena generata, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
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
  
4.  <span data-ttu-id="bdcc6-117">Compilare e firmare friend_signed_A usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```console  
    Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  <span data-ttu-id="bdcc6-118">Creare un file di Visual Basic denominato `friend_signed_B` e contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-118">Create a Visual Basic file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="bdcc6-119">Poiché friend_signed_A specifica che friend_signed_B è un assembly Friend, il codice in friend_signed_B può accedere ai tipi e ai membri `Friend` da friend_signed_A.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `Friend` types and members from friend_signed_A.</span></span> <span data-ttu-id="bdcc6-120">Il file contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-120">The file contains the following code.</span></span>  
  
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
  
6.  <span data-ttu-id="bdcc6-121">Compilare e firmare friend_signed_B usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```console  
    vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     <span data-ttu-id="bdcc6-122">Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="bdcc6-123">È possibile impostare in modo esplicito l'assembly utilizzando il `-out` opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-123">You can explicitly set the assembly by using the `-out` compiler option.</span></span> <span data-ttu-id="bdcc6-124">Per altre informazioni, vedere [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="bdcc6-124">For more information, see [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
7.  <span data-ttu-id="bdcc6-125">Eseguire il file friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="bdcc6-126">Il programma visualizza la stringa "Class1.Test".</span><span class="sxs-lookup"><span data-stu-id="bdcc6-126">The program displays the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="bdcc6-127">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bdcc6-127">.NET Framework Security</span></span>  
 <span data-ttu-id="bdcc6-128">Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="bdcc6-129">La differenza principale è che <xref:System.Security.Permissions.StrongNameIdentityPermission> può chiedere le autorizzazioni di sicurezza per l'esecuzione di una particolare sezione di codice, mentre l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controlla la visibilità dei membri e dei tipi `Friend`.</span><span class="sxs-lookup"><span data-stu-id="bdcc6-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdcc6-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdcc6-130">See also</span></span>
- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="bdcc6-131">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="bdcc6-131">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="bdcc6-132">Assembly Friend</span><span class="sxs-lookup"><span data-stu-id="bdcc6-132">Friend Assemblies</span></span>](../../../../standard/assembly/friend-assemblies.md)
- [<span data-ttu-id="bdcc6-133">Procedura: Creare assembly Friend non firmati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdcc6-133">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="bdcc6-134">-keyfile</span><span class="sxs-lookup"><span data-stu-id="bdcc6-134">-keyfile</span></span>](../../../../visual-basic/reference/command-line-compiler/keyfile.md)
- <span data-ttu-id="bdcc6-135">[Sn.exe (strumento nome sicuro)](../../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="bdcc6-135">[Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
- [<span data-ttu-id="bdcc6-136">Creazione e utilizzo degli assembly con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="bdcc6-136">Creating and Using Strong-Named Assemblies</span></span>](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md)
- [<span data-ttu-id="bdcc6-137">Nozioni di base sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="bdcc6-137">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
