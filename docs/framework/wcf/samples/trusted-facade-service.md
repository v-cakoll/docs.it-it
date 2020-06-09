---
title: Servizio facciata attendibile
ms.date: 03/30/2017
ms.assetid: c34d1a8f-e45e-440b-a201-d143abdbac38
ms.openlocfilehash: e7aa5e96fb8104c8140a8cebc6be45d2000821aa
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591319"
---
# <a name="trusted-facade-service"></a><span data-ttu-id="72227-102">Servizio facciata attendibile</span><span class="sxs-lookup"><span data-stu-id="72227-102">Trusted Facade Service</span></span>
<span data-ttu-id="72227-103">In questo scenario di esempio viene illustrato come eseguire il flusso delle informazioni di identità del chiamante da un servizio a un altro utilizzando l'infrastruttura di sicurezza Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="72227-103">This scenario sample demonstrates how to flow caller's identity information from one service to another using Windows Communication Foundation (WCF) security infrastructure.</span></span>  
  
 <span data-ttu-id="72227-104">Si tratta di un modello di progettazione comune per esporre la funzionalità fornita da un servizio alla rete pubblica usando un servizio di facciata.</span><span class="sxs-lookup"><span data-stu-id="72227-104">It is a common design pattern to expose the functionality provided by a service to the public network using a façade service.</span></span> <span data-ttu-id="72227-105">Il servizio di facciata risiede in genere nella rete perimetrale e comunica con un servizio back-end che implementa la regola business e ha accesso ai dati interni.</span><span class="sxs-lookup"><span data-stu-id="72227-105">The façade service typically resides in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet) and communicates with a backend service that implements the business logic and has access to internal data.</span></span> <span data-ttu-id="72227-106">Il canale di comunicazione tra il servizio di facciata e il servizio back-end passa attraverso un firewall e in genere è limitato a un solo obiettivo.</span><span class="sxs-lookup"><span data-stu-id="72227-106">The communication channel between the façade service and the backend service goes through a firewall and is usually limited for a single purpose only.</span></span>  
  
 <span data-ttu-id="72227-107">L'esempio è costituito dai componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="72227-107">This sample consists of the following components:</span></span>  
  
- <span data-ttu-id="72227-108">Client calcolatrice</span><span class="sxs-lookup"><span data-stu-id="72227-108">Calculator client</span></span>  
  
- <span data-ttu-id="72227-109">Servizio di facciata calcolatrice</span><span class="sxs-lookup"><span data-stu-id="72227-109">Calculator façade service</span></span>  
  
- <span data-ttu-id="72227-110">Servizio back-end calcolatrice</span><span class="sxs-lookup"><span data-stu-id="72227-110">Calculator backend service</span></span>  
  
 <span data-ttu-id="72227-111">Il servizio di facciata ha la responsabilità di convalidare la richiesta e autenticare il chiamante.</span><span class="sxs-lookup"><span data-stu-id="72227-111">The façade service is responsible for validating the request and authenticating the caller.</span></span> <span data-ttu-id="72227-112">Una volta completate correttamente l'autenticazione e la convalida, inoltra la richiesta al servizio back-end usando il canale di comunicazione controllato dalla rete perimetrale alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="72227-112">After successful authentication and validation, it forwards the request to the backend service using the controlled communication channel from the perimeter network to the internal network.</span></span> <span data-ttu-id="72227-113">I servizio di facciata include come parte della richiesta inoltrata informazioni sull'identità del chiamante, in modo che il servizio back-end possa usare queste informazioni nell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="72227-113">As a part of the forwarded request, the façade service includes information about the caller's identity so that the backend service can use this information in its processing.</span></span> <span data-ttu-id="72227-114">L'identità del chiamante viene trasmessa usando un token di sicurezza `Username` all'interno dell'intestazione di `Security` del messaggio.</span><span class="sxs-lookup"><span data-stu-id="72227-114">The caller's identity is transmitted using a `Username` security token inside the message `Security` header.</span></span> <span data-ttu-id="72227-115">Nell'esempio viene utilizzata l'infrastruttura di sicurezza WCF per trasmettere ed estrarre queste informazioni dall' `Security` intestazione.</span><span class="sxs-lookup"><span data-stu-id="72227-115">The sample uses the WCF security infrastructure to transmit and extract this information from the `Security` header.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="72227-116">Il servizio back-end considera attendibile il servizio di facciata per autenticare il chiamante.</span><span class="sxs-lookup"><span data-stu-id="72227-116">The backend service trusts the façade service to authenticate the caller.</span></span> <span data-ttu-id="72227-117">Di conseguenza il servizio back-end non autentica nuovamente il chiamante, ma usa le informazioni di identità fornite dal servizio di facciata nella richiesta inoltrata.</span><span class="sxs-lookup"><span data-stu-id="72227-117">Because of this, the backend service does not authenticate the caller again; it uses the identity information provided by the façade service in the forwarded request.</span></span> <span data-ttu-id="72227-118">A causa di questa relazione di trust, il servizio back-end deve autenticare il servizio di facciata in modo da assicurare che il messaggio inoltrato provenga da una fonte attendibile, in questo caso, dal servizio di facciata.</span><span class="sxs-lookup"><span data-stu-id="72227-118">Because of this trust relationship, the backend service must authenticate the façade service to ensure that the forwarded message comes from a trusted source - in this case, the façade service.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="72227-119">Implementazione</span><span class="sxs-lookup"><span data-stu-id="72227-119">Implementation</span></span>  
 <span data-ttu-id="72227-120">In questo esempio vengono riportati due percorsi di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="72227-120">There are two communication paths in this sample.</span></span> <span data-ttu-id="72227-121">Il primo è tra il client e il servizio di facciata, il secondo è tra il servizio di facciata e il servizio back-end.</span><span class="sxs-lookup"><span data-stu-id="72227-121">First is between the client and the façade service, the second is between the façade service and the backend service.</span></span>  
  
