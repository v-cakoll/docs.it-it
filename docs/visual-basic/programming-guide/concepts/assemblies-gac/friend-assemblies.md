---
title: Assembly Friend (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 23c9167bf6a632b53202bdc56aebb2248065e967
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="friend-assemblies-visual-basic"></a><span data-ttu-id="c4e2f-102">Assembly Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4e2f-102">Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="c4e2f-103">Oggetto *assembly friend* è un assembly che può accedere a un altro assembly [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) tipi e membri.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-103">A *friend assembly* is an assembly that can access another assembly's [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) types and members.</span></span> <span data-ttu-id="c4e2f-104">Se si individua un assembly come assembly friend, non è necessario contrassegnare tipi e membri come pubblici affinché possano essere accessibili da altri assembly.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="c4e2f-105">Questo è particolarmente utile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4e2f-105">This is especially convenient in the following scenarios:</span></span>  
  
-   <span data-ttu-id="c4e2f-106">Durante gli unit test, quando il codice di test viene eseguito in un assembly separato ma richiede l'accesso ai membri nell'assembly sottoposto a test che sono contrassegnati come `Friend`.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `Friend`.</span></span>  
  
-   <span data-ttu-id="c4e2f-107">Quando si sviluppa una libreria di classi e le aggiunte alla libreria sono contenute in assembly separati ma richiedono l'accesso ai membri nell'assembly esistenti contrassegnati come `Friend`.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `Friend`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4e2f-108">Note</span><span class="sxs-lookup"><span data-stu-id="c4e2f-108">Remarks</span></span>  
 <span data-ttu-id="c4e2f-109">È possibile utilizzare il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>attributo per identificare uno o più assembly friend per un determinato assembly.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="c4e2f-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="c4e2f-110">Nell'esempio seguente viene utilizzata la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>attributo nell'assembly e specifica l'assembly `AssemblyB` come assembly friend.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="c4e2f-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="c4e2f-111">In questo modo l'assembly `AssemblyB` accesso a tutti i tipi e membri nell'assembly che sono contrassegnati come `Friend`.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `Friend`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4e2f-112">Quando si compila un assembly (assembly `AssemblyB`) che accederà ai tipi interni o i membri interni di un altro assembly (assembly *A*), è necessario specificare esplicitamente il nome del file di output (.exe o DLL) utilizzando il **/out** l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="c4e2f-113">Ciò è necessario perché il compilatore non ha ancora generato il nome dell'assembly in fase di compilazione in fase di che cui è associato a riferimenti esterni.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="c4e2f-114">Per ulteriori informazioni, vedere [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="c4e2f-114">For more information, see [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports System  
<Assembly: InternalsVisibleTo("AssemblyB")>   
  
' Friend class.  
Friend Class FriendClass  
    Public Sub Test()  
        Console.WriteLine("Sample Class")  
    End Sub  
End Class  
  
' Public class with a Friend method.  
Public Class ClassWithFriendMethod  
    Friend Sub Test()  
        Console.WriteLine("Sample Method")  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="c4e2f-115">Solo gli assembly specificati in modo esplicito come Friend possono accedere `Friend` tipi e membri.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-115">Only assemblies that you explicitly specify as friends can access `Friend` types and members.</span></span> <span data-ttu-id="c4e2f-116">Ad esempio, se l'assembly B è un elemento friend di assembly A e assembly C fa riferimento all'assembly B, C non dispone dell'accesso al `Friend` tipi di A.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-116">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `Friend` types in A.</span></span>  
  
 <span data-ttu-id="c4e2f-117">Il compilatore esegue alcune convalide di base del nome dell'assembly friend passato per il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>attributo.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="c4e2f-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="c4e2f-118">Se assembly *A* dichiara *B* come assembly friend, le regole di convalida sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4e2f-118">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>  
  
-   <span data-ttu-id="c4e2f-119">Se assembly *A* è con nome sicuro, assembly *B* deve avere un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-119">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="c4e2f-120">Il nome dell'assembly friend passato all'attributo deve includere il nome dell'assembly e la chiave pubblica della chiave con nome sicuro utilizzato per firmare l'assembly *B*.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>  
  
     <span data-ttu-id="c4e2f-121">Il nome dell'assembly friend che viene passato per il <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>attributo non può essere il nome sicuro dell'assembly *B*: non includono la versione dell'assembly, le impostazioni cultura, architettura o token di chiave pubblica.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="c4e2f-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>  
  
-   <span data-ttu-id="c4e2f-122">Se assembly *A* non è sicuro denominata, il nome dell'assembly friend deve essere costituito solo il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-122">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="c4e2f-123">Per ulteriori informazioni, vedere [procedura: creare assembly non firmati Friend (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="c4e2f-123">For more information, see [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>  
  
-   <span data-ttu-id="c4e2f-124">Se assembly *B* è con nome sicuro, è necessario specificare la chiave con nome sicuro per l'assembly *B* utilizzando l'impostazione di progetto o la riga di comando `/keyfile` l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-124">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="c4e2f-125">Per ulteriori informazioni, vedere [procedura: creare effettuato l'accesso Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="c4e2f-125">For more information, see [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="c4e2f-126">La <xref:System.Security.Permissions.StrongNameIdentityPermission>classe fornisce inoltre la possibilità di condividere i tipi, con le seguenti differenze:</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="c4e2f-126">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>  
  
-   <span data-ttu-id="c4e2f-127"><xref:System.Security.Permissions.StrongNameIdentityPermission>si applica a un singolo tipo, mentre un assembly friend valido per l'intero assembly.</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="c4e2f-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>  
  
-   <span data-ttu-id="c4e2f-128">Se sono presenti centinaia di tipi in assembly *A* che si desidera condividere con assembly *B*, è necessario aggiungere <xref:System.Security.Permissions.StrongNameIdentityPermission>su tutti gli elementi.</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="c4e2f-128">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="c4e2f-129">Se si utilizza un assembly friend, è sufficiente dichiarare la relazione friend una sola volta.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-129">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>  
  
-   <span data-ttu-id="c4e2f-130">Se si utilizza <xref:System.Security.Permissions.StrongNameIdentityPermission>, i tipi che si desidera condividere devono essere dichiarati come pubblici.</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="c4e2f-130">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="c4e2f-131">Se si utilizza un assembly friend, i tipi condivisi vengono dichiarati come `Friend`.</span><span class="sxs-lookup"><span data-stu-id="c4e2f-131">If you use a friend assembly, the shared types are declared as `Friend`.</span></span>  
  
 <span data-ttu-id="c4e2f-132">Per informazioni su come accedere a un assembly `Friend` tipi e metodi da un file di modulo (file con estensione netmodule), vedere [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span><span class="sxs-lookup"><span data-stu-id="c4e2f-132">For information about how to access an assembly's `Friend` types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e2f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4e2f-133">See Also</span></span>  
 <span data-ttu-id="c4e2f-134"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="c4e2f-134"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
 <span data-ttu-id="c4e2f-135"><xref:System.Security.Permissions.StrongNameIdentityPermission></xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="c4e2f-135"><xref:System.Security.Permissions.StrongNameIdentityPermission></span></span>   
<span data-ttu-id="c4e2f-136"> [Procedura: creare assembly Friend non firmati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="c4e2f-136"> [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span></span>  
<span data-ttu-id="c4e2f-137"> [Procedura: creare assembly Friend firmati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="c4e2f-137"> [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span></span>  
<span data-ttu-id="c4e2f-138"> [Gli assembly e Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="c4e2f-138"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="c4e2f-139"> [Nozioni di base sulla programmazione](../../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="c4e2f-139"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)</span></span>
