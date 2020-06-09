---
title: Token di supporto
ms.date: 03/30/2017
ms.assetid: 65a8905d-92cc-4ab0-b6ed-1f710e40784e
ms.openlocfilehash: 9c8ee4b11cd61e51e91c2e116ab3c20448fc1a58
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84575043"
---
# <a name="supporting-tokens"></a><span data-ttu-id="0271d-102">Token di supporto</span><span class="sxs-lookup"><span data-stu-id="0271d-102">Supporting Tokens</span></span>
<span data-ttu-id="0271d-103">L'esempio dei token di supporto illustra come aggiungere token aggiuntivi a un messaggio che utilizza WS-Security.</span><span class="sxs-lookup"><span data-stu-id="0271d-103">The Supporting Tokens sample demonstrates how to add additional tokens to a message that uses WS-Security.</span></span> <span data-ttu-id="0271d-104">L'esempio aggiunge un token di sicurezza binario X.509 e un token di sicurezza nome utente.</span><span class="sxs-lookup"><span data-stu-id="0271d-104">The example adds an X.509 binary security token in addition to a username security token.</span></span> <span data-ttu-id="0271d-105">Il token viene passato in un'intestazione di un messaggio WS-Security dal client al servizio e parte del messaggio viene firmata con la chiave privata associata al token di sicurezza X.509 per provare il possesso del certificato X.509 al destinatario.</span><span class="sxs-lookup"><span data-stu-id="0271d-105">The token is passed in a WS-Security message header from the client to the service and part of the message is signed with the private key associated with the X.509 security token to prove the possession of the X.509 certificate to the receiver.</span></span> <span data-ttu-id="0271d-106">Ciò è utile nel caso in cui vi sia un requisito di più richieste per autenticare o autorizzare il mittente associate a un messaggio.</span><span class="sxs-lookup"><span data-stu-id="0271d-106">This is useful in the case when there is a requirement to have multiple claims associated with a message to authenticate or authorize the sender.</span></span> <span data-ttu-id="0271d-107">Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="0271d-107">The service implements a contract that defines a request-reply communication pattern.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="0271d-108">Dimostra</span><span class="sxs-lookup"><span data-stu-id="0271d-108">Demonstrates</span></span>
 <span data-ttu-id="0271d-109">L'esempio illustra quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0271d-109">The sample demonstrates:</span></span>

- <span data-ttu-id="0271d-110">Come un client può passare token di sicurezza aggiuntivi a un servizio.</span><span class="sxs-lookup"><span data-stu-id="0271d-110">How a client can pass additional security tokens to a service.</span></span>

- <span data-ttu-id="0271d-111">Come il server può accedere a richieste associate ai token di sicurezza aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="0271d-111">How the server can access claims associated with additional security tokens.</span></span>

- <span data-ttu-id="0271d-112">Come viene usato il certificato X.509 del server per proteggere la chiave simmetrica usata per crittografare il messaggio e la firma.</span><span class="sxs-lookup"><span data-stu-id="0271d-112">How the server's X.509 certificate is used to protect the symmetric key used for message encryption and signature.</span></span>

> [!NOTE]
> <span data-ttu-id="0271d-113">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0271d-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

