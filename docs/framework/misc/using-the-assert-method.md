---
title: Utilizzo del metodo Assert
description: Vedere come è possibile usare il metodo Assert per abilitare il codice (e il codice dei chiamanti downstream) per eseguire le operazioni del codice, ma non i relativi chiamanti.
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
ms.openlocfilehash: 096e0375a94c92a835cccb4d1b3297783b4120e9
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309807"
---
# <a name="using-the-assert-method"></a><span data-ttu-id="cfca1-103">Utilizzo del metodo Assert</span><span class="sxs-lookup"><span data-stu-id="cfca1-103">Using the Assert Method</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="cfca1-104"><xref:System.Security.CodeAccessPermission.Assert%2A> è un metodo che può essere chiamato nelle classi di autorizzazione di accesso al codice e nella classe <xref:System.Security.PermissionSet>.</span><span class="sxs-lookup"><span data-stu-id="cfca1-104"><xref:System.Security.CodeAccessPermission.Assert%2A> is a method that can be called on code access permission classes and on the <xref:System.Security.PermissionSet> class.</span></span> <span data-ttu-id="cfca1-105">È possibile utilizzare **Assert** per abilitare il codice (e i chiamanti downstream) per eseguire azioni che il codice è autorizzato a eseguire, ma i chiamanti potrebbero non disporre delle autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="cfca1-105">You can use **Assert** to enable your code (and downstream callers) to perform actions that your code has permission to do but its callers might not have permission to do.</span></span> <span data-ttu-id="cfca1-106">Un'asserzione di sicurezza modifica il normale processo eseguito dal runtime durante un controllo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cfca1-106">A security assertion changes the normal process that the runtime performs during a security check.</span></span> <span data-ttu-id="cfca1-107">Mediante l'asserzione di un'autorizzazione si impone al sistema di sicurezza di non eseguire il controllo dei chiamanti del codice relativamente all'autorizzazione oggetto dell'asserzione.</span><span class="sxs-lookup"><span data-stu-id="cfca1-107">When you assert a permission, it tells the security system not to check the callers of your code for the asserted permission.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="cfca1-108">Usare con cautela le asserzioni, in quanto possono introdurre vulnerabilità nella sicurezza e compromettere il meccanismo runtime per l'applicazione delle restrizioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cfca1-108">Use assertions carefully because they can open security holes and undermine the runtime's mechanism for enforcing security restrictions.</span></span>  
  
 <span data-ttu-id="cfca1-109">Le asserzioni risultano utili nelle situazioni in cui una libreria chiama codice non gestito o effettua una chiamata che richiede un'autorizzazione non direttamente correlata all'uso previsto della libreria.</span><span class="sxs-lookup"><span data-stu-id="cfca1-109">Assertions are useful in situations in which a library calls into unmanaged code or makes a call that requires a permission that is not obviously related to the library's intended use.</span></span> <span data-ttu-id="cfca1-110">Ad esempio, tutto il codice gestito che chiama il codice non gestito deve avere **SecurityPermission** con il flag **UnmanagedCode** specificato.</span><span class="sxs-lookup"><span data-stu-id="cfca1-110">For example, all managed code that calls into unmanaged code must have **SecurityPermission** with the **UnmanagedCode** flag specified.</span></span> <span data-ttu-id="cfca1-111">Per impostazione predefinita, al codice che non ha origine nel computer locale, ad esempio quello scaricato dalla rete Intranet locale, non viene concessa questa autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="cfca1-111">Code that does not originate from the local computer, such as code that is downloaded from the local intranet, will not be granted this permission by default.</span></span> <span data-ttu-id="cfca1-112">Pertanto, affinché il codice scaricato dalla rete Intranet locale possa chiamare una libreria che usa codice non gestito, è necessaria un'asserzione dell'autorizzazione da parte della libreria.</span><span class="sxs-lookup"><span data-stu-id="cfca1-112">Therefore, in order for code that is downloaded from the local intranet to be able to call a library that uses unmanaged code, it must have the permission asserted by the library.</span></span> <span data-ttu-id="cfca1-113">Alcune librerie possono inoltre effettuare chiamate invisibili ai chiamanti e che richiedono autorizzazioni speciali.</span><span class="sxs-lookup"><span data-stu-id="cfca1-113">Additionally, some libraries might make calls that are unseen to callers and require special permissions.</span></span>  
  
 <span data-ttu-id="cfca1-114">Le asserzioni possono anche essere usate nelle situazioni in cui il codice accede a una risorsa in modo completamente invisibile ai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="cfca1-114">You can also use assertions in situations in which your code accesses a resource in a way that is completely hidden from callers.</span></span> <span data-ttu-id="cfca1-115">Si supponga, ad esempio, che la libreria acquisisca informazioni da un database, ma durante il processa legga anche informazioni dal Registro di sistema del computer.</span><span class="sxs-lookup"><span data-stu-id="cfca1-115">For example, suppose your library acquires information from a database, but in the process also reads information from the computer registry.</span></span> <span data-ttu-id="cfca1-116">Poiché gli sviluppatori che usano la libreria non hanno accesso all'origine, non hanno modo di sapere che il codice richiede **RegistryPermission** per poter usare il codice.</span><span class="sxs-lookup"><span data-stu-id="cfca1-116">Because developers using your library do not have access to your source, they have no way of knowing that their code requires **RegistryPermission** in order to use your code.</span></span> <span data-ttu-id="cfca1-117">In questo caso, se si stabilisce che non è ragionevole o necessario richiedere che i chiamanti del codice dispongano di un'autorizzazione per accedere al Registro di sistema, è possibile effettuare un'asserzione dell'autorizzazione di lettura del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="cfca1-117">In this case, if you decide that it is not reasonable or necessary to require that callers of your code have permission to access the registry, you can assert permission for reading the registry.</span></span> <span data-ttu-id="cfca1-118">In questa situazione è opportuno che la libreria affermi l'autorizzazione in modo che i chiamanti senza **RegistryPermission** possano usare la libreria.</span><span class="sxs-lookup"><span data-stu-id="cfca1-118">In this situation, it is appropriate for the library to assert the permission so that callers without **RegistryPermission** can use the library.</span></span>  
  
 <span data-ttu-id="cfca1-119">L'asserzione influisce sul percorso stack solo se l'autorizzazione che ne è oggetto e l'autorizzazione richiesta da un chiamante downstream sono dello stesso tipo e se l'autorizzazione richiesta è un subset dell'autorizzazione oggetto dell'asserzione.</span><span class="sxs-lookup"><span data-stu-id="cfca1-119">The assertion affects the stack walk only if the asserted permission and a permission demanded by a downstream caller are of the same type and if the demanded permission is a subset of the asserted permission.</span></span> <span data-ttu-id="cfca1-120">Se, ad esempio, si dichiara **FileIOPermission** per leggere tutti i file nell'unità C e viene eseguita una richiesta downstream per la lettura dei file in C:\Temp da parte di **FileIOPermission** , l'asserzione potrebbe influire sul percorso stack. Tuttavia, se la richiesta era relativa a **FileIOPermission** per la scrittura nell'unità C, l'asserzione non avrebbe alcun effetto.</span><span class="sxs-lookup"><span data-stu-id="cfca1-120">For example, if you assert **FileIOPermission** to read all files on the C drive, and a downstream demand is made for **FileIOPermission** to read files in C:\Temp, the assertion could affect the stack walk; however, if the demand was for **FileIOPermission** to write to the C drive, the assertion would have no effect.</span></span>  
  
 <span data-ttu-id="cfca1-121">Perché sia possibile effettuare asserzioni, è necessario concedere al codice sia l'autorizzazione oggetto dell'asserzione sia <xref:System.Security.Permissions.SecurityPermission>, che rappresenta il diritto di effettuare asserzioni.</span><span class="sxs-lookup"><span data-stu-id="cfca1-121">To perform assertions, your code must be granted both the permission you are asserting and the <xref:System.Security.Permissions.SecurityPermission> that represents the right to make assertions.</span></span> <span data-ttu-id="cfca1-122">Benché sia possibile effettuare l'asserzione di un'autorizzazione non concessa al codice, tale operazione non avrebbe alcun significato, poiché il controllo di sicurezza avrebbe esito negativo ancor prima che l'asserzione possa garantirne la riuscita.</span><span class="sxs-lookup"><span data-stu-id="cfca1-122">Although you could assert a permission that your code has not been granted, the assertion would be pointless because the security check would fail before the assertion could cause it to succeed.</span></span>  
  
 <span data-ttu-id="cfca1-123">Nella figura seguente viene illustrato cosa accade quando si utilizza **Assert**.</span><span class="sxs-lookup"><span data-stu-id="cfca1-123">The following illustration shows what happens when you use **Assert**.</span></span> <span data-ttu-id="cfca1-124">Si supponga che le affermazioni seguenti siano valide per gli assembly A, B, C, E e F e le due autorizzazioni P1 e P1A:</span><span class="sxs-lookup"><span data-stu-id="cfca1-124">Assume that the following statements are true about assemblies A, B, C, E, and F, and two permissions, P1 and P1A:</span></span>  
  
