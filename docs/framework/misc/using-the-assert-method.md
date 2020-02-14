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
ms.openlocfilehash: 2bc46714a508990c5ae31b50e7d19a287da2c5c0
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215830"
---
# <a name="using-the-assert-method"></a>Utilizzo del metodo Assert
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <xref:System.Security.CodeAccessPermission.Assert%2A> è un metodo che può essere chiamato nelle classi di autorizzazione di accesso al codice e nella classe <xref:System.Security.PermissionSet>. È possibile utilizzare **Assert** per abilitare il codice (e i chiamanti downstream) per eseguire azioni che il codice è autorizzato a eseguire, ma i chiamanti potrebbero non disporre delle autorizzazioni necessarie. Un'asserzione di sicurezza modifica il normale processo eseguito dal runtime durante un controllo di sicurezza. Mediante l'asserzione di un'autorizzazione si impone al sistema di sicurezza di non eseguire il controllo dei chiamanti del codice relativamente all'autorizzazione oggetto dell'asserzione.  
  
> [!CAUTION]
> Usare con cautela le asserzioni, in quanto possono introdurre vulnerabilità nella sicurezza e compromettere il meccanismo runtime per l'applicazione delle restrizioni di sicurezza.  
  
 Le asserzioni risultano utili nelle situazioni in cui una libreria chiama codice non gestito o effettua una chiamata che richiede un'autorizzazione non direttamente correlata all'uso previsto della libreria. Ad esempio, tutto il codice gestito che chiama il codice non gestito deve avere **SecurityPermission** con il flag **UnmanagedCode** specificato. Per impostazione predefinita, al codice che non ha origine nel computer locale, ad esempio quello scaricato dalla rete Intranet locale, non viene concessa questa autorizzazione. Pertanto, affinché il codice scaricato dalla rete Intranet locale possa chiamare una libreria che usa codice non gestito, è necessaria un'asserzione dell'autorizzazione da parte della libreria. Alcune librerie possono inoltre effettuare chiamate invisibili ai chiamanti e che richiedono autorizzazioni speciali.  
  
 Le asserzioni possono anche essere usate nelle situazioni in cui il codice accede a una risorsa in modo completamente invisibile ai chiamanti. Si supponga, ad esempio, che la libreria acquisisca informazioni da un database, ma durante il processa legga anche informazioni dal Registro di sistema del computer. Poiché gli sviluppatori che usano la libreria non hanno accesso all'origine, non hanno modo di sapere che il codice richiede **RegistryPermission** per poter usare il codice. In questo caso, se si stabilisce che non è ragionevole o necessario richiedere che i chiamanti del codice dispongano di un'autorizzazione per accedere al Registro di sistema, è possibile effettuare un'asserzione dell'autorizzazione di lettura del Registro di sistema. In questa situazione è opportuno che la libreria affermi l'autorizzazione in modo che i chiamanti senza **RegistryPermission** possano usare la libreria.  
  
 L'asserzione influisce sul percorso stack solo se l'autorizzazione che ne è oggetto e l'autorizzazione richiesta da un chiamante downstream sono dello stesso tipo e se l'autorizzazione richiesta è un subset dell'autorizzazione oggetto dell'asserzione. Se, ad esempio, si dichiara **FileIOPermission** per leggere tutti i file nell'unità C e viene eseguita una richiesta downstream per la lettura dei file in C:\Temp da parte di **FileIOPermission** , l'asserzione potrebbe influire sul percorso stack. Tuttavia, se la richiesta era relativa a **FileIOPermission** per la scrittura nell'unità C, l'asserzione non avrebbe alcun effetto.  
  
 Perché sia possibile effettuare asserzioni, è necessario concedere al codice sia l'autorizzazione oggetto dell'asserzione sia <xref:System.Security.Permissions.SecurityPermission>, che rappresenta il diritto di effettuare asserzioni. Benché sia possibile effettuare l'asserzione di un'autorizzazione non concessa al codice, tale operazione non avrebbe alcun significato, poiché il controllo di sicurezza avrebbe esito negativo ancor prima che l'asserzione possa garantirne la riuscita.  
  
 Nella figura seguente viene illustrato cosa accade quando si utilizza **Assert**. Si supponga che le affermazioni seguenti siano valide per gli assembly A, B, C, E e F e le due autorizzazioni P1 e P1A:  
  
- P1A rappresenta il diritto di leggere i file TXT presenti nell'unità C.  
  
- P1 rappresenta il diritto di leggere tutti i file presenti nell'unità C.  
  
- P1A e P1 sono entrambi tipi **FileIOPermission** e P1A è un subset di P1.  
  
- Agli assembly E ed F è stata concessa l'autorizzazione P1A.  
  
- All'assembly C è stata concessa l'autorizzazione P1.  
  
- Agli assembly A e B non è stata concessa né l'autorizzazione P1 né l'autorizzazione P1A.  
  
