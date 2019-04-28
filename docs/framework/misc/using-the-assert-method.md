---
title: Utilizzo del metodo Assert
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- granting permissions, overriding security checks
- code access security, overriding security checks
- overriding security checks
- security [.NET Framework], overriding security checks
- security [.NET Framework], assertions
- asserted permissions
- Assert method
- caller security checks
- permissions [.NET Framework], overriding security checks
- permissions [.NET Framework], assertions
ms.assetid: 1e40f4d3-fb7d-4f19-b334-b6076d469ea9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08b46d96f9fb950602766639559a375a25747010
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61869012"
---
# <a name="using-the-assert-method"></a>Utilizzo del metodo Assert
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <xref:System.Security.CodeAccessPermission.Assert%2A> è un metodo che può essere chiamato nelle classi di autorizzazione di accesso al codice e nella classe <xref:System.Security.PermissionSet>. È possibile usare **Assert** per consentire al codice (e ai chiamanti downstream) eseguire le azioni che il codice dispone delle autorizzazioni, ma i chiamanti non disponga dell'autorizzazione necessaria. Un'asserzione di sicurezza modifica il normale processo eseguito dal runtime durante un controllo di sicurezza. Mediante l'asserzione di un'autorizzazione si impone al sistema di sicurezza di non eseguire il controllo dei chiamanti del codice relativamente all'autorizzazione oggetto dell'asserzione.  
  
> [!CAUTION]
>  Usare con cautela le asserzioni, in quanto possono introdurre vulnerabilità nella sicurezza e compromettere il meccanismo runtime per l'applicazione delle restrizioni di sicurezza.  
  
 Le asserzioni risultano utili nelle situazioni in cui una libreria chiama codice non gestito o effettua una chiamata che richiede un'autorizzazione non direttamente correlata all'uso previsto della libreria. Ad esempio, tutto il codice gestito che chiama codice non gestito deve avere **SecurityPermission** con il **UnmanagedCode** flag specificato. Per impostazione predefinita, al codice che non ha origine nel computer locale, ad esempio quello scaricato dalla rete Intranet locale, non viene concessa questa autorizzazione. Pertanto, affinché il codice scaricato dalla rete Intranet locale possa chiamare una libreria che usa codice non gestito, è necessaria un'asserzione dell'autorizzazione da parte della libreria. Alcune librerie possono inoltre effettuare chiamate invisibili ai chiamanti e che richiedono autorizzazioni speciali.  
  
 Le asserzioni possono anche essere usate nelle situazioni in cui il codice accede a una risorsa in modo completamente invisibile ai chiamanti. Si supponga, ad esempio, che la libreria acquisisca informazioni da un database, ma durante il processa legga anche informazioni dal Registro di sistema del computer. Poiché gli sviluppatori che usano la libreria non hanno accesso all'origine, non hanno modo di sapere che è necessaria **RegistryPermission** per usare il codice. In questo caso, se si stabilisce che non è ragionevole o necessario richiedere che i chiamanti del codice dispongano di un'autorizzazione per accedere al Registro di sistema, è possibile effettuare un'asserzione dell'autorizzazione di lettura del Registro di sistema. In questo caso, è consigliabile che la libreria effettui l'asserzione dell'autorizzazione, che i chiamanti privi **RegistryPermission** possono usare la libreria.  
  
 L'asserzione influisce sul percorso stack solo se l'autorizzazione che ne è oggetto e l'autorizzazione richiesta da un chiamante downstream sono dello stesso tipo e se l'autorizzazione richiesta è un subset dell'autorizzazione oggetto dell'asserzione. Ad esempio, se si effettua un'asserzione **FileIOPermission** viene effettuata per leggere tutti i file presenti nell'unità C e a una richiesta downstream **FileIOPermission** per leggere i file in C:\Temp, l'asserzione può influire sull'analisi dello stack. Tuttavia, se la richiesta era per **FileIOPermission** per scrivere nell'unità C, l'asserzione non avrà effetto.  
  
 Perché sia possibile effettuare asserzioni, è necessario concedere al codice sia l'autorizzazione oggetto dell'asserzione sia <xref:System.Security.Permissions.SecurityPermission>, che rappresenta il diritto di effettuare asserzioni. Benché sia possibile effettuare l'asserzione di un'autorizzazione non concessa al codice, tale operazione non avrebbe alcun significato, poiché il controllo di sicurezza avrebbe esito negativo ancor prima che l'asserzione possa garantirne la riuscita.  
  
 La figura seguente mostra cosa accade quando si usa **Assert**. Si supponga che le affermazioni seguenti siano valide per gli assembly A, B, C, E e F e le due autorizzazioni P1 e P1A:  
  
