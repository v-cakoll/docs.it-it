---
title: 'Procedura: creare assembly Friend non firmati (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
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
ms.openlocfilehash: d184b5d6f8334df46351d3f2974f1fb91e54a492
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a><span data-ttu-id="a6ed8-102">Procedura: creare assembly Friend non firmati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a6ed8-102">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="a6ed8-103">In questo esempio viene illustrato come utilizzare gli assembly friend con assembly non firmati.</span><span class="sxs-lookup"><span data-stu-id="a6ed8-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="a6ed8-104">Per creare un assembly e un assembly friend</span><span class="sxs-lookup"><span data-stu-id="a6ed8-104">To create an assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="a6ed8-105">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a6ed8-105">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="a6ed8-106">Creare un file di Visual Basic denominato `friend_signed_A.` che contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a6ed8-106">Create a Visual Basic file named `friend_signed_A.` that contains the following code.</span></span> <span data-ttu-id="a6ed8-107">Il codice utilizza il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>attributo per dichiarare friend_signed_B come assembly friend.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="a6ed8-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
    ```vb  
    ' friend_unsigned_A.vb  
    ' Compile with:   
    ' Vbc /target:library friend_unsigned_A.vb  
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
  
3.  <span data-ttu-id="a6ed8-108">Compilare e firmare friend_signed_A utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="a6ed8-108">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```vb  
    Vbc /target:library friend_unsigned_A.vb  
    ```  
  
4.  <span data-ttu-id="a6ed8-109">Creare un file di Visual Basic denominato `friend_unsigned_B` che contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="a6ed8-109">Create a Visual Basic file named `friend_unsigned_B` that contains the following code.</span></span> <span data-ttu-id="a6ed8-110">Poiché friend_unsigned_A specifica friend_unsigned_B come assembly friend, il codice di friend_unsigned_B può accedere `Friend` tipi e membri da friend_unsigned_A.</span><span class="sxs-lookup"><span data-stu-id="a6ed8-110">Because friend_unsigned_A specifies friend_unsigned_B as a friend assembly, the code in friend_unsigned_B can access `Friend` types and members from friend_unsigned_A.</span></span>  
  
    ```vb  
    ' friend_unsigned_B.vb  
    ' Compile with:   
    ' Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
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
  
5.  <span data-ttu-id="a6ed8-111">Compilare friend_signed_B utilizzando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="a6ed8-111">Compile friend_signed_B by using the following command.</span></span>  
  
    ```vb  
    Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     <span data-ttu-id="a6ed8-112">Il nome dell'assembly generato dal compilatore deve corrispondere il nome dell'assembly friend che viene passato per il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>attributo.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="a6ed8-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="a6ed8-113">È possibile impostare in modo esplicito l'assembly utilizzando il `/out` l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="a6ed8-113">You can explicitly set the assembly by using the `/out` compiler option.</span></span>  
  
6.  <span data-ttu-id="a6ed8-114">Eseguire il file friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="a6ed8-114">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="a6ed8-115">Il programma stampa due stringhe: "Class1" e "Class2. test".</span><span class="sxs-lookup"><span data-stu-id="a6ed8-115">The program prints two strings: "Class1.Test" and "Class2.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a6ed8-116">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a6ed8-116">.NET Framework Security</span></span>  
 <span data-ttu-id="a6ed8-117">Esistono analogie tra l' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>attributo e la <xref:System.Security.Permissions.StrongNameIdentityPermission>classe.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="a6ed8-117">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="a6ed8-118">La differenza principale è che <xref:System.Security.Permissions.StrongNameIdentityPermission>può richiedere le autorizzazioni di sicurezza per l'esecuzione di una particolare sezione di codice, mentre il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>attributo controlla la visibilità di `Friend` tipi e membri.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="a6ed8-118">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ed8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6ed8-119">See Also</span></span>  
 <span data-ttu-id="a6ed8-120"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="a6ed8-120"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
<span data-ttu-id="a6ed8-121"> [Gli assembly e Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="a6ed8-121"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="a6ed8-122"> [Assembly Friend (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="a6ed8-122"> [Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span></span>  
<span data-ttu-id="a6ed8-123"> [Procedura: creare assembly Friend firmati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="a6ed8-123"> [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span></span>  
<span data-ttu-id="a6ed8-124"> [Concetti relativi alla Guida di programmazione](../../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="a6ed8-124"> [Programming Guide Concepts](../../../../visual-basic/programming-guide/concepts/index.md)</span></span>