## <a name="client-authenticates-with-username-token-and-supporting-x509-security-token"></a><span data-ttu-id="0271d-114">Il client autentica con token nome utente e token di sicurezza X.509 di supporto</span><span class="sxs-lookup"><span data-stu-id="0271d-114">Client Authenticates with Username Token and Supporting X.509 Security Token</span></span>
 <span data-ttu-id="0271d-115">Il servizio espone un solo endpoint per comunicare con il servizio che viene creato a livello di codice utilizzando le classi `BindingHelper` e `EchoServiceHost`.</span><span class="sxs-lookup"><span data-stu-id="0271d-115">The service exposes a single endpoint for communicating that is programmatically created using the `BindingHelper` and `EchoServiceHost` classes.</span></span> <span data-ttu-id="0271d-116">L'endpoint è costituito da un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="0271d-116">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="0271d-117">L'associazione è configurata con un'associazione personalizzata usando `SymmetricSecurityBindingElement` e `HttpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="0271d-117">The binding is configured with a custom binding using `SymmetricSecurityBindingElement` and `HttpTransportBindingElement`.</span></span> <span data-ttu-id="0271d-118">Questo esempio imposta `SymmetricSecurityBindingElement` per utilizzare un certificato X.509 del servizio per proteggere la chiave simmetrica durante la trasmissione e passare un `UserNameToken` insieme a un  `X509SecurityToken` di supporto in un'intestazione del messaggio WS-Security.</span><span class="sxs-lookup"><span data-stu-id="0271d-118">This sample sets the `SymmetricSecurityBindingElement` to use a service X.509 certificate to protect the symmetric key during transmission and to pass a `UserNameToken` along with the supporting `X509SecurityToken` in a WS-Security message header.</span></span> <span data-ttu-id="0271d-119">La chiave simmetrica viene utilizzata per crittografare il corpo del messaggio e il token di sicurezza del nome utente.</span><span class="sxs-lookup"><span data-stu-id="0271d-119">The symmetric key is used to encrypt the message body and the username security token.</span></span> <span data-ttu-id="0271d-120">Il token di supporto viene passato come un token di sicurezza binario aggiuntivo nell'intestazione del messaggio WS-Security.</span><span class="sxs-lookup"><span data-stu-id="0271d-120">The supporting token is passed as an additional binary security token in the WS-Security message header.</span></span> <span data-ttu-id="0271d-121">L'autenticità del token di supporto viene provata firmando parte del messaggio con la chiave privata associata con il token di sicurezza X.509 di supporto.</span><span class="sxs-lookup"><span data-stu-id="0271d-121">The authenticity of the supporting token is proved by signing part of the message with the private key associated with the supporting X.509 security token.</span></span>

```csharp
public static Binding CreateMultiFactorAuthenticationBinding()
{
    HttpTransportBindingElement httpTransport = new HttpTransportBindingElement();

    // the message security binding element will be configured to require 2 tokens:
    // 1) A username-password encrypted with the service token
    // 2) A client certificate used to sign the message

    // Instantiate a binding element that will require the username/password token in the message (encrypted with the server cert)
    SymmetricSecurityBindingElement messageSecurity = SecurityBindingElement.CreateUserNameForCertificateBindingElement();

    // Create supporting token parameters for the client X509 certificate.
    X509SecurityTokenParameters clientX509SupportingTokenParameters = new X509SecurityTokenParameters();
    // Specify that the supporting token is passed in message send by the client to the service
    clientX509SupportingTokenParameters.InclusionMode = SecurityTokenInclusionMode.AlwaysToRecipient;
    // Turn off derived keys
    clientX509SupportingTokenParameters.RequireDerivedKeys = false;
    // Augment the binding element to require the client's X509 certificate as an endorsing token in the message
    messageSecurity.EndpointSupportingTokenParameters.Endorsing.Add(clientX509SupportingTokenParameters);

    // Create a CustomBinding based on the constructed security binding element.
    return new CustomBinding(messageSecurity, httpTransport);
}
```

 <span data-ttu-id="0271d-122">Il comportamento specifica le credenziali del servizio che devono essere usate per l'autenticazione del client e anche informazioni sul certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="0271d-122">The behavior specifies the service credentials that are to be used for client authentication and also information about the service X.509 certificate.</span></span> <span data-ttu-id="0271d-123">L'esempio utilizza `CN=localhost` come nome del soggetto nel certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="0271d-123">The sample uses `CN=localhost` as a subject name in the service X.509 certificate.</span></span>