- P1A rappresenta il diritto di leggere i file TXT presenti nell'unità C.  
  
- P1 rappresenta il diritto di leggere tutti i file presenti nell'unità C.  
  
- P1A e P1 sono entrambi **FileIOPermission** tipi e P1A è un subset di P1.  
  
- Agli assembly E ed F è stata concessa l'autorizzazione P1A.  
  
- All'assembly C è stata concessa l'autorizzazione P1.  
  
- Agli assembly A e B non è stata concessa né l'autorizzazione P1 né l'autorizzazione P1A.  
  
- Il metodo A è incluso nell'assembly A, il metodo B nell'assembly B e così via.  
  
 ![Diagramma che mostra gli assembly del metodo Assert.](./media/using-the-assert-method/assert-method-assemblies.gif)    
  
 In questo scenario, il metodo a chiama B, B chiama C, C chiama E, E chiama F. metodo C effettua un'asserzione dell'autorizzazione per leggere i file nell'unità C (autorizzazione P1) e (metodo) E richiede l'autorizzazione per leggere i file con estensione txt nell'unità C (autorizzazione P1A). Quando viene rilevata la richiesta in F in fase di esecuzione, viene eseguita un'analisi dello stack per controllare le autorizzazioni di tutti i chiamanti di F, a partire E. E dispone dell'autorizzazione P1A, pertanto il percorso stack procede esaminando le autorizzazioni di C, in cui viene individuata l'asserzione di C. Poiché l'autorizzazione richiesta (P1A) è un subset dell'autorizzazione oggetto dell'asserzione (P1), il percorso stack si interrompe e automaticamente il controllo di sicurezza ha esito positivo. Non è importante che agli assembly A e B non sia stata concessa l'autorizzazione P1A. Con l'asserzione di P1, il metodo C garantisce che i chiamanti possano accedere alla risorsa protetta da P1, anche se non è stata loro concessa l'autorizzazione di accesso.  
  
 Se si progetta una libreria di classi e una classe accede a una risorsa protetta, nella maggior parte dei casi è consigliabile effettuare una richiesta di sicurezza che imponga ai chiamanti della classe di disporre dell'autorizzazione appropriata. Se la classe esegue quindi un'operazione per cui si conosce la maggior parte dei chiamanti non disporrà delle autorizzazioni, e se si è disposti ad assumere la responsabilità per consentire ai chiamanti di chiamare il codice, è possibile effettuare un'asserzione dell'autorizzazione chiamando il **Assert** metodo su un oggetto di autorizzazione che rappresenta l'operazione che sta eseguendo il codice. Usando **Assert** in questo modo consente ai chiamanti che normalmente non disporrebbero chiamare il codice. Quando si effettua quindi l'asserzione di un'autorizzazione, è necessario assicurarsi di avere precedentemente eseguito gli opportuni controlli di sicurezza per impedire l'uso improprio del componente.  
  
 Si supponga, ad esempio, che una classe di libreria altamente attendibile disponga di un metodo per l'eliminazione di file. L'accesso al file viene effettuato chiamando una funzione Win32 non gestita. Un chiamante richiama il codice **eliminare** , passando il nome del file da eliminare, c:\test.txt. All'interno di **eliminare** metodo, il codice crea un <xref:System.Security.Permissions.FileIOPermission> oggetto che rappresenta l'accesso in scrittura a c:\test.txt. L'accesso in scrittura è necessario per l'eliminazione di un file. Il codice richiama quindi un controllo di sicurezza imperativo chiamando il **FileIOPermission** dell'oggetto **richiesta** (metodo). Se uno dei chiamanti inclusi nello stack di chiamate non dispone di questa autorizzazione, viene generata un'eccezione <xref:System.Security.SecurityException>. Se non viene generata alcuna eccezione, significa che tutti i chiamanti hanno il diritto di accedere a C:\Test.txt. Poiché si ritiene che la maggior parte dei chiamanti non disporrà dell'autorizzazione per accedere al codice non gestito, il codice crea un <xref:System.Security.Permissions.SecurityPermission> oggetto che rappresenta il diritto di chiamare codice non gestito e chiama l'oggetto **Assert** (metodo). Infine, chiama la funzione Win32 non gestita per eliminare C:\Test.txt e restituisce il controllo al chiamante.  
  
