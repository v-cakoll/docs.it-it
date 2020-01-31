---
title: Rappresentazione del client
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, impersonation sample
- Impersonating the Client Sample [Windows Communication Foundation]
- impersonation, Windows Communication Foundation sample
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
ms.openlocfilehash: e9e85729b10d1c992a22f6c0bea65dfd1e21e7e4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742561"
---
# <a name="impersonating-the-client"></a><span data-ttu-id="e3f00-102">Rappresentazione del client</span><span class="sxs-lookup"><span data-stu-id="e3f00-102">Impersonating the Client</span></span>
<span data-ttu-id="e3f00-103">L'esempio Rappresentazione di client mostra come rappresentare l'applicazione del chiamante al servizio così che il servizio possa accedere a risorse di sistema per conto del chiamante.</span><span class="sxs-lookup"><span data-stu-id="e3f00-103">The Impersonation sample demonstrates how to impersonate the caller application at the service so that the service can access system resources on behalf of the caller.</span></span>  
  
 <span data-ttu-id="e3f00-104">Questo esempio è basato sull'esempio [self-host](../../../../docs/framework/wcf/samples/self-host.md) .</span><span class="sxs-lookup"><span data-stu-id="e3f00-104">This sample is based on the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md) sample.</span></span> <span data-ttu-id="e3f00-105">Il servizio e i file di configurazione client corrispondono a quelli dell'esempio [self-host](../../../../docs/framework/wcf/samples/self-host.md) .</span><span class="sxs-lookup"><span data-stu-id="e3f00-105">The service and client configuration files are the same as that of the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md) sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3f00-106">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e3f00-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e3f00-107">Il codice del servizio è stato modificato in modo tale che il metodo `Add` nel servizio rappresenta il chiamante utilizzando <xref:System.ServiceModel.OperationBehaviorAttribute> come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e3f00-107">The service code has been modified such that the `Add` method on the service impersonates the caller using the <xref:System.ServiceModel.OperationBehaviorAttribute> as shown in the following sample code.</span></span>  
  
