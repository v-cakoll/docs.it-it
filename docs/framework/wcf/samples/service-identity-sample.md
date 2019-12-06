---
title: Esempio identità del servizio
ms.date: 03/30/2017
ms.assetid: 79fa8c1c-85bb-4b67-bc67-bfaf721303f8
ms.openlocfilehash: eb2dd3c6392164905cf755075856608ec5fcaf30
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837792"
---
# <a name="service-identity-sample"></a><span data-ttu-id="87185-102">Esempio identità del servizio</span><span class="sxs-lookup"><span data-stu-id="87185-102">Service Identity Sample</span></span>
<span data-ttu-id="87185-103">Questo esempio di identità del servizio illustra come impostare l'identità di un servizio.</span><span class="sxs-lookup"><span data-stu-id="87185-103">This service identity sample demonstrates how to set the identity for a service.</span></span> <span data-ttu-id="87185-104">In fase di progettazione, un client può recuperare l'identità utilizzando i metadati del servizio e quindi al runtime il client può autenticare l'identità del servizio.</span><span class="sxs-lookup"><span data-stu-id="87185-104">At design time, a client can retrieve the identity using the service's metadata and then at runtime the client can authenticate the service's identity.</span></span> <span data-ttu-id="87185-105">Il concetto di identità del servizio serve per consentire a un client di autenticare un servizio prima di chiamare qualsiasi operazione, proteggendo in questo modo il client da chiamate non autenticate.</span><span class="sxs-lookup"><span data-stu-id="87185-105">The concept of service identity is to allow a client to authenticate a service before calling any of its operations, thereby protecting the client from unauthenticated calls.</span></span> <span data-ttu-id="87185-106">Su una connessione sicura il servizio autentica anche le credenziali di un client prima di consentirgli l'accesso, ma questo non è il punto centrale dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="87185-106">On a secure connection the service also authenticates a client's credentials before allowing it access, but this is not the focus of this sample.</span></span> <span data-ttu-id="87185-107">Vedere gli esempi nel [client](../../../../docs/framework/wcf/samples/client.md) che mostrano l'autenticazione server.</span><span class="sxs-lookup"><span data-stu-id="87185-107">See the samples in [Client](../../../../docs/framework/wcf/samples/client.md) that show server authentication.</span></span>

> [!NOTE]
> <span data-ttu-id="87185-108">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="87185-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="87185-109">In questo esempio vengono illustrate le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="87185-109">This sample illustrates the following features:</span></span>

- <span data-ttu-id="87185-110">Come impostare tipi diversi di identità su endpoint diversi per un servizio.</span><span class="sxs-lookup"><span data-stu-id="87185-110">How to set the different types of identity on different endpoints for a service.</span></span> <span data-ttu-id="87185-111">Ogni tipo di identità ha funzionalità diverse.</span><span class="sxs-lookup"><span data-stu-id="87185-111">Each type of identity has different capabilities.</span></span> <span data-ttu-id="87185-112">Il tipo di identità da utilizzare dipende dal tipo di credenziali di sicurezza utilizzato sull'associazione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="87185-112">The type of identity to use is dependent on the type of security credentials used on the endpoint's binding.</span></span>

- <span data-ttu-id="87185-113">L'identità può essere impostata in modo dichiarativo a livello di configurazione o in modo imperativo a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="87185-113">Identity can either be set declaratively in configuration or imperatively in code.</span></span> <span data-ttu-id="87185-114">In genere, sia per il client che per il servizio, per impostare l'identità, è necessario utilizzare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="87185-114">Typically for both the client and the service you should use configuration to set the identity.</span></span>

