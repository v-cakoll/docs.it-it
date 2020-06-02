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
ms.openlocfilehash: dbfd71830ace1eb8af9f55f06c9ce35c32d592bb
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288017"
---
# <a name="impersonating-and-reverting"></a><span data-ttu-id="e40f3-102">Rappresentazione e ripristino</span><span class="sxs-lookup"><span data-stu-id="e40f3-102">Impersonating and Reverting</span></span>
<span data-ttu-id="e40f3-103">Talvolta può essere necessario ottenere un token di account Windows per rappresentare un account Windows.</span><span class="sxs-lookup"><span data-stu-id="e40f3-103">Sometimes you might need to obtain a Windows account token to impersonate a Windows account.</span></span> <span data-ttu-id="e40f3-104">Può essere necessario, ad esempio, che l'applicazione basata su ASP.NET agisca per conto di più utenti in momenti diversi.</span><span class="sxs-lookup"><span data-stu-id="e40f3-104">For example, your ASP.NET-based application might have to act on behalf of several users at different times.</span></span> <span data-ttu-id="e40f3-105">L'applicazione potrebbe accettare un token che rappresenta un amministratore da Internet Information Services (IIS), rappresentare tale utente, eseguire un'operazione e ripristinare l'identità precedente.</span><span class="sxs-lookup"><span data-stu-id="e40f3-105">Your application might accept a token that represents an administrator from Internet Information Services (IIS), impersonate that user, perform an operation, and revert to the previous identity.</span></span> <span data-ttu-id="e40f3-106">In seguito potrebbe accettare un token da IIS che rappresenta un utente con meno diritti, eseguire un'operazione e di nuovo il ripristino.</span><span class="sxs-lookup"><span data-stu-id="e40f3-106">Next, it might accept a token from IIS that represents a user with fewer rights, perform some operation, and revert again.</span></span>  
  
 <span data-ttu-id="e40f3-107">Nelle situazioni in cui l'applicazione deve rappresentare un account Windows che non è stato associato al thread corrente da IIS, è necessario recuperare il token di tale account e usarlo per attivare l'account.</span><span class="sxs-lookup"><span data-stu-id="e40f3-107">In situations where your application must impersonate a Windows account that has not been attached to the current thread by IIS, you must retrieve that account's token and use it to activate the account.</span></span> <span data-ttu-id="e40f3-108">A tale scopo, è possibile eseguire queste attività:</span><span class="sxs-lookup"><span data-stu-id="e40f3-108">You can do this by performing the following tasks:</span></span>  
  
1. <span data-ttu-id="e40f3-109">Recuperare un token di un account per un particolare utente eseguendo una chiamata al metodo **LogonUser** non gestito.</span><span class="sxs-lookup"><span data-stu-id="e40f3-109">Retrieve an account token for a particular user by making a call to the unmanaged **LogonUser** method.</span></span> <span data-ttu-id="e40f3-110">Questo metodo non si trova nella libreria di classi base di .NET Framework, ma nel file **advapi32.dll** non gestito.</span><span class="sxs-lookup"><span data-stu-id="e40f3-110">This method is not in the .NET Framework base class library, but is located in the unmanaged **advapi32.dll**.</span></span> <span data-ttu-id="e40f3-111">L'accesso ai metodi nel codice non gestito è un'operazione avanzata che non rientra nell'ambito di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e40f3-111">Accessing methods in unmanaged code is an advanced operation and is beyond the scope of this discussion.</span></span> <span data-ttu-id="e40f3-112">Per altre informazioni, vedere [Interoperabilità con codice non gestito](../../framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="e40f3-112">For more information, see [Interoperating with Unmanaged Code](../../framework/interop/index.md).</span></span> <span data-ttu-id="e40f3-113">Per altre informazioni sul metodo **LogonUser** e su **advapi32.dll**, vedere la documentazione di Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="e40f3-113">For more information about the **LogonUser** method and **advapi32.dll**, see the Platform SDK documentation.</span></span>  
  