### <a name="communication-path-between-client-and-faade-service"></a><span data-ttu-id="72227-122">Percorso di comunicazione tra il client e il servizio di facciata</span><span class="sxs-lookup"><span data-stu-id="72227-122">Communication Path between Client and Façade Service</span></span>  
 <span data-ttu-id="72227-123">Il percorso di comunicazione dal client al servizio di facciata usa `wsHttpBinding` con un tipo di credenziale `UserName` .</span><span class="sxs-lookup"><span data-stu-id="72227-123">The client to the façade service communication path uses `wsHttpBinding` with a `UserName` client credential type.</span></span> <span data-ttu-id="72227-124">Questo significa che il client usa il nome utente e la password per autenticare al servizio di facciata e il servizio di facciata usa il certificato X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="72227-124">This means that the client uses username and password to authenticate to the façade service and the façade service uses X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="72227-125">L'aspetto della configurazione dell'associazione è analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="72227-125">The binding configuration looks like the following example.</span></span>  
  
```xml  
<bindings>  
  <wsHttpBinding>  
    <binding name="Binding1">  
      <security mode="Message">  
        <message clientCredentialType="UserName"/>  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="72227-126">Il servizio di facciata autentica il chiamante usando l'implementazione `UserNamePasswordValidator` personalizzata.</span><span class="sxs-lookup"><span data-stu-id="72227-126">The façade service authenticates the caller using custom `UserNamePasswordValidator` implementation.</span></span> <span data-ttu-id="72227-127">A scopo dimostrativo, l'autenticazione assicura solo che il nome utente del chiamante corrisponda alla password presentata.</span><span class="sxs-lookup"><span data-stu-id="72227-127">For demonstration purposes, the authentication only ensures that the caller's username matches the presented password.</span></span> <span data-ttu-id="72227-128">Nella situazione del mondo reale l'utente viene probabilmente autenticato usando Active Directory o un provider di appartenenze ASP.NET personalizzato.</span><span class="sxs-lookup"><span data-stu-id="72227-128">In the real world situation, the user is probably authenticated using Active Directory or custom ASP.NET Membership provider.</span></span> <span data-ttu-id="72227-129">L'implementazione del validator si trova nel file `FacadeService.cs` .</span><span class="sxs-lookup"><span data-stu-id="72227-129">The validator implementation resides in `FacadeService.cs` file.</span></span>  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // check that username matches password  
        if (null == userName || userName != password)  
        {  
            Console.WriteLine("Invalid username or password");  
            throw new SecurityTokenValidationException(  
                       "Invalid username or password");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="72227-130">Il validator personalizzato viene configurato per essere usato nel comportamento `serviceCredentials` nel file di configurazione del servizio di facciata.</span><span class="sxs-lookup"><span data-stu-id="72227-130">The custom validator is configured to be used inside the `serviceCredentials` behavior in the façade service configuration file.</span></span> <span data-ttu-id="72227-131">Questo comportamento viene inoltre usato per configurare il certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="72227-131">This behavior is also used to configure the service's X.509 certificate.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="FacadeServiceBehavior">  
      <!--The serviceCredentials behavior allows you to define -->  
      <!--a service certificate. -->  
      <!--A service certificate is used by the service to  -->  
      <!--authenticate itself to its clients and to provide  -->  
      <!--message protection. -->  
      <!--This configuration references the "localhost"  -->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate
               findValue="localhost"
               storeLocation="LocalMachine"
               storeName="My"
               x509FindType="FindBySubjectName" />  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
            customUserNamePasswordValidatorType=  
           "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,  
            FacadeService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
### <a name="communication-path-between-faade-service-and-backend-service"></a><span data-ttu-id="72227-132">Percorso di comunicazione tra il servizio di facciata e il servizio back-end</span><span class="sxs-lookup"><span data-stu-id="72227-132">Communication Path between Façade Service and Backend Service</span></span>  
 <span data-ttu-id="72227-133">Il percorso di comunicazione dal servizio di facciata al servizio back-end usa un `customBinding` costituito da molti elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="72227-133">The façade service to the backend service communication path uses a `customBinding` that consists of several binding elements.</span></span> <span data-ttu-id="72227-134">Questa associazione consente di raggiungere due obiettivi.</span><span class="sxs-lookup"><span data-stu-id="72227-134">This binding accomplishes two things.</span></span> <span data-ttu-id="72227-135">Autentica il servizio di facciata e il servizio back-end per assicurare che la comunicazione sia protetta e che provenga da una fonte attendibile.</span><span class="sxs-lookup"><span data-stu-id="72227-135">It authenticates the façade service and backend service to ensure that the communication is secure and is coming from a trusted source.</span></span> <span data-ttu-id="72227-136">Trasmette inoltre l'identità del chiamante iniziale all'interno del token di sicurezza `Username` .</span><span class="sxs-lookup"><span data-stu-id="72227-136">Additionally, it also transmits the initial caller's identity inside the `Username` security token.</span></span> <span data-ttu-id="72227-137">In questo caso, solo il nome utente del chiamante iniziale viene trasmesso al servizio back-end, la password non viene inclusa nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="72227-137">In this case, only the initial caller's username is transmitted to the backend service, the password is not included in the message.</span></span> <span data-ttu-id="72227-138">Questo è dovuto al fatto che il servizio back-end considera attendibile il servizio di facciata per autenticare il chiamante prima di inoltrargli la richiesta.</span><span class="sxs-lookup"><span data-stu-id="72227-138">This is because the backend service trusts the façade service to authenticate the caller before forwarding the request to it.</span></span> <span data-ttu-id="72227-139">Poiché il servizio di facciata si autentica con il servizio back-end, il servizio back-end può considerare le informazioni contenute nella richiesta inoltrata attendibili.</span><span class="sxs-lookup"><span data-stu-id="72227-139">Because the façade service authenticates itself to the backend service, the backend service can trust the information contained in the forwarded request.</span></span>  
  
 <span data-ttu-id="72227-140">Di seguito è riportata la configurazione di associazione per questo percorso di comunicazione.</span><span class="sxs-lookup"><span data-stu-id="72227-140">The following is the binding configuration for this communication path.</span></span>  
  
```xml  
<bindings>  
  <customBinding>  
    <binding name="ClientBinding">  
      <security authenticationMode="UserNameOverTransport"/>  
      <windowsStreamSecurity/>  
      <tcpTransport/>  
    </binding>  
  </customBinding>  
