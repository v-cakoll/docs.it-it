---
title: 'Procedura: creare assembly Friend firmati (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a8a7df331c8cd93de45d902cb9b6c67460952c6d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a><span data-ttu-id="e6d5e-102">Procedura: creare assembly Friend firmati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6d5e-102">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="e6d5e-103">In questo esempio viene illustrato come utilizzare gli assembly friend con assembly con nomi sicuri.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="e6d5e-104">Entrambi gli assembly devono essere sicuro.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="e6d5e-105">Anche se entrambi gli assembly in questo esempio utilizzano le stesse chiavi, è possibile utilizzare chiavi diverse per due assembly.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="e6d5e-106">Per creare un assembly firmato e un assembly friend</span><span class="sxs-lookup"><span data-stu-id="e6d5e-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="e6d5e-107">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="e6d5e-108">Utilizzare la seguente sequenza di comandi con lo strumento nome sicuro per generare un file di chiave e per visualizzare la relativa chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="e6d5e-109">Per altre informazioni, vedere [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span><span class="sxs-lookup"><span data-stu-id="e6d5e-109">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
    1.  <span data-ttu-id="e6d5e-110">Generare una chiave con nome sicuro per questo esempio e archiviarlo nel file FriendAssemblies. snk:</span><span class="sxs-lookup"><span data-stu-id="e6d5e-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="e6d5e-111">Estrarre la chiave pubblica da FriendAssemblies. snk e inserirla in FriendAssemblies. publickey:</span><span class="sxs-lookup"><span data-stu-id="e6d5e-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="e6d5e-112">Visualizzare la chiave pubblica archiviata nel file FriendAssemblies. publickey:</span><span class="sxs-lookup"><span data-stu-id="e6d5e-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="e6d5e-113">Creare un file di Visual Basic denominato `friend_signed_A` che contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-113">Create a Visual Basic file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="e6d5e-114">Il codice utilizza il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>attributo per dichiarare friend_signed_B come assembly friend.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="e6d5e-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="e6d5e-115">Ogni volta che viene eseguito, lo strumento nome sicuro genera una nuova chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="e6d5e-116">Pertanto, è necessario sostituire la chiave pubblica nel codice seguente con la chiave pubblica che appena generato, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    Imports System.Runtime.CompilerServices  
  
    <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>   
    Public Class Class1  
        Public Sub Test()  
            System.Console.WriteLine("Class1.Test")  
            System.Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
4.  <span data-ttu-id="e6d5e-117">Compilare e firmare friend_signed_A utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```vb  
    Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  <span data-ttu-id="e6d5e-118">Creare un file di Visual Basic denominato `friend_signed_B` e contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-118">Create a Visual Basic file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="e6d5e-119">Poiché friend_signed_A specifica friend_signed_B come assembly friend, il codice in friend_signed_B può accedere `Friend` tipi e membri da friend_signed_A.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `Friend` types and members from friend_signed_A.</span></span> <span data-ttu-id="e6d5e-120">Il file contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-120">The file contains the following code.</span></span>  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="e6d5e-121">Compilare e firmare friend_signed_B utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```vb  
    Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     <span data-ttu-id="e6d5e-122">Il nome dell'assembly generato dal compilatore deve corrispondere il nome dell'assembly friend passato per il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>attributo.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="e6d5e-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="e6d5e-123">È possibile impostare in modo esplicito l'assembly utilizzando il `/out` l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-123">You can explicitly set the assembly by using the `/out` compiler option.</span></span> <span data-ttu-id="e6d5e-124">Per ulteriori informazioni, vedere [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="e6d5e-124">For more information, see [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
7.  <span data-ttu-id="e6d5e-125">Eseguire il file friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="e6d5e-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="e6d5e-126">Il programma stampa la stringa "Class1".</span><span class="sxs-lookup"><span data-stu-id="e6d5e-126">The program prints the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e6d5e-127">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e6d5e-127">.NET Framework Security</span></span>  
 <span data-ttu-id="e6d5e-128">Esistono analogie tra l' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>attributo e la <xref:System.Security.Permissions.StrongNameIdentityPermission>classe.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="e6d5e-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="e6d5e-129">La differenza principale è che <xref:System.Security.Permissions.StrongNameIdentityPermission>può richiedere le autorizzazioni di sicurezza per l'esecuzione di una particolare sezione di codice, mentre il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>attributo controlla la visibilità di `Friend` tipi e membri.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="e6d5e-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d5e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6d5e-130">See Also</span></span>  
 <span data-ttu-id="e6d5e-131"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="e6d5e-131"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
<span data-ttu-id="e6d5e-132"> [Gli assembly e Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6d5e-132"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="e6d5e-133"> [Assembly Friend (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="e6d5e-133"> [Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span></span>  
<span data-ttu-id="e6d5e-134"> [Procedura: creare assembly Friend non firmati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="e6d5e-134"> [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span></span>  
<span data-ttu-id="e6d5e-135"> [/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="e6d5e-135"> [/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
<span data-ttu-id="e6d5e-136"> [Sn.exe (strumento nome sicuro)](https://msdn.microsoft.com/library/k5b5tt23) </span><span class="sxs-lookup"><span data-stu-id="e6d5e-136"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span></span>  
<span data-ttu-id="e6d5e-137"> [Creazione e utilizzo di assembly con nomi sicuri](https://msdn.microsoft.com/library/xwb8f617) </span><span class="sxs-lookup"><span data-stu-id="e6d5e-137"> [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) </span></span>  
<span data-ttu-id="e6d5e-138"> [Nozioni di base sulla programmazione](../../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="e6d5e-138"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)</span></span>