- <span data-ttu-id="cfca1-125">P1A rappresenta il diritto di leggere i file TXT presenti nell'unità C.</span><span class="sxs-lookup"><span data-stu-id="cfca1-125">P1A represents the right to read .txt files on the C drive.</span></span>  
  
- <span data-ttu-id="cfca1-126">P1 rappresenta il diritto di leggere tutti i file presenti nell'unità C.</span><span class="sxs-lookup"><span data-stu-id="cfca1-126">P1 represents the right to read all files on the C drive.</span></span>  
  
- <span data-ttu-id="cfca1-127">P1A e P1 sono entrambi tipi **FileIOPermission** e P1A è un subset di P1.</span><span class="sxs-lookup"><span data-stu-id="cfca1-127">P1A and P1 are both **FileIOPermission** types, and P1A is a subset of P1.</span></span>  
  
- <span data-ttu-id="cfca1-128">Agli assembly E ed F è stata concessa l'autorizzazione P1A.</span><span class="sxs-lookup"><span data-stu-id="cfca1-128">Assemblies E and F have been granted P1A permission.</span></span>  
  
- <span data-ttu-id="cfca1-129">All'assembly C è stata concessa l'autorizzazione P1.</span><span class="sxs-lookup"><span data-stu-id="cfca1-129">Assembly C has been granted P1 permission.</span></span>  
  