```csharp
override protected void InitializeRuntime()
{
    // Extract the ServiceCredentials behavior or create one.
    ServiceCredentials serviceCredentials =
        this.Description.Behaviors.Find<ServiceCredentials>();
    if (serviceCredentials == null)
    {
        serviceCredentials = new ServiceCredentials();
        this.Description.Behaviors.Add(serviceCredentials);
    }

    // Set the service certificate
    serviceCredentials.ServiceCertificate.SetCertificate(
                                       "CN=localhost");

/*
Setting the CertificateValidationMode to PeerOrChainTrust means that if the certificate is in the Trusted People store, then it will be trusted without performing a validation of the certificate's issuer chain. This setting is used here for convenience so that the sample can be run without having to have certificates issued by a certification authority (CA).
This setting is less secure than the default, ChainTrust. The security implications of this setting should be carefully considered before using PeerOrChainTrust in production code.
*/
    serviceCredentials.ClientCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;

    // Create the custom binding and add an endpoint to the service.
    Binding multipleTokensBinding =
         BindingHelper.CreateMultiFactorAuthenticationBinding();
    this.AddServiceEndpoint(typeof(IEchoService),
                          multipleTokensBinding, string.Empty);
    base.InitializeRuntime();
}
```

 <span data-ttu-id="0271d-124">Codice del servizio</span><span class="sxs-lookup"><span data-stu-id="0271d-124">Service code:</span></span>

```csharp
[ServiceBehavior(IncludeExceptionDetailInFaults = true)]
public class EchoService : IEchoService
{
    public string Echo()
    {
        string userName;
        string certificateSubjectName;
        GetCallerIdentities(
            OperationContext.Current.ServiceSecurityContext,
            out userName,
            out certificateSubjectName);
            return $"Hello {userName}, {certificateSubjectName}";
    }

    public void Dispose()
    {
    }

    bool TryGetClaimValue<TClaimResource>(ClaimSet claimSet,
            string claimType, out TClaimResource resourceValue)
            where TClaimResource : class
    {
        resourceValue = default(TClaimResource);
        IEnumerable<Claim> matchingClaims =
            claimSet.FindClaims(claimType, Rights.PossessProperty);
        if(matchingClaims == null)
            return false;
        IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();
        if (enumerator.MoveNext())
        {
            resourceValue =
              (enumerator.Current.Resource == null) ? null :
              (enumerator.Current.Resource as TClaimResource);
            return true;
        }
        else
        {
            return false;
        }
    }

    // Returns the username and certificate subject name provided by
    //the client
    void GetCallerIdentities(ServiceSecurityContext
        callerSecurityContext,
        out string userName, out string certificateSubjectName)
    {
        userName = null;
        certificateSubjectName = null;

       // Look in all the claimsets in the authorization context
       foreach (ClaimSet claimSet in
               callerSecurityContext.AuthorizationContext.ClaimSets)
       {
            if (claimSet is WindowsClaimSet)
            {
                // Try to find a Name claim. This will have been
                // generated from the windows username.
                string tmpName;
                if (TryGetClaimValue<string>(claimSet, ClaimTypes.Name,
                                                      out tmpName))
                {
                    userName = tmpName;
                }
            }
            else if (claimSet is X509CertificateClaimSet)
            {
                // Try to find an X500DistinguishedName claim. This will
                // have been generated from the client certificate.
                X500DistinguishedName tmpDistinguishedName;
                if (TryGetClaimValue<X500DistinguishedName>(claimSet,
                               ClaimTypes.X500DistinguishedName,
                               out tmpDistinguishedName))
                {
                    certificateSubjectName = tmpDistinguishedName.Name;
                }
            }
        }
    }
}
```

 <span data-ttu-id="0271d-125">L'endpoint del client viene configurato in modo simile all'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="0271d-125">The client endpoint is configured in a similar way to the service endpoint.</span></span> <span data-ttu-id="0271d-126">Il client usa la stessa classe `BindingHelper` per creare un'associazione.</span><span class="sxs-lookup"><span data-stu-id="0271d-126">The client uses the same `BindingHelper` class to create a binding.</span></span> <span data-ttu-id="0271d-127">Il resto dell'installazione è situato nella classe `Client`.</span><span class="sxs-lookup"><span data-stu-id="0271d-127">The rest of the setup is located in `Client` class.</span></span> <span data-ttu-id="0271d-128">Il client imposta informazioni sul token di sicurezza del nome utente, il token di sicurezza X.509 di supporto e informazioni sul certificato X.509 del servizio nel codice dell'installazione sulla raccolta dei comportamenti dell'endpoint del client.</span><span class="sxs-lookup"><span data-stu-id="0271d-128">The client sets information about the user name security token, the supporting X.509 security token and information about the service X.509 certificate in the setup code to the client endpoint behaviors collection.</span></span>