> [!CAUTION]
>  È necessario assicurarsi che il codice non usi asserzioni in situazioni in cui può essere usato da altro codice per accedere a una risorsa protetta dall'autorizzazione oggetto dell'asserzione. Nel codice che scrive in un file il cui nome è specificato dal chiamante come parametro, ad esempio, sarebbe assert non la **FileIOPermission** per scrittura su file, perché il codice sarebbe esposto a uso improprio da terze parti.  
  
 Quando si usa la sintassi di sicurezza imperativa, chiamando il **Assert** metodo su più autorizzazioni nello stesso metodo fa in modo che venga generata un'eccezione di sicurezza. In alternativa, è necessario creare un **PermissionSet** dell'oggetto, chiamarla le singole autorizzazioni si desidera richiamare e quindi chiamare il **Assert** metodo sul **PermissionSet** oggetto. È possibile chiamare il **Assert** metodo più volte quando si usa la sintassi di sicurezza dichiarativa.  
  
 Nell'esempio seguente illustra la sintassi dichiarativa per controlli di sicurezza esegue l'override usando le **Assert** (metodo). Si noti che il **FileIOPermissionAttribute** sintassi accetta due valori: un <xref:System.Security.Permissions.SecurityAction> enumerazione e il percorso del file o della directory a cui viene concesso l'autorizzazione. La chiamata a **Assert** fa sì che le richieste per l'accesso a `C:\Log.txt` abbia esito positivo, anche se i chiamanti non vengono verificati per l'autorizzazione accedere al file.  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
  
      End Sub  
  
     <FileIOPermission(SecurityAction.Assert, All := "C:\Log.txt")> Public Sub   
      MakeLog()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now) '  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {      
      }     
      [FileIOPermission(SecurityAction.Assert, All = @"C:\Log.txt")]  
      public void MakeLog()  
      {     
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}   
```  
  
 I frammenti di codice seguenti illustrano la sintassi imperativa per controlli di sicurezza esegue l'override usando le **Assert** (metodo). In questo esempio, un'istanza di **FileIOPermission** a un oggetto dichiarato. Il costruttore viene passato **FileIOPermissionAccess. AllAccess** per definire il tipo di accesso consentito, seguito da una stringa che descrive il percorso del file. Una volta il **FileIOPermission** oggetto è definito, è sufficiente chiamare relativo **Assert** metodo per eseguire l'override del controllo di sicurezza.  
  
```vb  
Option Explicit  
Option Strict  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
      End Sub 'New  
  
      Public Sub MakeLog()  
         Dim FilePermission As New FileIOPermission(FileIOPermissionAccess.AllAccess, "C:\Log.txt")  
         FilePermission.Assert()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now)  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {      
      }     
      public void MakeLog()  
      {  
         FileIOPermission FilePermission = new FileIOPermission(FileIOPermissionAccess.AllAccess,@"C:\Log.txt");   
         FilePermission.Assert();  
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.SecurityPermission>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.Permissions.SecurityAction>
- [Attributi](../../../docs/standard/attributes/index.md)
- [Sicurezza dall'accesso di codice](../../../docs/framework/misc/code-access-security.md)
