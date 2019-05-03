---
title: 'Procedura: Creare assembly Friend non firmati (Visual Basic)'
ms.date: 03/14/2018
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
ms.openlocfilehash: 4771d0fe116d1532c270cf41b209665d5403a9b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022233"
---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a>Procedura: Creare assembly Friend non firmati (Visual Basic)
In questo esempio viene illustrato come usare assembly Friend e assembly non firmati.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>Per creare un assembly e un assembly Friend  
  
1. Aprire un prompt dei comandi.  
  
2. Creare un file di Visual Basic denominato `friend_signed_A.` che contiene il codice seguente. Il codice usa l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per dichiarare friend_signed_B come assembly Friend.  
  
    ```vb  
    ' friend_unsigned_A.vb  
    ' Compile with:   
    ' vbc -target:library friend_unsigned_A.vb  
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
  
3. Compilare e firmare friend_signed_A usando il comando seguente.  
  
    ```console  
    vbc -target:library friend_unsigned_A.vb  
    ```  
  
4. Creare un file di Visual Basic denominato `friend_unsigned_B` che contiene il codice seguente. Poiché friend_unsigned_A specifica che friend_unsigned_B è un assembly Friend, il codice in friend_unsigned_B può accedere ai tipi e ai membri `Friend` da friend_unsigned_A.  
  
    ```vb  
    ' friend_unsigned_B.vb  
    ' Compile with:   
    ' vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb  
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
  
5. Compilare friend_signed_B usando il comando seguente.  
  
    ```console
    vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. È possibile impostare in modo esplicito l'assembly utilizzando il `/out` opzione del compilatore.  
  
6. Eseguire il file friend_signed_B.exe.  
  
     Il programma visualizza due stringhe: "Class1.Test" e "Class2.Test".  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>. La differenza principale è che <xref:System.Security.Permissions.StrongNameIdentityPermission> può chiedere le autorizzazioni di sicurezza per l'esecuzione di una particolare sezione di codice, mentre l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> controlla la visibilità dei membri e dei tipi `Friend`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Assembly in .NET](../../../../standard/assembly/index.md)
- [Assembly Friend](../../../../standard/assembly/friend-assemblies.md)
- [Procedura: Creare assembly Friend firmati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [Concetti relativi alla Guida di programmazione](../../../../visual-basic/programming-guide/concepts/index.md)