```csharp
 static void Main()
 {
     // Create the custom binding and an endpoint address for
     // the service.
     Binding multipleTokensBinding =
         BindingHelper.CreateMultiFactorAuthenticationBinding();
         EndpointAddress serviceAddress = new EndpointAddress(
         "http://localhost/servicemodelsamples/service.svc");
       ChannelFactory<IEchoService> channelFactory = null;
       IEchoService client = null;

       Console.WriteLine("Username authentication required.");
       Console.WriteLine(
         "Provide a valid machine or domain account. [domain\\user]");
       Console.WriteLine("   Enter username:");
       string username = Console.ReadLine();
       Console.WriteLine("   Enter password:");
       string password = "";
       ConsoleKeyInfo info = Console.ReadKey(true);
       while (info.Key != ConsoleKey.Enter)
       {
           if (info.Key != ConsoleKey.Backspace)
           {
               if (info.KeyChar != '\0')
               {
                   password += info.KeyChar;
                }
                info = Console.ReadKey(true);
            }
            else if (info.Key == ConsoleKey.Backspace)
            {
                if (password != "")
                {
                    password =
                       password.Substring(0, password.Length - 1);
                }
                info = Console.ReadKey(true);
            }
         }
         for (int i = 0; i < password.Length; i++)
            Console.Write("*");
         Console.WriteLine();
         try
         {
           // Create a proxy with the previously create binding and
           // endpoint address
              channelFactory =
                 new ChannelFactory<IEchoService>(
                     multipleTokensBinding, serviceAddress);
           // configure the username credentials, the client
           // certificate and the server certificate on the channel
           // factory
           channelFactory.Credentials.UserName.UserName = username;
           channelFactory.Credentials.UserName.Password = password;
           channelFactory.Credentials.ClientCertificate.SetCertificate(
           "CN=client.com", StoreLocation.CurrentUser, StoreName.My);
              channelFactory.Credentials.ServiceCertificate.SetDefaultCertificate(
           "CN=localhost", StoreLocation.LocalMachine, StoreName.My);
           client = channelFactory.CreateChannel();
           Console.WriteLine("Echo service returned: {0}",
                                           client.Echo());

           ((IChannel)client).Close();
           channelFactory.Close();
        }
        catch (CommunicationException e)
        {
         Abort((IChannel)client, channelFactory);
         // if there is a fault then print it out
         FaultException fe = null;
         Exception tmp = e;
         while (tmp != null)
         {
            fe = tmp as FaultException;
            if (fe != null)
            {
                break;
            }
            tmp = tmp.InnerException;
        }
        if (fe != null)
        {
           Console.WriteLine("The server sent back a fault: {0}",
         fe.CreateMessageFault().Reason.GetMatchingTranslation().Text);
        }
        else
        {
         Console.WriteLine("The request failed with exception: {0}",e);
        }
    }
    catch (TimeoutException)
    {
        Abort((IChannel)client, channelFactory);
        Console.WriteLine("The request timed out");
    }
    catch (Exception e)
    {
         Abort((IChannel)client, channelFactory);
          Console.WriteLine(
          "The request failed with unexpected exception: {0}", e);
    }
    Console.WriteLine();
    Console.WriteLine("Press <ENTER> to terminate client.");
    Console.ReadLine();
}
```

## <a name="displaying-callers-information"></a><span data-ttu-id="0271d-129">Visualizzazione delle informazioni sul chiamante</span><span class="sxs-lookup"><span data-stu-id="0271d-129">Displaying Callers' Information</span></span>
 <span data-ttu-id="0271d-130">Per visualizzare le informazioni sul chiamante è possibile utilizzare `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` come mostra il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="0271d-130">To display the caller's information, you can use the `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` as shown in the following code.</span></span> <span data-ttu-id="0271d-131">`ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contiene attestazioni di autorizzazione associate al chiamante corrente.</span><span class="sxs-lookup"><span data-stu-id="0271d-131">The `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contains authorization claims associated with the current caller.</span></span> <span data-ttu-id="0271d-132">Queste attestazioni vengono fornite automaticamente da Windows Communication Foundation (WCF) per ogni token ricevuto nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="0271d-132">Those claims are supplied automatically by Windows Communication Foundation (WCF) for every token received in the message.</span></span>