2. <span data-ttu-id="e40f3-114">Creare una nuova istanza della classe **WindowsIdentity**, passando il token.</span><span class="sxs-lookup"><span data-stu-id="e40f3-114">Create a new instance of the **WindowsIdentity** class, passing the token.</span></span> <span data-ttu-id="e40f3-115">Il codice seguente illustra questa chiamata, dove `hToken` rappresenta un token di Windows.</span><span class="sxs-lookup"><span data-stu-id="e40f3-115">The following code demonstrates this call, where `hToken` represents a Windows token.</span></span>  
  
    ```csharp  
    WindowsIdentity impersonatedIdentity = new WindowsIdentity(hToken);  
    ```  
  
    ```vb  
    Dim impersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3. <span data-ttu-id="e40f3-116">Iniziare la rappresentazione creando una nuova istanza della classe <xref:System.Security.Principal.WindowsImpersonationContext> e inizializzandola con il metodo <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> della classe inizializzata, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e40f3-116">Begin impersonation by creating a new instance of the <xref:System.Security.Principal.WindowsImpersonationContext> class and initializing it with the <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> method of the initialized class, as shown in the following code.</span></span>  
  
    ```csharp  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate();  
    ```  
  
    ```vb  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate()  
    ```  
  
4. <span data-ttu-id="e40f3-117">Quando la rappresentazione non è più necessaria, chiamare il metodo <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> per ripristinare la rappresentazione, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e40f3-117">When you no longer need to impersonate, call the <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> method to revert the impersonation, as shown in the following code.</span></span>  
  
    ```csharp  
    myImpersonation.Undo();  
    ```  
  
    ```vb  
    myImpersonation.Undo()  
    ```  
  
 <span data-ttu-id="e40f3-118">Se il codice attendibile ha già associato un <xref:System.Security.Principal.WindowsPrincipal> oggetto al thread, è possibile chiamare il metodo di istanza **Impersonate**, che non accetta un token di account.</span><span class="sxs-lookup"><span data-stu-id="e40f3-118">If trusted code has already attached a <xref:System.Security.Principal.WindowsPrincipal> object to the thread, you can call the instance method **Impersonate**, which does not take an account token.</span></span> <span data-ttu-id="e40f3-119">Si noti che questo è utile solo quando l'oggetto **WindowsPrincipal** nel thread rappresenta un utente diverso da quello per cui il processo è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e40f3-119">Note that this is only useful when the **WindowsPrincipal** object on the thread represents a user other than the one under which the process is currently executing.</span></span> <span data-ttu-id="e40f3-120">Questa situazione può verificarsi, ad esempio, quando si usa ASP.NET con l'autenticazione di Windows attivata e la rappresentazione disattivata.</span><span class="sxs-lookup"><span data-stu-id="e40f3-120">For example, you might encounter this situation using ASP.NET with Windows authentication turned on and impersonation turned off.</span></span> <span data-ttu-id="e40f3-121">In questo caso, il processo viene eseguito con un account configurato in Internet Information Services (IIS), mentre l'entità corrente rappresenta l'utente di Windows che sta accedendo alla pagina.</span><span class="sxs-lookup"><span data-stu-id="e40f3-121">In this case, the process is running under an account configured in Internet Information Services (IIS) while the current principal represents the Windows user that is accessing the page.</span></span>  
  
 <span data-ttu-id="e40f3-122">Si noti che né **Impersonate** né **Undo** modificano l'oggetto **Principal** ( <xref:System.Security.Principal.IPrincipal> ) associato al contesto di chiamata corrente.</span><span class="sxs-lookup"><span data-stu-id="e40f3-122">Note that neither **Impersonate** nor **Undo** changes the **Principal** object (<xref:System.Security.Principal.IPrincipal>)  associated with the current call context.</span></span> <span data-ttu-id="e40f3-123">La rappresentazione e il ripristino modificano invece il token associato al processo del sistema operativo corrente.</span><span class="sxs-lookup"><span data-stu-id="e40f3-123">Rather, impersonation and reverting change the token associated with the current operating system process..</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e40f3-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e40f3-124">See also</span></span>

- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.Security.Principal.WindowsImpersonationContext>
- [<span data-ttu-id="e40f3-125">Oggetti Principal e Identity</span><span class="sxs-lookup"><span data-stu-id="e40f3-125">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
- [<span data-ttu-id="e40f3-126">Interoperabilità con codice non gestito</span><span class="sxs-lookup"><span data-stu-id="e40f3-126">Interoperating with Unmanaged Code</span></span>](../../framework/interop/index.md)
