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
ms.openlocfilehash: 14b01ec3ac800abd795e87b641a442df100f102b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706019"
---
# <a name="impersonating-and-reverting"></a>Rappresentazione e ripristino
Talvolta può essere necessario ottenere un token di account Windows per rappresentare un account Windows. Può essere necessario, ad esempio, che l'applicazione basata su ASP.NET agisca per conto di più utenti in momenti diversi. L'applicazione potrebbe accettare un token che rappresenta un amministratore da Internet Information Services (IIS), rappresentare tale utente, eseguire un'operazione e ripristinare l'identità precedente. In seguito potrebbe accettare un token da IIS che rappresenta un utente con meno diritti, eseguire un'operazione e di nuovo il ripristino.  
  
 Nelle situazioni in cui l'applicazione deve rappresentare un account Windows che non è stato associato al thread corrente da IIS, è necessario recuperare il token di tale account e usarlo per attivare l'account. A tale scopo, è possibile eseguire queste attività:  
  
1. Recuperare un token di un account per un particolare utente eseguendo una chiamata al metodo **LogonUser** non gestito. Questo metodo non si trova nella libreria di classi base di .NET Framework, ma nel file **advapi32.dll** non gestito. L'accesso ai metodi nel codice non gestito è un'operazione avanzata che non rientra nell'ambito di questo argomento. Per altre informazioni, vedere [Interoperabilità con codice non gestito](../../../docs/framework/interop/index.md). Per altre informazioni sul metodo **LogonUser** e su **advapi32.dll**, vedere la documentazione di Platform SDK.  
  
2. Creare una nuova istanza della classe **WindowsIdentity**, passando il token. Il codice seguente illustra questa chiamata, dove `hToken` rappresenta un token di Windows.  
  
    ```csharp  
    WindowsIdentity impersonatedIdentity = new WindowsIdentity(hToken);  
    ```  
  
    ```vb  
    Dim impersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3. Iniziare la rappresentazione creando una nuova istanza della classe <xref:System.Security.Principal.WindowsImpersonationContext> e inizializzandola con il metodo <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> della classe inizializzata, come mostrato nel codice seguente.  
  
    ```csharp  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate();  
    ```  
  
    ```vb  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate()  
    ```  
  
4. Quando la rappresentazione non è più necessaria, chiamare il metodo <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> per ripristinare la rappresentazione, come mostrato nel codice seguente.  
  
    ```csharp  
    myImpersonation.Undo();  
    ```  
  
    ```vb  
    myImpersonation.Undo()  
    ```  
  
 Se il codice attendibile ha già associato un oggetto <xref:System.Security.Principal.WindowsPrincipal> al thread, è possibile chiamare il metodo di istanza **Impersonate**, che non accetta un token di account. Si noti che questo è utile solo quando l'oggetto **WindowsPrincipal** nel thread rappresenta un utente diverso da quello per cui il processo è attualmente in esecuzione. Questa situazione può verificarsi, ad esempio, quando si usa ASP.NET con l'autenticazione di Windows attivata e la rappresentazione disattivata. In questo caso, il processo viene eseguito con un account configurato in Internet Information Services (IIS), mentre l'entità corrente rappresenta l'utente di Windows che sta accedendo alla pagina.  
  
 Si noti che né **Impersonate** né **Undo** modificano l'oggetto **Principal** (<xref:System.Security.Principal.IPrincipal>) associato al contesto di chiamata corrente. La rappresentazione e il ripristino modificano invece il token associato al processo del sistema operativo corrente.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.Security.Principal.WindowsImpersonationContext>
- [Oggetti Principal e Identity](../../../docs/standard/security/principal-and-identity-objects.md)
- [Interoperabilità con codice non gestito](../../../docs/framework/interop/index.md)