</bindings>  
```  
  
 <span data-ttu-id="72227-141">L' [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento di associazione si occupa della trasmissione e dell'estrazione del nome utente del chiamante iniziale.</span><span class="sxs-lookup"><span data-stu-id="72227-141">The [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) binding element takes care of the initial caller's username transmission and extraction.</span></span> <span data-ttu-id="72227-142">E si occupano [\<windowsStreamSecurity>](../../configure-apps/file-schema/wcf/windowsstreamsecurity.md) [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) dell'autenticazione dei servizi di facciata e back-end e della protezione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="72227-142">The [\<windowsStreamSecurity>](../../configure-apps/file-schema/wcf/windowsstreamsecurity.md) and [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) take care of authenticating façade and backend services and message protection.</span></span>  
  
 <span data-ttu-id="72227-143">Per inviare la richiesta, l'implementazione del servizio di facciata deve fornire il nome utente del chiamante iniziale, in modo che l'infrastruttura di sicurezza di WCF possa inserire questo oggetto nel messaggio trasmesso.</span><span class="sxs-lookup"><span data-stu-id="72227-143">To forward the request, the façade service implementation must provide the initial caller's username so that WCF security infrastructure can place this into the forwarded message.</span></span> <span data-ttu-id="72227-144">Il nome utente del chiamante iniziale viene fornito nell'implementazione del servizio di facciata impostandolo nella proprietà `ClientCredentials` sull'istanza del proxy client che il servizio di facciata usa per comunicare con il servizio back-end.</span><span class="sxs-lookup"><span data-stu-id="72227-144">The initial caller's username is provided in the façade service implementation by setting it in the `ClientCredentials` property on the client proxy instance that façade service uses to communicate with the backend service.</span></span>  
  
 <span data-ttu-id="72227-145">Nel codice seguente viene illustrata l'implementazione del metodo `GetCallerIdentity` nel servizio di facciata.</span><span class="sxs-lookup"><span data-stu-id="72227-145">The following code shows how `GetCallerIdentity` method is implemented on the façade service.</span></span> <span data-ttu-id="72227-146">Gli altri metodi usano lo stesso modello.</span><span class="sxs-lookup"><span data-stu-id="72227-146">Other methods use the same pattern.</span></span>  
  
```csharp  
public string GetCallerIdentity()  
{  
    CalculatorClient client = new CalculatorClient();  
    client.ClientCredentials.UserName.UserName = ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    string result = client.GetCallerIdentity();  
    client.Close();  
    return result;  
}  
```  
  
 <span data-ttu-id="72227-147">Come illustrato nel codice precedente, la password non viene impostata nella proprietà `ClientCredentials` . Viene impostato solo il nome utente.</span><span class="sxs-lookup"><span data-stu-id="72227-147">As shown in the previous code, the password is not set on the `ClientCredentials` property, only the username is set.</span></span> <span data-ttu-id="72227-148">L'infrastruttura di sicurezza di WCF crea un token di sicurezza del nome utente senza una password in questo caso, che è esattamente ciò che è necessario in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="72227-148">WCF security infrastructure creates a username security token without a password in this case, which is exactly what is required in this scenario.</span></span>  
  
 <span data-ttu-id="72227-149">Nel servizio back-end, le informazioni contenute nel token di sicurezza del nome utente devono essere autenticate.</span><span class="sxs-lookup"><span data-stu-id="72227-149">On the backend service, the information contained in the username security token must be authenticated.</span></span> <span data-ttu-id="72227-150">Per impostazione predefinita, la sicurezza WCF tenta di eseguire il mapping dell'utente a un account di Windows usando la password fornita.</span><span class="sxs-lookup"><span data-stu-id="72227-150">By default, WCF security attempts to map the user to a Windows account using the provided password.</span></span> <span data-ttu-id="72227-151">In questo caso non è stata fornita una password e non è necessario che il servizio back-end autentichi il nome utente, visto che l'autenticazione è già stata eseguita dal servizio di facciata.</span><span class="sxs-lookup"><span data-stu-id="72227-151">In this case, there is no password provided and the backend service is not required to authenticate the username because the authentication was already performed by the façade service.</span></span> <span data-ttu-id="72227-152">Per implementare questa funzionalità in WCF, `UserNamePasswordValidator` viene fornito un personalizzato che impone solo che venga specificato un nome utente nel token e non esegua alcuna autenticazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="72227-152">To implement this functionality in WCF, a custom `UserNamePasswordValidator` is provided that only enforces that a username is specified in the token and does not perform any additional authentication.</span></span>  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // Ignore the password because it is empty,
        // we trust the facade service to authenticate the client.  
        // Accept the username information here so that the
        // application gets access to it.  
        if (null == userName)  
        {  
            Console.WriteLine("Invalid username");  
            throw new
             SecurityTokenValidationException("Invalid username");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="72227-153">Il validator personalizzato viene configurato per essere usato nel comportamento `serviceCredentials` nel file di configurazione del servizio di facciata.</span><span class="sxs-lookup"><span data-stu-id="72227-153">The custom validator is configured to be used inside the `serviceCredentials` behavior in the façade service configuration file.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="BackendServiceBehavior">  
      <serviceCredentials>  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
           customUserNamePasswordValidatorType=  
          "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,
           BackendService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="72227-154">Per estrarre le informazioni relative al nome utente e all'account del servizio di facciata attendibile, l'implementazione del servizio back-end usa la classe `ServiceSecurityContext` .</span><span class="sxs-lookup"><span data-stu-id="72227-154">To extract the username information and information about the trusted façade service account, the backend service implementation uses the `ServiceSecurityContext` class.</span></span> <span data-ttu-id="72227-155">Nel codice seguente viene illustrato come implementare il metodo `GetCallerIdentity` .</span><span class="sxs-lookup"><span data-stu-id="72227-155">The following code shows how the `GetCallerIdentity` method is implemented.</span></span>  
  
```csharp  
public string GetCallerIdentity()  
{  
    // Facade service is authenticated using Windows authentication.  
    //Its identity is accessible.  
    // On ServiceSecurityContext.Current.WindowsIdentity.  
    string facadeServiceIdentityName =
          ServiceSecurityContext.Current.WindowsIdentity.Name;  
  
    // The client name is transmitted using Username authentication on
    //the message level without the password  
    // using a supporting encrypted UserNameToken.  
    // Claims extracted from this supporting token are available in
    // ServiceSecurityContext.Current.AuthorizationContext.ClaimSets
    // collection.  
    string clientName = null;  
    foreach (ClaimSet claimSet in
        ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)  
    {  
        foreach (Claim claim in claimSet)  
        {  
            if (claim.ClaimType == ClaimTypes.Name &&
                                   claim.Right == Rights.Identity)  
            {  
                clientName = (string)claim.Resource;  
                break;  
            }  
        }  
    }  
    if (clientName == null)  
    {  
        // In case there was no UserNameToken attached to the request.  
        // In the real world implementation the service should reject
        // this request.  
        return "Anonymous caller via " + facadeServiceIdentityName;  
    }  
  
    return clientName + " via " + facadeServiceIdentityName;  
}  
```  
  
 <span data-ttu-id="72227-156">Le informazioni relative all'account del servizio di facciata vengono estratte usando la proprietà `ServiceSecurityContext.Current.WindowsIdentity` .</span><span class="sxs-lookup"><span data-stu-id="72227-156">The façade service account information is extracted using the `ServiceSecurityContext.Current.WindowsIdentity` property.</span></span> <span data-ttu-id="72227-157">Per accedere alle informazioni relative al chiamante iniziale, il servizio back-end usa la proprietà `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` .</span><span class="sxs-lookup"><span data-stu-id="72227-157">To access the information about the initial caller the backend service uses the `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` property.</span></span> <span data-ttu-id="72227-158">Cerca un'attestazione di `Identity` di tipo `Name`.</span><span class="sxs-lookup"><span data-stu-id="72227-158">It looks for an `Identity` claim with a type `Name`.</span></span> <span data-ttu-id="72227-159">Questa attestazione viene generata automaticamente dall'infrastruttura di sicurezza WCF dalle informazioni contenute nel `Username` token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="72227-159">This claim is automatically generated by WCF security infrastructure from the information contained in the `Username` security token.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="72227-160">Esecuzione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="72227-160">Running the sample</span></span>  
 <span data-ttu-id="72227-161">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="72227-161">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="72227-162">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="72227-162">Press ENTER in the client window to shut down the client.</span></span> <span data-ttu-id="72227-163">È possibile premere INVIO nelle finestre della console del servizio di facciata e del servizio back-end per arrestare i servizi.</span><span class="sxs-lookup"><span data-stu-id="72227-163">You can press ENTER in the façade and backend service console windows to shut down the services.</span></span>  
  
```console  
Username authentication required.  
Provide a valid machine or domain ac  
   Enter username:  
