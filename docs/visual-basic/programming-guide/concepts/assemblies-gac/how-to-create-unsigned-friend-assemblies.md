---
title: 'Procedura: creare assembly Friend non firmati (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a2b2667c60a07a2897a0934d210901042e2e43c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a>Procedura: creare assembly Friend non firmati (Visual Basic)
In questo esempio viene illustrato come usare assembly Friend e assembly non firmati.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>Per creare un assembly e un assembly Friend  
  
1.  Aprire un prompt dei comandi.  
  
2.  Creare un file di Visual Basic denominato `friend_signed_A.` che contiene il codice seguente. Il codice usa l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per dichiarare friend_signed_B come assembly Friend.  
  
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
  
3.  Compilare e firmare friend_signed_A usando il comando seguente.  
  
    ```vb  
    Vbc /target:library friend_unsigned_A.vb  
    ```  
  
4.  Creare un file di Visual Basic denominato `friend_unsigned_B` che contiene il codice seguente. Poiché friend_unsigned_A specifica che friend_unsigned_B è un assembly Friend, il codice in friend_unsigned_B può accedere ai tipi e ai membri `Friend` da friend_unsigned_A.  
  
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
  
5.  Compilare friend_signed_B usando il comando seguente.  
  
    ```vb  
    Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. È possibile impostare in modo esplicito l'assembly utilizzando il `/out` l'opzione del compilatore.  
  
6.  Eseguire il file friend_signed_B.exe.  
  
     Il programma stampa due stringhe: "Class1.Test" e "Class2.Test".  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>. La differenza principale è che <xref:System.Security.Permissions.StrongNameIdentityPermission> può chiedere le autorizzazioni di sicurezza per l'esecuzione di una particolare sezione di codice, mentre l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controlla la visibilità dei membri e dei tipi `Friend`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [Assembly e Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Assembly Friend (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [Procedura: creare assembly Friend firmati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [Concetti relativi alla Guida di programmazione](../../../../visual-basic/programming-guide/concepts/index.md)
