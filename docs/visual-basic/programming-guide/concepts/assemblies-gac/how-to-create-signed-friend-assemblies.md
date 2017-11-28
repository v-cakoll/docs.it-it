---
title: 'Procedura: creare assembly Friend firmati (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f87f816992bdfa9ed347c35ba651c59187551772
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a>Procedura: creare assembly Friend firmati (Visual Basic)
In questo esempio viene illustrato come usare assembly Friend e assembly con nomi sicuri. È necessario che entrambi i tipi di assembly abbiano un nome sicuro. Gli assembly in questo esempio usano le stesse chiavi. È comunque possibile usare chiavi diverse per i due assembly.  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a>Per creare un assembly firmato e un assembly friend  
  
1.  Aprire un prompt dei comandi.  
  
2.  Eseguire la sequenza di comandi seguente con lo strumento Nome sicuro per generare un keyfile e per visualizzare la relativa chiave pubblica. Per altre informazioni, vedere [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).  
  
    1.  Generare una chiave con nome sicuro per questo esempio e archiviarla nel file FriendAssemblies.snk:  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  Estrarre la chiave pubblica da FriendAssemblies.snk e inserirla in FriendAssemblies.publickey:  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  Visualizzare la chiave pubblica archiviata nel file FriendAssemblies.publickey:  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  Creare un file di Visual Basic denominato `friend_signed_A` che contiene il codice seguente. Il codice usa l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per dichiarare friend_signed_B come assembly Friend.  
  
     Ogni volta che viene eseguito, lo strumento Nome sicuro genera una chiave pubblica nuova. È pertanto necessario sostituire la chiave pubblica nel codice seguente con la chiave pubblica appena generata, come illustrato nell'esempio seguente.  
  
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
  
4.  Compilare e firmare friend_signed_A usando il comando seguente.  
  
    ```vb  
    Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  Creare un file di Visual Basic denominato `friend_signed_B` e contiene il codice seguente. Poiché friend_signed_A specifica che friend_signed_B è un assembly Friend, il codice in friend_signed_B può accedere ai tipi e ai membri `Friend` da friend_signed_A. Il file contiene il codice seguente.  
  
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
  
6.  Compilare e firmare friend_signed_B usando il comando seguente.  
  
    ```vb  
    Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. È possibile impostare in modo esplicito l'assembly utilizzando il `/out` l'opzione del compilatore. Per ulteriori informazioni, vedere [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
7.  Eseguire il file friend_signed_B.exe.  
  
     Il programma stampa la stringa "Class1.Test".  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>. La differenza principale è che <xref:System.Security.Permissions.StrongNameIdentityPermission> può chiedere le autorizzazioni di sicurezza per l'esecuzione di una particolare sezione di codice, mentre l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controlla la visibilità dei membri e dei tipi `Friend`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [Assembly e Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Assembly Friend (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [Procedura: creare assembly Friend non firmati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [Sn.exe (strumento Nome sicuro)](https://msdn.microsoft.com/library/k5b5tt23)  
 [Creazione e utilizzo degli assembly con nome sicuro](https://msdn.microsoft.com/library/xwb8f617)  
 [Nozioni di base sulla programmazione](../../../../visual-basic/programming-guide/concepts/index.md)