```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    Console.WriteLine("Received Add({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 <span data-ttu-id="e3f00-108">Di conseguenza, il contesto di sicurezza del thread in esecuzione passa a rappresentare il chiamante prima di immettere il metodo `Add` ed essere ripristinato sul metodo esistente.</span><span class="sxs-lookup"><span data-stu-id="e3f00-108">As a result, the security context of the executing thread is switched to impersonate the caller before entering the `Add` method and reverted on exiting the method.</span></span>  
  
 <span data-ttu-id="e3f00-109">Il metodo `DisplayIdentityInformation` illustrato nel codice di esempio seguente è una funzione di utilità che visualizza l'identità del chiamante.</span><span class="sxs-lookup"><span data-stu-id="e3f00-109">The `DisplayIdentityInformation` method shown in the following sample code is a utility function that displays the caller's identity.</span></span>  
  
```csharp
static void DisplayIdentityInformation()  
{  
    Console.WriteLine("\t\tThread Identity            :{0}",  
         WindowsIdentity.GetCurrent().Name);  
    Console.WriteLine("\t\tThread Identity level  :{0}",   
         WindowsIdentity.GetCurrent().ImpersonationLevel);  
    Console.WriteLine("\t\thToken                     :{0}",  
         WindowsIdentity.GetCurrent().Token.ToString());  
    return;  
}  
```  
  
 <span data-ttu-id="e3f00-110">Il metodo `Subtract` nel servizio rappresenta il chiamante utilizzando chiamate imperative come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e3f00-110">The `Subtract` method on the service impersonates the caller using imperative calls as shown in the following sample code.</span></span>  
  
```csharp
public double Subtract(double n1, double n2)  
{  
    double result = n1 - n2;  
    Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    Console.WriteLine("Before impersonating");  
    DisplayIdentityInformation();  
  
    if (ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Impersonation ||  
        ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Delegation)  
    {  
        // Impersonate.  
        using (ServiceSecurityContext.Current.WindowsIdentity.Impersonate())  
        {  
            // Make a system call in the caller's context and ACLs   
            // on the system resource are enforced in the caller's context.   
            Console.WriteLine("Impersonating the caller imperatively");  
            DisplayIdentityInformation();  
        }  
    }  
    else  
    {  
        Console.WriteLine("ImpersonationLevel is not high enough to perform this operation.");  
    }  
  
    Console.WriteLine("After reverting");  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 <span data-ttu-id="e3f00-111">Notare che in questo caso che il chiamante non è rappresentato per la chiamata intera ma è rappresentato solo per una parte della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e3f00-111">Note that in this case the caller is not impersonated for the entire call but is only impersonated for a portion of the call.</span></span> <span data-ttu-id="e3f00-112">In generale, la rappresentazione di ambiti più piccoli, è preferibile alla rappresentazione dell'intera operazione.</span><span class="sxs-lookup"><span data-stu-id="e3f00-112">In general, impersonating for the smallest scope is preferable to impersonating for the entire operation.</span></span>  
  
 <span data-ttu-id="e3f00-113">Gli altri metodi non rappresentano il chiamante.</span><span class="sxs-lookup"><span data-stu-id="e3f00-113">The other methods do not impersonate the caller.</span></span>  
  
 <span data-ttu-id="e3f00-114">Il codice client è stato modificato per impostare il livello di rappresentazione su <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>.</span><span class="sxs-lookup"><span data-stu-id="e3f00-114">The client code has been modified to set the impersonation level to <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>.</span></span> <span data-ttu-id="e3f00-115">Il client specifica il livello di rappresentazione che il servizio deve utilizzare, utilizzando l'enumerazione <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="e3f00-115">The client specifies the impersonation level to be used by the service, by using the <xref:System.Security.Principal.TokenImpersonationLevel> enumeration.</span></span> <span data-ttu-id="e3f00-116">L'enumerazione supporta i seguenti i seguenti valori: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> e <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>.</span><span class="sxs-lookup"><span data-stu-id="e3f00-116">The enumeration supports the following values: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> and <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>.</span></span> <span data-ttu-id="e3f00-117">Per eseguire una verifica di accesso quando si accede a una risorsa di sistema sul computer locale protetto utilizzando Windows ACL, il livello di rappresentazione deve essere impostato su <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, come mostra il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e3f00-117">To perform an access check when accessing a system resource on the local machine that is protected using Windows ACLs, the impersonation level must be set to <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, as shown in the following sample code.</span></span>  
  
```csharp
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 <span data-ttu-id="e3f00-118">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nelle finestre della console client e del servizio.</span><span class="sxs-lookup"><span data-stu-id="e3f00-118">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="e3f00-119">Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="e3f00-119">Press ENTER in each console window to shut down the service and client.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3f00-120">Il servizio deve essere eseguito con un account amministrativo o l'account in cui è in esecuzione deve disporre dei diritti per registrare l'URI del `http://localhost:8000/ServiceModelSamples` con il livello HTTP.</span><span class="sxs-lookup"><span data-stu-id="e3f00-120">The service must either run under an administrative account or the account it runs under must be granted rights to register the `http://localhost:8000/ServiceModelSamples` URI with the HTTP layer.</span></span> <span data-ttu-id="e3f00-121">Tali diritti possono essere concessi impostando una [prenotazione dello spazio dei nomi](/windows/win32/http/namespace-reservations-registrations-and-routing) utilizzando lo [strumento HttpCfg. exe](/windows/win32/http/httpcfg-exe).</span><span class="sxs-lookup"><span data-stu-id="e3f00-121">Such rights can be granted by setting up a [Namespace Reservation](/windows/win32/http/namespace-reservations-registrations-and-routing) using the [Httpcfg.exe tool](/windows/win32/http/httpcfg-exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3f00-122">Nei computer che eseguono Windows Server 2003, la rappresentazione è supportata solo se l'applicazione host. exe dispone del privilegio di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="e3f00-122">On computers running Windows Server 2003, impersonation is supported only if the Host.exe application has the Impersonation privilege.</span></span> <span data-ttu-id="e3f00-123">Per impostazione predefinita, solo gli amministratori dispongono di questa autorizzazione. Per aggiungere questo privilegio a un account con cui il servizio è in esecuzione, passare a **strumenti di amministrazione**, aprire **criteri di sicurezza locali**, aprire **criteri locali**, fare clic su **assegnazione diritti utente**e selezionare **rappresenta un client dopo l'autenticazione** e fare doppio clic su **Proprietà** per aggiungere un utente o un gruppo.</span><span class="sxs-lookup"><span data-stu-id="e3f00-123">(By default, only administrators have this permission.) To add this privilege to an account the service is running as, go to **Administrative Tools**, open **Local Security Policy**, open **Local Policies**, click **User Rights Assignment**, and select **Impersonate a Client after Authentication** and double-click **Properties** to add a user or group.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e3f00-124">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="e3f00-124">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e3f00-125">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e3f00-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="e3f00-126">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e3f00-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="e3f00-127">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e3f00-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
4. <span data-ttu-id="e3f00-128">Per dimostrare che il servizio rappresenta il chiamante, eseguire il client sotto un account diverso rispetto a quello sotto cui il servizio è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e3f00-128">To demonstrate that the service impersonates the caller, run the client under a different account than the one the service is running under.</span></span> <span data-ttu-id="e3f00-129">A tale scopo, al prompt dei comandi, digitare:</span><span class="sxs-lookup"><span data-stu-id="e3f00-129">To do so, at the command prompt, type:</span></span>  
  
    ```console  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     <span data-ttu-id="e3f00-130">Viene richiesta una password.</span><span class="sxs-lookup"><span data-stu-id="e3f00-130">You are then prompted for a password.</span></span> <span data-ttu-id="e3f00-131">Immettere la password per l'account precedentemente specificata.</span><span class="sxs-lookup"><span data-stu-id="e3f00-131">Enter the password for the account you previously specified.</span></span>  
  
5. <span data-ttu-id="e3f00-132">Quando si esegue il client, notare l'identità prima e dopo aver eseguito credenziali diverse.</span><span class="sxs-lookup"><span data-stu-id="e3f00-132">When you run the client, note the identity before and after running it with different credentials.</span></span>  
