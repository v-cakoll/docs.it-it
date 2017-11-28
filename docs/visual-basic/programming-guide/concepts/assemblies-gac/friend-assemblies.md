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
# <a name="friend-assemblies-visual-basic"></a>Assembly Friend (Visual Basic)
Oggetto *assembly friend* è un assembly che può accedere a un altro assembly [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) tipi e membri. Se un assembly viene riconosciuto di tipo Friend, non è più necessario contrassegnare tipi e membri come pubblici perché altri assembly possano accedervi. Questo metodo è particolarmente utile negli scenari seguenti:  
  
-   Durante gli unit test, quando il codice di test viene eseguito in un assembly separato ma richiede l'accesso ai membri nell'assembly sottoposto a test che sono contrassegnati come `Friend`.  
  
-   Quando si sviluppa una libreria di classi e aggiunte alla libreria sono contenute in assembly distinti, ma richiedono l'accesso ai membri assembly esistenti che sono contrassegnati come `Friend`.  
  
## <a name="remarks"></a>Note  
 È possibile usare l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per identificare uno o più assembly Friend per un determinato assembly. L'esempio seguente usa l'attributo `AssemblyB` nell'assembly A e specifica l'assembly <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> come assembly Friend. In questo modo l'assembly `AssemblyB` può accedere a tutti i tipi e i membri nell'assembly A che sono contrassegnati come `Friend`.  
  
> [!NOTE]
>  Quando si compila un assembly (assembly `AssemblyB`) che deve accedere ai tipi o ai membri interni di un altro assembly (assembly *A*), è necessario specificare in modo esplicito il nome del file di output (con estensione exe o dll) usando l'opzione del compilatore **/out**. Il compilatore non ha infatti ancora generato il nome dell'assembly in fase di compilazione quando crea l'associazione a riferimenti esterni. Per ulteriori informazioni, vedere [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
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
  
 Possono accedere ai tipi e ai membri `Friend` solo gli assembly che sono stati definiti di tipo Friend in modo esplicito. Ad esempio, se l'assembly B è un elemento di tipo Friend per l'assembly A e l'assembly C fa riferimento all'assembly B, l'assembly C non può accedere ai tipi `Friend` in A.  
  
 Il compilatore esegue alcune operazioni di convalida di base del nome dell'assembly Friend che viene passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Se l'assembly *A* dichiara che *B* è un assembly Friend, le regole di convalida sono le seguenti:  
  
-   Se *A* è un assembly con nome sicuro, anche *B* deve essere un assembly con nome sicuro. Il nome dell'assembly Friend passato all'attributo deve includere il nome dell'assembly e la chiave pubblica della chiave con nome sicuro usata per firmare l'assembly *B*.  
  
     Il nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> non può essere il nome sicuro dell'assembly *B*. Non includere la versione dell'assembly, le impostazioni cultura, l'architettura o il token di chiave pubblica.  
  
-   Se *A* non è un assembly con nome sicuro, il nome dell'assembly Friend deve comprendere solo il nome dell'assembly. Per ulteriori informazioni, vedere [procedura: creare assembly non firmati Friend (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).  
  
-   Se *B* è un assembly con nome sicuro, è necessario specificare la chiave con nome sicuro per l'assembly *B* usando l'impostazione di progetto o l'opzione del compilatore `/keyfile` della riga di comando. Per ulteriori informazioni, vedere [procedura: creare Friend gli assembly con firma (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).  
  
 La classe <xref:System.Security.Permissions.StrongNameIdentityPermission> consente anche la condivisione dei tipi, con le differenze seguenti:  
  
-   <xref:System.Security.Permissions.StrongNameIdentityPermission> si applica a un singolo tipo, mentre un assembly Friend si applica all'intero assembly.  
  
-   Se un assembly *A* contiene centinaia di tipi che si vuole condividere con l'assembly *B*, è necessario aggiungere <xref:System.Security.Permissions.StrongNameIdentityPermission> a tutti i tipi. Se invece si usa un assembly Friend, è sufficiente dichiarare una volta che si tratta di una relazione di tipo Friend.  
  
-   Se si usa <xref:System.Security.Permissions.StrongNameIdentityPermission>, i tipi da condividere devono essere dichiarati come pubblici. Se si usa un assembly Friend, i tipi condivisi vengono dichiarati `Friend`.  
  
 Per informazioni su come accedere a un assembly `Friend` tipi e metodi da un file di modulo (file con estensione netmodule), vedere [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 <xref:System.Security.Permissions.StrongNameIdentityPermission>  
 [Procedura: creare assembly Friend non firmati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [Procedura: creare assembly Friend firmati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [Assembly e Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Nozioni di base sulla programmazione](../../../../visual-basic/programming-guide/concepts/index.md)