- Il metodo A è incluso nell'assembly A, il metodo B nell'assembly B e così via.  
  
 ![Diagramma che Mostra gli assembly del metodo Assert.](./media/using-the-assert-method/assert-method-assemblies.gif)    
  
 In questo scenario, il metodo A chiama B, B chiama C, C chiama E e e chiama F. il metodo C asserisce l'autorizzazione per leggere i file nell'unità C (autorizzazione P1) e il metodo e richiede l'autorizzazione per leggere i file con estensione txt nell'unità C (autorizzazione P1A). Quando viene rilevata la richiesta in F in fase di esecuzione, viene eseguito un percorso stack per verificare le autorizzazioni di tutti i chiamanti di F, a partire da E. a è stata concessa l'autorizzazione P1A, quindi il percorso stack procede per esaminare le autorizzazioni di C, dove viene individuata l'asserzione di C. Poiché l'autorizzazione richiesta (P1A) è un subset dell'autorizzazione oggetto dell'asserzione (P1), il percorso stack si interrompe e automaticamente il controllo di sicurezza ha esito positivo. Non è importante che agli assembly A e B non sia stata concessa l'autorizzazione P1A. Con l'asserzione di P1, il metodo C garantisce che i chiamanti possano accedere alla risorsa protetta da P1, anche se non è stata loro concessa l'autorizzazione di accesso.  
  
 Se si progetta una libreria di classi e una classe accede a una risorsa protetta, nella maggior parte dei casi è consigliabile effettuare una richiesta di sicurezza che imponga ai chiamanti della classe di disporre dell'autorizzazione appropriata. Se la classe esegue quindi un'operazione per la quale si conosce la maggior parte dei chiamanti non avrà l'autorizzazione e se si è disposti ad assumere la responsabilità di consentire a questi chiamanti di chiamare il codice, è possibile dichiarare l'autorizzazione chiamando il metodo **Assert** su un oggetto autorizzazione che rappresenta l'operazione eseguita dal codice. L'uso di **Assert** in questo modo consente ai chiamanti che in genere non possono eseguire chiamate al codice. Quando si effettua quindi l'asserzione di un'autorizzazione, è necessario assicurarsi di avere precedentemente eseguito gli opportuni controlli di sicurezza per impedire l'uso improprio del componente.  
  
 Si supponga, ad esempio, che una classe di libreria altamente attendibile disponga di un metodo per l'eliminazione di file. L'accesso al file viene effettuato chiamando una funzione Win32 non gestita. Un chiamante richiama il metodo **Delete** del codice, passando il nome del file da eliminare, C:\test.txt. All'interno del metodo **Delete** , il codice crea un oggetto <xref:System.Security.Permissions.FileIOPermission> che rappresenta l'accesso in scrittura a C:\test.txt. Per eliminare un file, è necessario l'accesso in scrittura. Il codice richiama quindi un controllo di sicurezza imperativo chiamando il metodo **Demand** dell'oggetto **FileIOPermission** . Se uno dei chiamanti inclusi nello stack di chiamate non dispone di questa autorizzazione, viene generata un'eccezione <xref:System.Security.SecurityException>. Se non viene generata alcuna eccezione, significa che tutti i chiamanti hanno il diritto di accedere a C:\Test.txt. Poiché si ritiene che la maggior parte dei chiamanti non sarà autorizzato ad accedere al codice non gestito, il codice crea quindi un oggetto <xref:System.Security.Permissions.SecurityPermission> che rappresenta il diritto di chiamare codice non gestito e chiama il metodo **Assert** dell'oggetto. Infine, chiama la funzione Win32 non gestita per eliminare C:\Test.txt e restituisce il controllo al chiamante.  
  
> [!CAUTION]
> È necessario assicurarsi che il codice non usi asserzioni in situazioni in cui può essere usato da altro codice per accedere a una risorsa protetta dall'autorizzazione oggetto dell'asserzione. Ad esempio, nel codice che scrive in un file il cui nome è specificato dal chiamante come parametro, non è necessario dichiarare l'oggetto **FileIOPermission** per la scrittura nei file perché il codice potrebbe essere utilizzato in modo improprio da terze parti.  
  
 Quando si usa la sintassi di sicurezza imperativa, la chiamata al metodo **Assert** su più autorizzazioni nello stesso metodo comporta la generazione di un'eccezione di sicurezza. È invece consigliabile creare un oggetto **PermissionSet** , passargli le singole autorizzazioni da richiamare, quindi chiamare il metodo **Assert** sull'oggetto **PermissionSet** . È possibile chiamare il metodo **Assert** più di una volta quando si usa la sintassi di sicurezza dichiarativa.  
  
 Nell'esempio seguente viene illustrata la sintassi dichiarativa per l'override dei controlli di sicurezza tramite il metodo **Assert** . Si noti che la sintassi **FileIOPermissionAttribute** accetta due valori: un'enumerazione <xref:System.Security.Permissions.SecurityAction> e il percorso del file o della directory a cui deve essere concessa l'autorizzazione. La chiamata a **Assert** causa la riuscita della richiesta di accesso `C:\Log.txt`, anche se non viene verificata l'autorizzazione per l'accesso al file da parte dei chiamanti.  
  
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
  
 I frammenti di codice seguenti mostrano la sintassi imperativa per l'override dei controlli di sicurezza tramite il metodo **Assert** . In questo esempio viene dichiarata un'istanza dell'oggetto **FileIOPermission** . Al costruttore viene passato **FileIOPermissionAccess. AllAccess** per definire il tipo di accesso consentito, seguito da una stringa che descrive la posizione del file. Una volta definito l'oggetto **FileIOPermission** , è sufficiente chiamare il relativo metodo **Assert** per eseguire l'override del controllo di sicurezza.  
  
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
- [Attributes (Attributi)](../../standard/attributes/index.md)
- [Sicurezza dall'accesso di codice](code-access-security.md)