- <span data-ttu-id="87185-115">Come impostare un'identità personalizzata in un client</span><span class="sxs-lookup"><span data-stu-id="87185-115">How to set a custom identity on the client.</span></span> <span data-ttu-id="87185-116">Un'identità personalizzata è in genere una personalizzazione di un tipo esistente di identità che consente al client di esaminare le altre informazioni della richiesta fornite nelle credenziali del servizio per prendere decisioni di autorizzazione prima di chiamare il servizio.</span><span class="sxs-lookup"><span data-stu-id="87185-116">A custom identity is typically a customization of an existing type of identity that enables the client to examine other claim information provided in the service's credentials to make authorization decisions before calling the service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87185-117">Questo esempio controlla l'identità di un certificato specifico chiamato identity.com e la chiave RSA contenuta al suo interno.</span><span class="sxs-lookup"><span data-stu-id="87185-117">This sample checks the identity of a specific certificate called identity.com and the RSA key contained within this certificate.</span></span> <span data-ttu-id="87185-118">Quando si utilizzano i tipi di identità del certificato e di RSA nella configurazione del client, un modo semplice per ottenere questi valori è di controllare il WSDL del servizio dove questi valori vengono serializzati.</span><span class="sxs-lookup"><span data-stu-id="87185-118">When using the Certificate and RSA identity types in configuration on the client, an easy way to get these values is to inspect the WSDL for the service where these values are serialized.</span></span>

 <span data-ttu-id="87185-119">Nel codice di esempio seguente viene mostrato come configurare l'identità di un endpoint del servizio con il DNS di un certificato utilizzando un'associazione WSHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="87185-119">The following sample code shows how to configure the identity of a service endpoint with the Domain Name Server (DNS) of a certificate using a WSHttpBinding.</span></span>

```csharp
//Create a service endpoint and set its identity to the certificate's DNS
WSHttpBinding wsAnonbinding = new WSHttpBinding (SecurityMode.Message);
// Client are Anonymous to the service
wsAnonbinding.Security.Message.ClientCredentialType = MessageCredentialType.None;
WServiceEndpoint ep = serviceHost.AddServiceEndpoint(typeof(ICalculator),wsAnonbinding, String.Empty);
EndpointAddress epa = new EndpointAddress(dnsrelativeAddress,EndpointIdentity.CreateDnsIdentity("identity.com"));
ep.Address = epa;
```

 <span data-ttu-id="87185-120">L'identità può anche essere specificata in fase di configurazione nel file App.config.</span><span class="sxs-lookup"><span data-stu-id="87185-120">The identity can also be specified in configuration in the App.config file.</span></span> <span data-ttu-id="87185-121">Nell'esempio seguente viene mostrato come impostare l'identità di UPN (User Principal Name) per un endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="87185-121">The following example shows how to set the UPN (User Principal Name) identity for a service endpoint.</span></span>

```xml
<endpoint address="upnidentity"
        behaviorConfiguration=""
        binding="wsHttpBinding"
        bindingConfiguration="WSHttpBinding_Windows"
        name="WSHttpBinding_ICalculator_Windows"
        contract="Microsoft.ServiceModel.Samples.ICalculator">
  <!-- Set the UPN identity for this endpoint -->
  <identity>
      <userPrincipalName value="host\myservice.com" />
  </identity >
</endpoint>
```

 <span data-ttu-id="87185-122">Un'identità personalizzata può essere impostata sul client derivando dalle classi <xref:System.ServiceModel.EndpointIdentity> e <xref:System.ServiceModel.Security.IdentityVerifier>.</span><span class="sxs-lookup"><span data-stu-id="87185-122">A custom identity can be set on the client by deriving from the <xref:System.ServiceModel.EndpointIdentity> and the <xref:System.ServiceModel.Security.IdentityVerifier> classes.</span></span> <span data-ttu-id="87185-123">Concettualmente la classe <xref:System.ServiceModel.Security.IdentityVerifier> può essere considerata l'equivalente client della classe `AuthorizationManager` del servizio.</span><span class="sxs-lookup"><span data-stu-id="87185-123">Conceptually the <xref:System.ServiceModel.Security.IdentityVerifier> class can be considered to be the client equivalent of the service's `AuthorizationManager` class.</span></span> <span data-ttu-id="87185-124">Nell'esempio di codice seguente viene mostrata un'implementazione di `OrgEndpointIdentity` che archivia il nome di un'organizzazione affinché corrisponda al nome dell'oggetto del certificato del server.</span><span class="sxs-lookup"><span data-stu-id="87185-124">The following code example shows an implementation of `OrgEndpointIdentity`, which stores an organization name to match in the subject name of the server's certificate.</span></span> <span data-ttu-id="87185-125">Il controllo dell'autorizzazione per il nome dell'organizzazione si verifica nel metodo `CheckAccess` sulla classe `CustomIdentityVerifier`.</span><span class="sxs-lookup"><span data-stu-id="87185-125">The authorization check for the organization name occurs in the `CheckAccess` method on the `CustomIdentityVerifier` class.</span></span>