user  
   Enter password:  
****  
user via MyMachine\testaccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="72227-164">Il file batch Setup.bat incluso nell'esempio relativo allo scenario della Facciata attendibile consente di configurare il server con un certificato attinente per eseguire il servizio di facciata che richiede sicurezza server basata su certificato per autenticarsi sul client.</span><span class="sxs-lookup"><span data-stu-id="72227-164">The Setup.bat batch file included with the Trusted Facade scenario sample enables you to configure the server with a relevant certificate to run the façade service that requires certificate-based security to authenticate itself to the client.</span></span> <span data-ttu-id="72227-165">Per altre informazioni, vedere la procedura di configurazione alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="72227-165">See the setup procedure at the end of this topic for details.</span></span>  
  
 <span data-ttu-id="72227-166">Di seguito viene presentata una breve panoramica delle diverse sezioni dei file batch.</span><span class="sxs-lookup"><span data-stu-id="72227-166">The following provides a brief overview of the different sections of the batch files.</span></span>  
  
- <span data-ttu-id="72227-167">Creazione del certificato server.</span><span class="sxs-lookup"><span data-stu-id="72227-167">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="72227-168">Le righe seguenti del file batch Setup.bat creano il certificato server da usare.</span><span class="sxs-lookup"><span data-stu-id="72227-168">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```console  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="72227-169">La variabile `%SERVER_NAME%` specifica il nome del server. Il valore predefinito è localhost.</span><span class="sxs-lookup"><span data-stu-id="72227-169">The `%SERVER_NAME%` variable specifies the server name - the default value is localhost.</span></span> <span data-ttu-id="72227-170">Il certificato viene archiviato nell'archivio LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="72227-170">The certificate is stored in the LocalMachine store.</span></span>  
  
- <span data-ttu-id="72227-171">Installazione del servizio di facciata nell'archivio certificati attendibili del client.</span><span class="sxs-lookup"><span data-stu-id="72227-171">Installing the façade service's certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="72227-172">La riga seguente copia il servizio di facciata nell'archivio Persone attendibili del client.</span><span class="sxs-lookup"><span data-stu-id="72227-172">The following line copies the façade service's certificate into the client trusted people store.</span></span> <span data-ttu-id="72227-173">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="72227-173">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="72227-174">Se è già disponibile un certificato impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="72227-174">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```console  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="72227-175">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="72227-175">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="72227-176">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="72227-176">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="72227-177">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="72227-177">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="72227-178">Per eseguire l'esempio sullo stesso computer</span><span class="sxs-lookup"><span data-stu-id="72227-178">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="72227-179">Assicurarsi che il percorso includa la cartella in cui è situato Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="72227-179">Ensure that the path includes the folder where Makecert.exe is located.</span></span>  
  