```csharp
bool TryGetClaimValue<TClaimResource>(ClaimSet claimSet, string
                         claimType, out TClaimResource resourceValue)
    where TClaimResource : class
{
    resourceValue = default(TClaimResource);
    IEnumerable<Claim> matchingClaims =
    claimSet.FindClaims(claimType, Rights.PossessProperty);
    if (matchingClaims == null)
          return false;
    IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();
    if (enumerator.MoveNext())
    {
        resourceValue = (enumerator.Current.Resource == null) ? null : (enumerator.Current.Resource as TClaimResource);
        return true;
    }
    else
    {
         return false;
    }
}

// Returns the username and certificate subject name provided by the client
void GetCallerIdentities(ServiceSecurityContext callerSecurityContext, out string userName, out string certificateSubjectName)
{
    userName = null;
    certificateSubjectName = null;

    // Look in all the claimsets in the authorization context
    foreach (ClaimSet claimSet in
      callerSecurityContext.AuthorizationContext.ClaimSets)
    {
        if (claimSet is WindowsClaimSet)
        {
            // Try to find a Name claim. This will have been generated
            //from the windows username.
            string tmpName;
            if (TryGetClaimValue<string>(claimSet, ClaimTypes.Name,
                                                     out tmpName))
            {
                userName = tmpName;
            }
        }
        else if (claimSet is X509CertificateClaimSet)
         {
            //Try to find an X500DistinguishedName claim.
            //This will have been generated from the client
            //certificate.
            X500DistinguishedName tmpDistinguishedName;
            if (TryGetClaimValue<X500DistinguishedName>(claimSet,
               ClaimTypes.X500DistinguishedName,
               out tmpDistinguishedName))
            {
                    certificateSubjectName = tmpDistinguishedName.Name;
            }
        }
    }
}
```

## <a name="running-the-sample"></a><span data-ttu-id="0271d-133">Esecuzione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="0271d-133">Running the Sample</span></span>
 <span data-ttu-id="0271d-134">Quando si esegue l'esempio, il client innanzitutto richiede nome utente e password per il token del nome utente.</span><span class="sxs-lookup"><span data-stu-id="0271d-134">When you run the sample, the client first prompts you to provide user name and password for the user name token.</span></span> <span data-ttu-id="0271d-135">Assicurarsi di specificare i valori corretti per l'account di sistema, perché WCF nel servizio esegue il mapping dei valori forniti nel token del nome utente nell'identità fornita dal sistema.</span><span class="sxs-lookup"><span data-stu-id="0271d-135">Be sure to provide correct values for your system account, because WCF on the service maps the values supplied in the user name token into the identity provided by the system.</span></span> <span data-ttu-id="0271d-136">Successivamente, il client visualizza la risposta del servizio.</span><span class="sxs-lookup"><span data-stu-id="0271d-136">After that, the client displays the response from the service.</span></span> <span data-ttu-id="0271d-137">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="0271d-137">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="0271d-138">File batch di installazione</span><span class="sxs-lookup"><span data-stu-id="0271d-138">Setup Batch File</span></span>
 <span data-ttu-id="0271d-139">Il file batch Setup.bat incluso in questo esempio consente di configurare il server con i certificati attinenti per eseguire un'applicazione ospitata su Internet Information Services (IIS) che richiede sicurezza server basata su certificato.</span><span class="sxs-lookup"><span data-stu-id="0271d-139">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run Internet Information Services (IIS) hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="0271d-140">Questo file batch deve essere modificato per funzionare tra più computer o in caso di applicazioni indipendenti.</span><span class="sxs-lookup"><span data-stu-id="0271d-140">This batch file must be modified to work across machines or to work in a non-hosted case.</span></span>

 <span data-ttu-id="0271d-141">Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch in modo che possano essere modificate per l'esecuzione nella configurazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="0271d-141">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration.</span></span>

