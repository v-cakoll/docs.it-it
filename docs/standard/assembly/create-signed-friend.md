---
title: 'Procedura: creare assembly friend firmatiHow to: Create signed friend assemblies'
ms.date: 08/19/2019
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
dev_langs:
- csharp
- vb
ms.openlocfilehash: 9912fa70014a8828e994cf528644aaa7cb351fea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159494"
---
# <a name="how-to-create-signed-friend-assemblies"></a>Procedura: creare assembly friend firmatiHow to: Create signed friend assemblies
In questo esempio viene illustrato come usare assembly Friend e assembly con nomi sicuri. È necessario che entrambi i tipi di assembly abbiano un nome sicuro. Gli assembly in questo esempio usano le stesse chiavi. È comunque possibile usare chiavi diverse per i due assembly.  
  
## <a name="create-a-signed-assembly-and-a-friend-assembly"></a>Creare un assembly firmato e un assembly friendCreate a signed assembly and a friend assembly  
  
1. Aprire un prompt dei comandi.  
  
2. Eseguire la sequenza di comandi seguente con lo strumento Nome sicuro per generare un keyfile e per visualizzare la relativa chiave pubblica. Per ulteriori informazioni, vedere [Sn.exe (strumento Nome sicuro)](../../framework/tools/sn-exe-strong-name-tool.md).  
  
    1. Generare una chiave con nome sicuro per questo esempio e archiviarla nel file *FriendAssemblies.snk*:  
  
         `sn -k FriendAssemblies.snk`  
  
    2. Estrarre la chiave pubblica da *FriendAssemblies.snk* e inserirla in *FriendAssemblies.publickey*:  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3. Visualizzare la chiave pubblica archiviata nel file *FriendAssemblies.publickey*:  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. Creare un file di Visual Basic denominato *friend_signed_A* che contiene il codice seguente. Il codice <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> utilizza l'attributo per dichiarare *friend_signed_B* come assembly Friend.  

   Ogni volta che viene eseguito, lo strumento Nome sicuro genera una chiave pubblica nuova. È pertanto necessario sostituire la chiave pubblica nel codice seguente con la chiave pubblica appena generata, come illustrato nell'esempio seguente.  

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

4. Compilare e firmare *friend_signed_A* utilizzando il comando seguente.  

   ```csharp
   csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
   ```  

   ```vb
   Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
   ```  

5. Creare un file di C o Visual Basic denominato *friend_signed_B* che contiene il codice seguente. Poiché *friend_signed_A* specifica *friend_signed_B* come assembly Friend, `internal` il codice in `Friend` *friend_signed_B* può accedere ai tipi e ai membri (C) o (Visual Basic) da *friend_signed_A*. Il file contiene il codice seguente.  

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

6. Compilare e firmare *friend_signed_B* utilizzando il comando seguente.  

   ```csharp
   csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
   ```  

   ```vb
   vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
   ```  

   Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. È necessario specificare in modo esplicito il nome dell'assembly di output (*.exe* o *.dll*) utilizzando l'opzione del `-out` compilatore. Per ulteriori informazioni, vedere [-out (opzioni del compilatore C)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).  

7. Eseguire il file *friend_signed_B.exe.*  

   Il programma restituisce la stringa **Class1.Test**.  
  
## <a name="net-security"></a>Protezione .NET  
 Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>. La differenza principale <xref:System.Security.Permissions.StrongNameIdentityPermission> è che può richiedere autorizzazioni di sicurezza <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> per l'esecuzione di una particolare sezione di codice, mentre l'attributo controlla la visibilità di `internal` (C ) o `Friend` (Visual Basic) tipi e membri.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Assembly in .NET](index.md)
- [Assembly Friend](friend.md)
- [Procedura: creare assembly friend non firmatiHow to: Create unsigned Friend assemblies](create-unsigned-friend.md)
- [-keyfile (C](../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)
- [-keyfile (Visual Basic)](../../visual-basic/reference/command-line-compiler/keyfile.md)
- [Sn.exe (strumento Nome sicuro)](../../framework/tools/sn-exe-strong-name-tool.md)
- [Creare e usare gli assembly con nome sicuro](create-use-strong-named.md)
- [Guida alla programmazione in C](../../csharp/programming-guide/index.md)
- [Concetti di programmazione (Visual Basic)Programming concepts (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