```csharp
// This custom EndpointIdentity stores an organization name
public class OrgEndpointIdentity : EndpointIdentity
{
    private string orgClaim;
    public OrgEndpointIdentity(string orgName)
    {
        orgClaim = orgName;
    }
    public string OrganizationClaim
    {
        get { return orgClaim; }
        set { orgClaim = value; }
    }
}

//This custom IdentityVerifier uses the supplied OrgEndpointIdentity to
//check that X.509 certificate's distinguished name claim contains
//the organization name e.g. the string value "O=Contoso"
class CustomIdentityVerifier : IdentityVerifier
{
    public override bool CheckAccess(EndpointIdentity identity, AuthorizationContext authContext)
    {
        bool returnvalue = false;
        foreach (ClaimSet claimset in authContext.ClaimSets)
        {
            foreach (Claim claim in claimset)
            {
                if (claim.ClaimType == "http://schemas.microsoft.com/ws/2005/05/identity/claims/x500distinguishedname")
                {
                    X500DistinguishedName name = (X500DistinguishedName)claim.Resource;
                    if (name.Name.Contains(((OrgEndpointIdentity)identity).OrganizationClaim))
                    {
                        Console.WriteLine("Claim Type: {0}",claim.ClaimType);
                        Console.WriteLine("Right: {0}", claim.Right);
                        Console.WriteLine("Resource: {0}",claim.Resource);
                        Console.WriteLine();
                        returnvalue = true;
                    }
                }
            }
        }
        return returnvalue;
    }
}
```

 <span data-ttu-id="87185-126">Questo esempio utilizza un certificato chiamato identity.com che è situato nella cartella Identity della soluzione specifica del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="87185-126">This sample uses a certificate called identity.com which is in the language-specific Identity solution folder.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="87185-127">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="87185-127">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="87185-128">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="87185-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="87185-129">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="87185-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="87185-130">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="87185-130">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="87185-131">Per eseguire l'esempio nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="87185-131">To run the sample on the same computer</span></span>

1. <span data-ttu-id="87185-132">In [!INCLUDE[wxp](../../../../includes/wxp-md.md)] o Windows Vista importare il file di certificato Identity. pfx nella cartella Identity Solution nell'archivio certificati LocalMachine/My (Personal) utilizzando lo snap-in MMC.</span><span class="sxs-lookup"><span data-stu-id="87185-132">On [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or Windows Vista, import the Identity.pfx certificate file in the Identity solution folder into the LocalMachine/My (Personal) certificate store using the MMC snap-in tool.</span></span> <span data-ttu-id="87185-133">Questo file è protetto da password.</span><span class="sxs-lookup"><span data-stu-id="87185-133">This file is password protected.</span></span> <span data-ttu-id="87185-134">Durante l'importazione viene richiesta una password.</span><span class="sxs-lookup"><span data-stu-id="87185-134">During the import you are asked for a password.</span></span> <span data-ttu-id="87185-135">Digitare `xyz` nella casella password.</span><span class="sxs-lookup"><span data-stu-id="87185-135">Type `xyz` into the password box.</span></span> <span data-ttu-id="87185-136">Per ulteriori informazioni, vedere l'argomento [procedura: visualizzare i certificati con lo snap-in MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) .</span><span class="sxs-lookup"><span data-stu-id="87185-136">For more information, see the [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) topic.</span></span> <span data-ttu-id="87185-137">Al termine, eseguire Setup. bat in una Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore, che copia il certificato nell'archivio CurrentUser/Trusted People per l'utilizzo nel client.</span><span class="sxs-lookup"><span data-stu-id="87185-137">Once this is done, run Setup.bat in a Developer Command Prompt for Visual Studio with administrator privileges, which copies this certificate to the CurrentUser/Trusted People store for use on the client.</span></span>

2. <span data-ttu-id="87185-138">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]eseguire Setup. bat dalla cartella di installazione dell'esempio all'interno di un prompt dei comandi di Visual Studio 2012 con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="87185-138">On [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], run Setup.bat from the sample install folder inside a Visual Studio 2012 command prompt with administrator privileges.</span></span> <span data-ttu-id="87185-139">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="87185-139">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="87185-140">Il file batch Setup. bat è progettato per essere eseguito da un prompt dei comandi di Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="87185-140">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="87185-141">La variabile di ambiente PATH impostata nel prompt dei comandi di Visual Studio 2012 punta alla directory che contiene i file eseguibili richiesti dallo script Setup. bat.</span><span class="sxs-lookup"><span data-stu-id="87185-141">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span> <span data-ttu-id="87185-142">Assicurarsi di rimuovere i certificati eseguendo Cleanup.bat una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="87185-142">Ensure that you remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="87185-143">Negli altri esempi relativi alla sicurezza vengono usati gli stessi certificati.</span><span class="sxs-lookup"><span data-stu-id="87185-143">Other security samples use the same certificates.</span></span>  
  