2. <span data-ttu-id="72227-180">Eseguire Setup.bat dalla cartella di installazione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="72227-180">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="72227-181">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="72227-181">This installs all the certificates required for running the sample.</span></span>  
  
3. <span data-ttu-id="72227-182">Avviare BackendService.exe dalla directory \BackendService\bin in una finestra della console separata</span><span class="sxs-lookup"><span data-stu-id="72227-182">Launch the BackendService.exe from \BackendService\bin directory in a separate console window</span></span>  
  
4. <span data-ttu-id="72227-183">Avviare FacadeService.exe dalla directory \FacadeService\bin in una finestra della console separata</span><span class="sxs-lookup"><span data-stu-id="72227-183">Launch the FacadeService.exe from \FacadeService\bin directory in a separate console window</span></span>  
  
5. <span data-ttu-id="72227-184">Avviare Client.exe da \client\bin.</span><span class="sxs-lookup"><span data-stu-id="72227-184">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="72227-185">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="72227-185">Client activity is displayed on the client console application.</span></span>  
  
6. <span data-ttu-id="72227-186">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="72227-186">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="72227-187">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="72227-187">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="72227-188">Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="72227-188">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="72227-189">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="72227-189">The samples may already be installed on your machine.</span></span> <span data-ttu-id="72227-190">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="72227-190">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="72227-191">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="72227-191">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="72227-192">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="72227-192">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\TrustedFacade`  