### <a name="creating-the-client-certificate"></a><span data-ttu-id="0271d-142">Creazione del certificato del client</span><span class="sxs-lookup"><span data-stu-id="0271d-142">Creating the Client Certificate</span></span>
 <span data-ttu-id="0271d-143">Le righe seguenti del file batch Setup.bat creano il certificato client da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="0271d-143">The following lines from the Setup.bat batch file create the client certificate to be used.</span></span> <span data-ttu-id="0271d-144">La variabile `%CLIENT_NAME%` specifica l'oggetto del certificato client.</span><span class="sxs-lookup"><span data-stu-id="0271d-144">The `%CLIENT_NAME%` variable specifies the subject of the client certificate.</span></span> <span data-ttu-id="0271d-145">Questo esempio utilizza "client.com" come nome del soggetto.</span><span class="sxs-lookup"><span data-stu-id="0271d-145">This sample uses "client.com" as the subject name.</span></span>

 <span data-ttu-id="0271d-146">Il certificato viene memorizzato nell'archivio personale nel percorso di archivio `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="0271d-146">The certificate is stored in My (Personal) store under the `CurrentUser` store location.</span></span>

```console
echo ************
echo making client cert
echo ************
makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
```

### <a name="installing-the-client-certificate-into-the-servers-trusted-store"></a><span data-ttu-id="0271d-147">Installazione del certificato client nell'archivio certificati attendibili del server:</span><span class="sxs-lookup"><span data-stu-id="0271d-147">Installing the Client Certificate into the Server's Trusted Store</span></span>
 <span data-ttu-id="0271d-148">La riga seguente nel file batch Setup.bat copia il certificato client nell'archivio delle persone attendibili del server.</span><span class="sxs-lookup"><span data-stu-id="0271d-148">The following line in the Setup.bat batch file copies the client certificate into the server’s trusted people store.</span></span> <span data-ttu-id="0271d-149">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema server.</span><span class="sxs-lookup"><span data-stu-id="0271d-149">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the server’s system.</span></span> <span data-ttu-id="0271d-150">Se è già disponibile un certificato con radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il passaggio del popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="0271d-150">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

```console
echo ************
echo copying client cert to server's CurrentUserstore
echo ************
certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
```

### <a name="creating-the-server-certificate"></a><span data-ttu-id="0271d-151">Creazione del certificato del server:</span><span class="sxs-lookup"><span data-stu-id="0271d-151">Creating the Server Certificate</span></span>
 <span data-ttu-id="0271d-152">Le righe seguenti del file batch Setup.bat creano il certificato server da usare.</span><span class="sxs-lookup"><span data-stu-id="0271d-152">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="0271d-153">La variabile `%SERVER_NAME%` specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="0271d-153">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="0271d-154">Modificare questa variabile per specificare nome del server.</span><span class="sxs-lookup"><span data-stu-id="0271d-154">Change this variable to specify your own server name.</span></span> <span data-ttu-id="0271d-155">Il valore predefinito in questo file batch è localhost.</span><span class="sxs-lookup"><span data-stu-id="0271d-155">The default in this batch file is localhost.</span></span>

 <span data-ttu-id="0271d-156">Il certificato viene memorizzato nell'archivio personale nel percorso di archivio LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="0271d-156">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span> <span data-ttu-id="0271d-157">Il certificato viene archiviato nell'archivio LocalMachine per i servizi ospitati su IIS.</span><span class="sxs-lookup"><span data-stu-id="0271d-157">The certificate is stored in the LocalMachine store for the IIS-hosted services.</span></span> <span data-ttu-id="0271d-158">Per i servizi indipendenti, è necessario modificare il file batch per archiviare il certificato server nel percorso dell'archivio CurrentUser sostituendo la stringa LocalMachine con CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="0271d-158">For self-hosted services, you should modify the batch file to store the server certificate in the CurrentUser store location by replacing the string LocalMachine with CurrentUser.</span></span>

```console
echo ************
echo Server cert setup starting
echo %SERVER_NAME%
echo ************
echo making server cert
echo ************
makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
```

