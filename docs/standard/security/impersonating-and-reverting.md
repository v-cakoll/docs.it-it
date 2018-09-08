---
title: Rappresentazione e ripristino
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsIdentity objects, impersonating
- security [.NET Framework], impersonating Windows accounts
- impersonating Windows accounts
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3bc5b4a9bef51ac1591bdeb21651cee624d552b2
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44137447"
---
# <a name="impersonating-and-reverting"></a>Rappresentazione e ripristino
Talvolta può essere necessario ottenere un token di account Windows per rappresentare un account Windows. Può essere necessario, ad esempio, che l'applicazione basata su ASP.NET agisca per conto di più utenti in momenti diversi. L'applicazione potrebbe accettare un token che rappresenta un amministratore da Internet Information Services (IIS), rappresentare tale utente, eseguire un'operazione e ripristinare l'identità precedente. In seguito potrebbe accettare un token da IIS che rappresenta un utente con meno diritti, eseguire un'operazione e di nuovo il ripristino.  
  
 Nelle situazioni in cui l'applicazione deve rappresentare un account Windows che non è stato associato al thread corrente da IIS, è necessario recuperare il token di tale account e usarlo per attivare l'account. A tale scopo, è possibile eseguire queste attività:  
  
1.  Recuperare un token di un account per un particolare utente eseguendo una chiamata al metodo **LogonUser** non gestito. Questo metodo non si trova nella libreria di classi base di .NET Framework, ma nel file **advapi32.dll** non gestito. L'accesso ai metodi nel codice non gestito è un'operazione avanzata che non rientra nell'ambito di questo argomento. Per altre informazioni, vedere [Interoperabilità con codice non gestito](../../../docs/framework/interop/index.md). Per altre informazioni sul metodo **LogonUser** e su **advapi32.dll**, vedere la documentazione di Platform SDK.  
  
2.  Creare una nuova istanza della classe **WindowsIdentity**, passando il token. Il codice seguente illustra questa chiamata, dove `hToken` rappresenta un token di Windows.  
  
    ```csharp  
    WindowsIdentity ImpersonatedIdentity = new WindowsIdentity(hToken);  
    ```  
  
    ```vb  
    Dim ImpersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3.  Iniziare la rappresentazione creando una nuova istanza di <xref:System.Security.Principal.WindowsImpersonationContext> classe e inizializzandola con il <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> metodo della classe inizializzata, come illustrato nel codice seguente.  
  
    ```csharp  
    WindowsImpersonationContext MyImpersonation = ImpersonatedIdentity.Impersonate();  
    ```  
  
    ```vb  
    WindowsImpersonationContext MyImpersonation = ImpersonatedIdentity.Impersonate()  
    ```  
  
4.  Quando si non è più necessario rappresentare, chiamare il <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> metodo per ripristinare la rappresentazione, come illustrato nel codice seguente.  
  
    ```csharp  
    MyImpersonation.Undo();  
    ```  
  
    ```vb  
    MyImpersonation.Undo()  
    ```  
  
 Se il codice attendibile ha già associato un <xref:System.Security.Principal.WindowsPrincipal> dell'oggetto al thread, è possibile chiamare il metodo di istanza **Impersonate**, che non accetta un token di account. Si noti che questo è utile solo quando l'oggetto **WindowsPrincipal** nel thread rappresenta un utente diverso da quello per cui il processo è attualmente in esecuzione. Questa situazione può verificarsi, ad esempio, quando si usa ASP.NET con l'autenticazione di Windows attivata e la rappresentazione disattivata. In questo caso, il processo viene eseguito con un account configurato in Internet Information Services (IIS), mentre l'entità corrente rappresenta l'utente di Windows che sta accedendo alla pagina.  
  
 Si noti che né **Impersonate** né **Annulla** modifiche il **entità** oggetto (<xref:System.Security.Principal.IPrincipal>) associato al contesto chiamata corrente. La rappresentazione e il ripristino modificano invece il token associato al processo del sistema operativo corrente.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Principal.WindowsIdentity>  
- <xref:System.Security.Principal.WindowsImpersonationContext>  
- [Oggetti Principal e Identity](../../../docs/standard/security/principal-and-identity-objects.md)  
- [Interoperabilità con codice non gestito](../../../docs/framework/interop/index.md)