- <span data-ttu-id="cfca1-130">Agli assembly A e B non è stata concessa né l'autorizzazione P1 né l'autorizzazione P1A.</span><span class="sxs-lookup"><span data-stu-id="cfca1-130">Assemblies A and B have been granted neither P1 nor P1A permissions.</span></span>  
  
- <span data-ttu-id="cfca1-131">Il metodo A è incluso nell'assembly A, il metodo B nell'assembly B e così via.</span><span class="sxs-lookup"><span data-stu-id="cfca1-131">Method A is contained in assembly A, method B is contained in assembly B, and so on.</span></span>  
  
 ![Diagramma che Mostra gli assembly del metodo Assert.](./media/using-the-assert-method/assert-method-assemblies.gif)
  
 <span data-ttu-id="cfca1-133">In questo scenario, il metodo A chiama B, B chiama C, C chiama E e e chiama F. il metodo C asserisce l'autorizzazione per leggere i file nell'unità C (autorizzazione P1) e il metodo e richiede l'autorizzazione per leggere i file con estensione txt nell'unità C (autorizzazione P1A).</span><span class="sxs-lookup"><span data-stu-id="cfca1-133">In this scenario, method A calls B, B calls C, C calls E, and E calls F. Method C asserts permission to read files on the C drive (permission P1), and method E demands permission to read .txt files on the C drive (permission P1A).</span></span> <span data-ttu-id="cfca1-134">Quando viene rilevata la richiesta in F in fase di esecuzione, viene eseguito un percorso stack per verificare le autorizzazioni di tutti i chiamanti di F, a partire da E. a è stata concessa l'autorizzazione P1A, quindi il percorso stack procede per esaminare le autorizzazioni di C, dove viene individuata l'asserzione di C.</span><span class="sxs-lookup"><span data-stu-id="cfca1-134">When the demand in F is encountered at run time, a stack walk is performed to check the permissions of all callers of F, starting with E. E has been granted P1A permission, so the stack walk proceeds to examine the permissions of C, where C's assertion is discovered.</span></span> <span data-ttu-id="cfca1-135">Poiché l'autorizzazione richiesta (P1A) è un subset dell'autorizzazione oggetto dell'asserzione (P1), il percorso stack si interrompe e automaticamente il controllo di sicurezza ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cfca1-135">Because the demanded permission (P1A) is a subset of the asserted permission (P1), the stack walk stops and the security check automatically succeeds.</span></span> <span data-ttu-id="cfca1-136">Non è importante che agli assembly A e B non sia stata concessa l'autorizzazione P1A.</span><span class="sxs-lookup"><span data-stu-id="cfca1-136">It does not matter that assemblies A and B have not been granted permission P1A.</span></span> <span data-ttu-id="cfca1-137">Con l'asserzione di P1, il metodo C garantisce che i chiamanti possano accedere alla risorsa protetta da P1, anche se non è stata loro concessa l'autorizzazione di accesso.</span><span class="sxs-lookup"><span data-stu-id="cfca1-137">By asserting P1, method C ensures that its callers can access the resource protected by P1, even if the callers have not been granted permission to access that resource.</span></span>  
  
 <span data-ttu-id="cfca1-138">Se si progetta una libreria di classi e una classe accede a una risorsa protetta, nella maggior parte dei casi è consigliabile effettuare una richiesta di sicurezza che imponga ai chiamanti della classe di disporre dell'autorizzazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="cfca1-138">If you design a class library and a class accesses a protected resource, you should, in most cases, make a security demand requiring that the callers of the class have the appropriate permission.</span></span> <span data-ttu-id="cfca1-139">Se la classe esegue quindi un'operazione per la quale si conosce la maggior parte dei chiamanti non avrà l'autorizzazione e se si è disposti ad assumere la responsabilità di consentire a questi chiamanti di chiamare il codice, è possibile dichiarare l'autorizzazione chiamando il metodo **Assert** su un oggetto autorizzazione che rappresenta l'operazione eseguita dal codice.</span><span class="sxs-lookup"><span data-stu-id="cfca1-139">If the class then performs an operation for which you know most of its callers will not have permission, and if you are willing to take the responsibility for letting these callers call your code, you can assert the permission by calling the **Assert** method on a permission object that represents the operation the code is performing.</span></span> <span data-ttu-id="cfca1-140">L'uso di **Assert** in questo modo consente ai chiamanti che in genere non possono eseguire chiamate al codice.</span><span class="sxs-lookup"><span data-stu-id="cfca1-140">Using **Assert** in this way lets callers that normally could not do so call your code.</span></span> <span data-ttu-id="cfca1-141">Quando si effettua quindi l'asserzione di un'autorizzazione, è necessario assicurarsi di avere precedentemente eseguito gli opportuni controlli di sicurezza per impedire l'uso improprio del componente.</span><span class="sxs-lookup"><span data-stu-id="cfca1-141">Therefore, if you assert a permission, you should be sure to perform appropriate security checks beforehand to prevent your component from being misused.</span></span>  
  
 <span data-ttu-id="cfca1-142">Si supponga, ad esempio, che una classe di libreria altamente attendibile disponga di un metodo per l'eliminazione di file.</span><span class="sxs-lookup"><span data-stu-id="cfca1-142">For example, suppose your highly trusted library class has a method that deletes files.</span></span> <span data-ttu-id="cfca1-143">L'accesso al file viene effettuato chiamando una funzione Win32 non gestita.</span><span class="sxs-lookup"><span data-stu-id="cfca1-143">It accesses the file by calling an unmanaged Win32 function.</span></span> <span data-ttu-id="cfca1-144">Un chiamante richiama il metodo **Delete** del codice, passando il nome del file da eliminare C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="cfca1-144">A caller invokes your code's **Delete** method, passing in the name of the file to be deleted, C:\Test.txt.</span></span> <span data-ttu-id="cfca1-145">All'interno del metodo **Delete** , il codice crea un <xref:System.Security.Permissions.FileIOPermission> oggetto che rappresenta l'accesso in scrittura a C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="cfca1-145">Within the **Delete** method, your code creates a <xref:System.Security.Permissions.FileIOPermission> object representing write access to C:\Test.txt.</span></span> <span data-ttu-id="cfca1-146">Per eliminare un file, è necessario l'accesso in scrittura. Il codice richiama quindi un controllo di sicurezza imperativo chiamando il metodo **Demand** dell'oggetto **FileIOPermission** .</span><span class="sxs-lookup"><span data-stu-id="cfca1-146">(Write access is required to delete a file.) Your code then invokes an imperative security check by calling the **FileIOPermission** object's **Demand** method.</span></span> <span data-ttu-id="cfca1-147">Se uno dei chiamanti inclusi nello stack di chiamate non dispone di questa autorizzazione, viene generata un'eccezione <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="cfca1-147">If one of the callers in the call stack does not have this permission, a <xref:System.Security.SecurityException> is thrown.</span></span> <span data-ttu-id="cfca1-148">Se non viene generata alcuna eccezione, significa che tutti i chiamanti hanno il diritto di accedere a C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="cfca1-148">If no exception is thrown, you know that all callers have the right to access C:\Test.txt.</span></span> <span data-ttu-id="cfca1-149">Poiché si ritiene che la maggior parte dei chiamanti non sarà autorizzato ad accedere al codice non gestito, il codice crea quindi un <xref:System.Security.Permissions.SecurityPermission> oggetto che rappresenta il diritto di chiamare codice non gestito e chiama il metodo **Assert** dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="cfca1-149">Because you believe that most of your callers will not have permission to access unmanaged code, your code then creates a <xref:System.Security.Permissions.SecurityPermission> object that represents the right to call unmanaged code and calls the object's **Assert** method.</span></span> <span data-ttu-id="cfca1-150">Infine, chiama la funzione Win32 non gestita per eliminare C:\Test.txt e restituisce il controllo al chiamante.</span><span class="sxs-lookup"><span data-stu-id="cfca1-150">Finally, it calls the unmanaged Win32 function to delete C:\Text.txt and returns control to the caller.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="cfca1-151">È necessario assicurarsi che il codice non usi asserzioni in situazioni in cui può essere usato da altro codice per accedere a una risorsa protetta dall'autorizzazione oggetto dell'asserzione.</span><span class="sxs-lookup"><span data-stu-id="cfca1-151">You must be sure that your code does not use assertions in situations where your code can be used by other code to access a resource that is protected by the permission you are asserting.</span></span> <span data-ttu-id="cfca1-152">Ad esempio, nel codice che scrive in un file il cui nome è specificato dal chiamante come parametro, non è necessario dichiarare l'oggetto **FileIOPermission** per la scrittura nei file perché il codice potrebbe essere utilizzato in modo improprio da terze parti.</span><span class="sxs-lookup"><span data-stu-id="cfca1-152">For example, in code that writes to a file whose name is specified by the caller as a parameter, you would not assert the **FileIOPermission** for writing to files because your code would be open to misuse by a third party.</span></span>  
  
 <span data-ttu-id="cfca1-153">Quando si usa la sintassi di sicurezza imperativa, la chiamata al metodo **Assert** su più autorizzazioni nello stesso metodo comporta la generazione di un'eccezione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cfca1-153">When you use the imperative security syntax, calling the **Assert** method on multiple permissions in the same method causes a security exception to be thrown.</span></span> <span data-ttu-id="cfca1-154">È invece consigliabile creare un oggetto **PermissionSet** , passargli le singole autorizzazioni da richiamare, quindi chiamare il metodo **Assert** sull'oggetto **PermissionSet** .</span><span class="sxs-lookup"><span data-stu-id="cfca1-154">Instead, you should create a **PermissionSet** object, pass it the individual permissions you want to invoke, and then call the **Assert** method on the **PermissionSet** object.</span></span> <span data-ttu-id="cfca1-155">È possibile chiamare il metodo **Assert** più di una volta quando si usa la sintassi di sicurezza dichiarativa.</span><span class="sxs-lookup"><span data-stu-id="cfca1-155">You can call the **Assert** method more than once when you use the declarative security syntax.</span></span>  
  
 <span data-ttu-id="cfca1-156">Nell'esempio seguente viene illustrata la sintassi dichiarativa per l'override dei controlli di sicurezza tramite il metodo **Assert** .</span><span class="sxs-lookup"><span data-stu-id="cfca1-156">The following example shows declarative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="cfca1-157">Si noti che la sintassi **FileIOPermissionAttribute** accetta due valori: un' <xref:System.Security.Permissions.SecurityAction> enumerazione e il percorso del file o della directory a cui deve essere concessa l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="cfca1-157">Notice that the **FileIOPermissionAttribute** syntax takes two values: a <xref:System.Security.Permissions.SecurityAction> enumeration and the location of the file or directory to which permission is to be granted.</span></span> <span data-ttu-id="cfca1-158">La chiamata a **Assert** causa la riuscita della richiesta di accesso a `C:\Log.txt` , anche se non viene verificata l'autorizzazione di accesso al file da parte dei chiamanti.</span><span class="sxs-lookup"><span data-stu-id="cfca1-158">The call to **Assert** causes demands for access to `C:\Log.txt` to succeed, even though callers are not checked for permission to access the file.</span></span>  
  
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
  
 <span data-ttu-id="cfca1-159">I frammenti di codice seguenti mostrano la sintassi imperativa per l'override dei controlli di sicurezza tramite il metodo **Assert** .</span><span class="sxs-lookup"><span data-stu-id="cfca1-159">The following code fragments show imperative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="cfca1-160">In questo esempio viene dichiarata un'istanza dell'oggetto **FileIOPermission** .</span><span class="sxs-lookup"><span data-stu-id="cfca1-160">In this example, an instance of the **FileIOPermission** object is declared.</span></span> <span data-ttu-id="cfca1-161">Al costruttore viene passato **FileIOPermissionAccess. AllAccess** per definire il tipo di accesso consentito, seguito da una stringa che descrive la posizione del file.</span><span class="sxs-lookup"><span data-stu-id="cfca1-161">Its constructor is passed **FileIOPermissionAccess.AllAccess** to define the type of access allowed, followed by a string describing the file's location.</span></span> <span data-ttu-id="cfca1-162">Una volta definito l'oggetto **FileIOPermission** , è sufficiente chiamare il relativo metodo **Assert** per eseguire l'override del controllo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cfca1-162">Once the **FileIOPermission** object is defined, you only need to call its **Assert** method to override the security check.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cfca1-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfca1-163">See also</span></span>

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.SecurityPermission>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.Permissions.SecurityAction>
- [<span data-ttu-id="cfca1-164">Attributes (Attributi)</span><span class="sxs-lookup"><span data-stu-id="cfca1-164">Attributes</span></span>](../../standard/attributes/index.md)
- [<span data-ttu-id="cfca1-165">Sicurezza dall'accesso di codice</span><span class="sxs-lookup"><span data-stu-id="cfca1-165">Code Access Security</span></span>](code-access-security.md)