3. <span data-ttu-id="87185-144">Avviare Service.exe dalla directory \service\bin.</span><span class="sxs-lookup"><span data-stu-id="87185-144">Launch Service.exe from the \service\bin directory.</span></span> <span data-ttu-id="87185-145">Verificare che il servizio indichi che è pronto e visualizza una richiesta di premere \<immettere > per terminare il servizio.</span><span class="sxs-lookup"><span data-stu-id="87185-145">Ensure that the service indicates that it is ready and displays a prompt to Press \<Enter> to terminate the service.</span></span>  
  
4. <span data-ttu-id="87185-146">Avviare Client.exe dalla directory \client\bin o premendo F5 in Visual Studio per compilare ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="87185-146">Launch Client.exe from \client\bin directory or by pressing F5 in Visual Studio to build and run.</span></span> <span data-ttu-id="87185-147">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="87185-147">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="87185-148">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="87185-148">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="87185-149">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="87185-149">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="87185-150">Prima di compilare la parte client dell'esempio, assicurarsi di aver modificato il valore dell'indirizzo endpoint del servizio nel file Client.cs nel metodo `CallServiceCustomClientIdentity`.</span><span class="sxs-lookup"><span data-stu-id="87185-150">Before building the client part of the sample, be sure to change the value for the service's endpoint address in the Client.cs file in the `CallServiceCustomClientIdentity` method.</span></span> <span data-ttu-id="87185-151">Quindi compilare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="87185-151">Then build the sample.</span></span>  
  
2. <span data-ttu-id="87185-152">Creare una directory sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="87185-152">Create a directory on the service computer.</span></span>  
  
3. <span data-ttu-id="87185-153">Copiare i file di programma del servizio da \service\bin nella directory del computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="87185-153">Copy the service program files from service\bin to the directory on the service computer.</span></span> <span data-ttu-id="87185-154">Copiare i file Setup.bat e Cleanup.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="87185-154">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
4. <span data-ttu-id="87185-155">Creare una directory sul client del servizio per i file binari del client.</span><span class="sxs-lookup"><span data-stu-id="87185-155">Create a directory on the client computer for the client binaries.</span></span>  
  
5. <span data-ttu-id="87185-156">Copiare i file di programma del client nella directory del client sul computer relativo</span><span class="sxs-lookup"><span data-stu-id="87185-156">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="87185-157">e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.</span><span class="sxs-lookup"><span data-stu-id="87185-157">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
6. <span data-ttu-id="87185-158">Nel servizio eseguire `setup.bat service` in un Prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="87185-158">On the service, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="87185-159">Quando si esegue `setup.bat` con l'argomento `service` viene creato un certificato di servizio con il nome di dominio completo del computer e il certificato del servizio viene esportato in un file denominato Service. cer.</span><span class="sxs-lookup"><span data-stu-id="87185-159">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
7. <span data-ttu-id="87185-160">Copiare il file Service.cer dalla directory del servizio nella directory del client sul computer relativo.</span><span class="sxs-lookup"><span data-stu-id="87185-160">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="87185-161">Nel file Client.exe.config presente nel computer client modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="87185-161">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="87185-162">Sono presenti più istanze che devono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="87185-162">There are multiple instances that must be changed.</span></span>  
  
9. <span data-ttu-id="87185-163">Sul client, eseguire ImportServiceCert. bat in un Prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="87185-163">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="87185-164">In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="87185-164">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="87185-165">Sul computer del servizio eseguire Service.exe dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="87185-165">On the service computer, launch the Service.exe from the command prompt.</span></span>  
  
11. <span data-ttu-id="87185-166">Sul computer client avviare Client.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="87185-166">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="87185-167">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="87185-167">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="87185-168">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="87185-168">To clean up after the sample</span></span>  
  
- <span data-ttu-id="87185-169">Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="87185-169">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="87185-170">Questo script non rimuove i certificati del servizio da un client quando si esegue l'esempio tra più computer.</span><span class="sxs-lookup"><span data-stu-id="87185-170">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="87185-171">Se sono stati eseguiti esempi Windows Communication Foundation (WCF) che usano certificati tra computer, assicurarsi di cancellare i certificati del servizio installati nell'archivio CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="87185-171">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="87185-172">Per eseguire questa operazione, usare il seguente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="87185-172">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
