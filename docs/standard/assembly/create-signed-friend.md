---
title: 'Procedura: creare assembly Friend firmati'
description: Questo articolo illustra come usare assembly Friend con assembly con nomi sicuri. Sono incluse informazioni sulla sicurezza di .NET.
ms.date: 08/19/2019
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
dev_langs:
- csharp
- vb
ms.openlocfilehash: b6176afed44e32911a37a0d753cea2bae7d8554e
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378535"
---
# <a name="how-to-create-signed-friend-assemblies"></a>Procedura: creare assembly Friend firmati
In questo esempio viene illustrato come usare assembly Friend e assembly con nomi sicuri. È necessario che entrambi i tipi di assembly abbiano un nome sicuro. Gli assembly in questo esempio usano le stesse chiavi. È comunque possibile usare chiavi diverse per i due assembly.  
  
## <a name="create-a-signed-assembly-and-a-friend-assembly"></a>Creare un assembly firmato e un assembly Friend  
  
1. Aprire un prompt dei comandi.  
  
2. Eseguire la sequenza di comandi seguente con lo strumento Nome sicuro per generare un keyfile e per visualizzare la relativa chiave pubblica. Per ulteriori informazioni, vedere [sn. exe (strumento nome sicuro)](../../framework/tools/sn-exe-strong-name-tool.md).  
  
    1. Generare una chiave con nome sicuro per questo esempio e archiviarla nel file *FriendAssemblies. snk*:  
  
         `sn -k FriendAssemblies.snk`  
  
    2. Estrarre la chiave pubblica da *FriendAssemblies. snk* e inserirla in *FriendAssemblies. PublicKey*:  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3. Visualizzare la chiave pubblica archiviata nel file *FriendAssemblies. PublicKey*:  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. Creare un file C# o Visual Basic denominato *friend_signed_A* che contiene il codice seguente. Il codice usa l' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributo per dichiarare *friend_signed_B* come assembly Friend.  

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

4. Compilare e firmare *friend_signed_A* usando il comando seguente.  

   ```csharp
   csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
   ```  

   ```vb
   Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
   ```  

5. Creare un file C# o Visual Basic denominato *friend_signed_B* che contiene il codice seguente. Poiché *friend_signed_A* specifica *friend_signed_B* come assembly Friend, il codice in *friend_signed_B* può accedere ai `internal` tipi (C#) o `Friend` (Visual Basic) e ai membri da *friend_signed_A*. Il file contiene il codice seguente.  

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

6. Compilare e firmare *friend_signed_B* usando il comando seguente.  

   ```csharp
   csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
   ```  

   ```vb
   vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
   ```  

   Il nome dell'assembly generato dal compilatore deve corrispondere al nome dell'assembly Friend passato all'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. È necessario specificare in modo esplicito il nome dell'assembly di output (con*estensione exe* o *dll*) utilizzando l' `-out` opzione del compilatore. Per ulteriori informazioni, vedere [-out (opzioni del compilatore C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) o [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).  

7. Eseguire il file *friend_signed_B. exe* .  

   Il programma restituisce la stringa **Class1. test**.  
  
## <a name="net-security"></a>Protezione .NET  
 Ci sono alcune analogie tra l'attributo <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> e la classe <xref:System.Security.Permissions.StrongNameIdentityPermission>. La differenza principale è che <xref:System.Security.Permissions.StrongNameIdentityPermission> può richiedere le autorizzazioni di sicurezza per eseguire una particolare sezione di codice, mentre l' <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attributo controlla la visibilità dei `internal` tipi e membri (C#) o `Friend` (Visual Basic).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Assembly in .NET](index.md)
- [Assembly Friend](friend.md)
- [Procedura: creare assembly Friend non firmati](create-unsigned-friend.md)
- [-filefile (C#)](../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)
- [-filefile (Visual Basic)](../../visual-basic/reference/command-line-compiler/keyfile.md)
- [Sn. exe (strumento nome sicuro)](../../framework/tools/sn-exe-strong-name-tool.md)
- [Creare e usare gli assembly con nome sicuro](create-use-strong-named.md)
- [Guida per programmatori C#](../../csharp/programming-guide/index.md)
- [Concetti di programmazione (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