### <a name="installing-server-certificate-into-clients-trusted-certificate-store"></a><span data-ttu-id="0271d-159">Installazione del certificato server nell'archivio certificati attendibili del client:</span><span class="sxs-lookup"><span data-stu-id="0271d-159">Installing Server Certificate into Client's Trusted Certificate Store</span></span>
 <span data-ttu-id="0271d-160">Le righe seguenti nel file batch Setup.bat copiano il certificato server nell'archivio di persone attendibile del client.</span><span class="sxs-lookup"><span data-stu-id="0271d-160">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="0271d-161">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="0271d-161">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="0271d-162">Se è già disponibile un certificato con radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il passaggio del popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="0271d-162">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

```console
echo ************
echo copying server cert to client's TrustedPeople store
echo ************certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
```

### <a name="enabling-access-to-the-certificates-private-key"></a><span data-ttu-id="0271d-163">Abilitare l'accesso alla chiave privata del certificato</span><span class="sxs-lookup"><span data-stu-id="0271d-163">Enabling Access to the Certificate's Private Key</span></span>
 <span data-ttu-id="0271d-164">Per abilitare l'accesso alla chiave privata del certificato dal servizio ospitato su IIS, è necessario concedere le autorizzazioni alla chiave privata appropriate all'account utente con cui viene eseguito il processo ospitato da IIS.</span><span class="sxs-lookup"><span data-stu-id="0271d-164">To enable access to the certificate private key from the IIS-hosted service, the user account under which the IIS-hosted process is running must be granted appropriate permissions for the private key.</span></span> <span data-ttu-id="0271d-165">Questa operazione viene eseguita negli ultimi passaggi dello script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="0271d-165">This is accomplished by last steps in the Setup.bat script.</span></span>

```console
echo ************
echo setting privileges on server certificates
echo ************
for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i
set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE
(ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET
echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R
iisreset
```

##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0271d-166">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="0271d-166">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="0271d-167">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0271d-167">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="0271d-168">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0271d-168">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="0271d-169">Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="0271d-169">To run the sample in a single- or cross-machine configuration, use the following instructions.</span></span>

##### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="0271d-170">Per eseguire l'esempio sullo stesso computer</span><span class="sxs-lookup"><span data-stu-id="0271d-170">To run the sample on the same machine</span></span>

1. <span data-ttu-id="0271d-171">Eseguire Setup. bat dalla cartella di installazione dell'esempio all'interno di un prompt dei comandi di Visual Studio 2012 eseguire con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0271d-171">Run Setup.bat from the sample install folder inside a Visual Studio 2012 command prompt run with administrator privileges.</span></span> <span data-ttu-id="0271d-172">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="0271d-172">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0271d-173">Il file batch Setup. bat è progettato per essere eseguito da un prompt dei comandi di Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="0271d-173">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="0271d-174">La variabile di ambiente PATH impostata nel prompt dei comandi di Visual Studio 2012 punta alla directory che contiene i file eseguibili richiesti dallo script Setup. bat.</span><span class="sxs-lookup"><span data-stu-id="0271d-174">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span> <span data-ttu-id="0271d-175">Assicurarsi di rimuovere i certificati eseguendo Cleanup.bat una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="0271d-175">Be sure to remove the certificates by running Cleanup.bat when finished with the sample.</span></span> <span data-ttu-id="0271d-176">Negli altri esempi relativi alla sicurezza vengono usati gli stessi certificati.</span><span class="sxs-lookup"><span data-stu-id="0271d-176">Other security samples use the same certificates.</span></span>  
  
2. <span data-ttu-id="0271d-177">Avviare Client.exe da \client\bin.</span><span class="sxs-lookup"><span data-stu-id="0271d-177">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="0271d-178">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="0271d-178">Client activity is displayed on the client console application.</span></span>  
  
