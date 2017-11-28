---
title: Assembly Friend (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d3a37629582e4fc2606afaf606735464c0d247a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="friend-assemblies-visual-basic"></a><span data-ttu-id="61f99-102">Assembly Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61f99-102">Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="61f99-103">Oggetto *assembly friend* è un assembly che può accedere a un altro assembly [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) tipi e membri.</span><span class="sxs-lookup"><span data-stu-id="61f99-103">A *friend assembly* is an assembly that can access another assembly's [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) types and members.</span></span> <span data-ttu-id="61f99-104">Se un assembly viene riconosciuto di tipo Friend, non è più necessario contrassegnare tipi e membri come pubblici perché altri assembly possano accedervi.</span><span class="sxs-lookup"><span data-stu-id="61f99-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="61f99-105">Questo metodo è particolarmente utile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="61f99-105">This is especially convenient in the following scenarios:</span></span>  
  
-   <span data-ttu-id="61f99-106">Durante gli unit test, quando il codice di test viene eseguito in un assembly separato ma richiede l'accesso ai membri nell'assembly sottoposto a test che sono contrassegnati come `Friend`.</span><span class="sxs-lookup"><span data-stu-id="61f99-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `Friend`.</span></span>  
  
-   <span data-ttu-id="61f99-107">Quando si sviluppa una libreria di classi e aggiunte alla libreria sono contenute in assembly distinti, ma richiedono l'accesso ai membri assembly esistenti che sono contrassegnati come `Friend`.</span><span class="sxs-lookup"><span data-stu-id="61f99-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `Friend`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61f99-108">Note</span><span class="sxs-lookup"><span data-stu-id="61f99-108">Remarks</span></span>  
 <span data-ttu-id="61f99-109">È possibile usare l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per identificare uno o più assembly Friend per un determinato assembly.</span><span class="sxs-lookup"><span data-stu-id="61f99-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="61f99-110">L'esempio seguente usa l'attributo `AssemblyB` nell'assembly A e specifica l'assembly <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> come assembly Friend.</span><span class="sxs-lookup"><span data-stu-id="61f99-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="61f99-111">In questo modo l'assembly `AssemblyB` può accedere a tutti i tipi e i membri nell'assembly A che sono contrassegnati come `Friend`.</span><span class="sxs-lookup"><span data-stu-id="61f99-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `Friend`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61f99-112">Quando si compila un assembly (assembly `AssemblyB`) che deve accedere ai tipi o ai membri interni di un altro assembly (assembly *A*), è necessario specificare in modo esplicito il nome del file di output (con estensione exe o dll) usando l'opzione del compilatore **/out**.</span><span class="sxs-lookup"><span data-stu-id="61f99-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="61f99-113">Il compilatore non ha infatti ancora generato il nome dell'assembly in fase di compilazione quando crea l'associazione a riferimenti esterni.</span><span class="sxs-lookup"><span data-stu-id="61f99-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="61f99-114">Per ulteriori informazioni, vedere [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="61f99-114">For more information, see [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
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
  
 <span data-ttu-id="61f99-115">Possono accedere ai tipi e ai membri `Friend` solo gli assembly che sono stati definiti di tipo Friend in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="61f99-115">Only assemblies that you explicitly specify as friends can access `Friend` types and members.</span></span> <span data-ttu-id="61f99-116">Ad esempio, se l'assembly B è un elemento di tipo Friend per l'assembly A e l'assembly C fa riferimento all'assembly B, l'assembly C non può accedere ai tipi `Friend` in A.</span><span class="sxs-lookup"><span data-stu-id="61f99-116">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `Friend` types in A.</span></span>  
  
 <span data-ttu-id="61f99-117">Il compilatore esegue alcune operazioni di convalida di base del nome dell'assembly Friend che viene passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="61f99-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="61f99-118">Se l'assembly *A* dichiara che *B* è un assembly Friend, le regole di convalida sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="61f99-118">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>  
  
-   <span data-ttu-id="61f99-119">Se *A* è un assembly con nome sicuro, anche *B* deve essere un assembly con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="61f99-119">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="61f99-120">Il nome dell'assembly Friend passato all'attributo deve includere il nome dell'assembly e la chiave pubblica della chiave con nome sicuro usata per firmare l'assembly *B*.</span><span class="sxs-lookup"><span data-stu-id="61f99-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>  
  
     <span data-ttu-id="61f99-121">Il nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> non può essere il nome sicuro dell'assembly *B*. Non includere la versione dell'assembly, le impostazioni cultura, l'architettura o il token di chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="61f99-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>  
  
-   <span data-ttu-id="61f99-122">Se *A* non è un assembly con nome sicuro, il nome dell'assembly Friend deve comprendere solo il nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="61f99-122">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="61f99-123">Per ulteriori informazioni, vedere [procedura: creare assembly non firmati Friend (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="61f99-123">For more information, see [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>  
  
-   <span data-ttu-id="61f99-124">Se *B* è un assembly con nome sicuro, è necessario specificare la chiave con nome sicuro per l'assembly *B* usando l'impostazione di progetto o l'opzione del compilatore `/keyfile` della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="61f99-124">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="61f99-125">Per ulteriori informazioni, vedere [procedura: creare Friend gli assembly con firma (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="61f99-125">For more information, see [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="61f99-126">La classe <xref:System.Security.Permissions.StrongNameIdentityPermission> consente anche la condivisione dei tipi, con le differenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="61f99-126">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>  
  
-   <span data-ttu-id="61f99-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> si applica a un singolo tipo, mentre un assembly Friend si applica all'intero assembly.</span><span class="sxs-lookup"><span data-stu-id="61f99-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>  
  
-   <span data-ttu-id="61f99-128">Se un assembly *A* contiene centinaia di tipi che si vuole condividere con l'assembly *B*, è necessario aggiungere <xref:System.Security.Permissions.StrongNameIdentityPermission> a tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="61f99-128">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="61f99-129">Se invece si usa un assembly Friend, è sufficiente dichiarare una volta che si tratta di una relazione di tipo Friend.</span><span class="sxs-lookup"><span data-stu-id="61f99-129">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>  
  
-   <span data-ttu-id="61f99-130">Se si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, i tipi da condividere devono essere dichiarati come pubblici.</span><span class="sxs-lookup"><span data-stu-id="61f99-130">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="61f99-131">Se si usa un assembly Friend, i tipi condivisi vengono dichiarati `Friend`.</span><span class="sxs-lookup"><span data-stu-id="61f99-131">If you use a friend assembly, the shared types are declared as `Friend`.</span></span>  
  
 <span data-ttu-id="61f99-132">Per informazioni su come accedere a un assembly `Friend` tipi e metodi da un file di modulo (file con estensione netmodule), vedere [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span><span class="sxs-lookup"><span data-stu-id="61f99-132">For information about how to access an assembly's `Friend` types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61f99-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61f99-133">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 <xref:System.Security.Permissions.StrongNameIdentityPermission>  
 [<span data-ttu-id="61f99-134">Procedura: creare assembly Friend non firmati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61f99-134">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [<span data-ttu-id="61f99-135">Procedura: creare assembly Friend firmati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61f99-135">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [<span data-ttu-id="61f99-136">Assembly e Global Assembly Cache (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61f99-136">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="61f99-137">Nozioni di base sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="61f99-137">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