3. <span data-ttu-id="0271d-179">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0271d-179">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
##### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="0271d-180">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="0271d-180">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="0271d-181">Creare una directory sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="0271d-181">Create a directory on the service machine.</span></span> <span data-ttu-id="0271d-182">Crea un'applicazione virtuale denominata servicemodelsamples per questa directory utilizzando lo strumento di gestione di Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="0271d-182">Create a virtual application named servicemodelsamples for this directory using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="0271d-183">Copiare i file del programma del servizio da \inetpub\wwwroot\servicemodelsamples alla directory virtuale sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="0271d-183">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service machine.</span></span> <span data-ttu-id="0271d-184">Assicurarsi di copiare i file nella sottodirectory \bin</span><span class="sxs-lookup"><span data-stu-id="0271d-184">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="0271d-185">Copiare anche i file Setup.bat, Cleanup.bat e ImportClientCert.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="0271d-185">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service machine.</span></span>  
  
3. <span data-ttu-id="0271d-186">Creare una directory sul client del servizio per i file binari del client.</span><span class="sxs-lookup"><span data-stu-id="0271d-186">Create a directory on the client machine for the client binaries.</span></span>  
  
4. <span data-ttu-id="0271d-187">Copiare i file di programma del client nella directory del client sul computer del client</span><span class="sxs-lookup"><span data-stu-id="0271d-187">Copy the client program files to the client directory on the client machine.</span></span> <span data-ttu-id="0271d-188">e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.</span><span class="sxs-lookup"><span data-stu-id="0271d-188">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="0271d-189">Sul server, eseguire `setup.bat service` in un prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0271d-189">On the server, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="0271d-190">Quando `setup.bat` si esegue con l' `service` argomento viene creato un certificato del servizio con il nome di dominio completo del computer e il certificato del servizio viene esportato in un file denominato Service. cer.</span><span class="sxs-lookup"><span data-stu-id="0271d-190">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="0271d-191">Modificare Web. config per riflettere il nuovo nome del certificato (nell' `findValue` attributo in [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ) che corrisponde al nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="0271d-191">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the machine.</span></span>  
  
7. <span data-ttu-id="0271d-192">Copiare il file Service.cer dalla directory del servizio alla directory del client sul computer client.</span><span class="sxs-lookup"><span data-stu-id="0271d-192">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
8. <span data-ttu-id="0271d-193">Sul client, eseguire `setup.bat client` in un prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0271d-193">On the client, run `setup.bat client` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="0271d-194">Quando si esegue `setup.bat` con l'argomento `client` viene creato un certificato client denominato client.com che viene esportato in un file denominato Client.cer.</span><span class="sxs-lookup"><span data-stu-id="0271d-194">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="0271d-195">Nel file Client.exe.config nel computer client, modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="0271d-195">In the Client.exe.config file on the client machine, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="0271d-196">Tale operazione viene eseguita sostituendo localhost con il nome di dominio completo del server.</span><span class="sxs-lookup"><span data-stu-id="0271d-196">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="0271d-197">Copiare il file Client.cer dalla directory del client nella directory del servizio sul server.</span><span class="sxs-lookup"><span data-stu-id="0271d-197">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="0271d-198">Nel client, eseguire ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="0271d-198">On the client, run ImportServiceCert.bat.</span></span> <span data-ttu-id="0271d-199">In questo modo viene importato il certificato del servizio dal file Service.cer nell'archivio CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="0271d-199">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="0271d-200">Eseguire sul server ImportClientCert.bat. In questo modo il certificato client viene importato dal file Client.cer nell'archivio LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="0271d-200">On the server, run ImportClientCert.bat, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="0271d-201">Sul computer client, avviare Client.exe da una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="0271d-201">On the client machine, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="0271d-202">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0271d-202">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
##### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="0271d-203">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="0271d-203">To clean up after the sample</span></span>  
  
- <span data-ttu-id="0271d-204">Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="0271d-204">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0271d-205">Questo script non rimuove i certificati del servizio su un client quando si esegue questo esempio tra più computer.</span><span class="sxs-lookup"><span data-stu-id="0271d-205">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="0271d-206">Se sono stati eseguiti esempi WCF che usano certificati tra computer, assicurarsi di cancellare i certificati del servizio installati nell'archivio CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="0271d-206">If you have run WCF samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="0271d-207">Per eseguire questa operazione, usare il seguente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="0271d-207">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
