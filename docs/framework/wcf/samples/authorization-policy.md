---
title: Criteri di autorizzazione
ms.date: 03/30/2017
ms.assetid: 1db325ec-85be-47d0-8b6e-3ba2fdf3dda0
ms.openlocfilehash: 5b93f7e05261d9770650335160ddb56404aed94d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585506"
---
# <a name="authorization-policy"></a><span data-ttu-id="4af6e-102">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4af6e-102">Authorization Policy</span></span>

<span data-ttu-id="4af6e-103">In questo esempio viene illustrato come implementare i criteri di autorizzazione dell'attestazione personalizzati e un gestore autorizzazioni personalizzato del servizio associato.</span><span class="sxs-lookup"><span data-stu-id="4af6e-103">This sample demonstrates how to implement a custom claim authorization policy and an associated custom service authorization manager.</span></span> <span data-ttu-id="4af6e-104">Questa procedura è utile quando il servizio esegue i controlli di accesso basati sull'attestazione nelle operazioni del servizio e prima dei controlli di accesso, concede al chiamante alcuni diritti.</span><span class="sxs-lookup"><span data-stu-id="4af6e-104">This is useful when the service makes claim-based access checks to service operations and prior to the access checks, grants the caller certain rights.</span></span> <span data-ttu-id="4af6e-105">In questo esempio viene illustrato sia il processo di aggiunta delle attestazioni che il processo di controllo dell'accesso a fronte del set finalizzato di attestazioni.</span><span class="sxs-lookup"><span data-stu-id="4af6e-105">This sample shows both the process of adding claims as well as the process for doing an access check against the finalized set of claims.</span></span> <span data-ttu-id="4af6e-106">Tutti i messaggi dell'applicazione tra il client e il server vengono firmati e crittografati.</span><span class="sxs-lookup"><span data-stu-id="4af6e-106">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="4af6e-107">Per impostazione predefinita, con l'associazione `wsHttpBinding` vengono utilizzati un nome utente e una password forniti dal client per accedere con un account Windows NT valido.</span><span class="sxs-lookup"><span data-stu-id="4af6e-107">By default with the `wsHttpBinding` binding, a username and password supplied by the client are used to logon to a valid Windows NT account.</span></span> <span data-ttu-id="4af6e-108">In questo esempio viene illustrato come utilizzare un <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> personalizzato per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="4af6e-108">This sample demonstrates how to utilize a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> to authenticate the client.</span></span> <span data-ttu-id="4af6e-109">Viene inoltre illustrata l'autenticazione del client nel servizio tramite un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="4af6e-109">In addition this sample shows the client authenticating to the service using an X.509 certificate.</span></span> <span data-ttu-id="4af6e-110">In questo esempio viene illustrata un'implementazione di <xref:System.IdentityModel.Policy.IAuthorizationPolicy> e <xref:System.ServiceModel.ServiceAuthorizationManager> che, insieme, concedono l'accesso a metodi specifici del servizio per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="4af6e-110">This sample shows an implementation of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and <xref:System.ServiceModel.ServiceAuthorizationManager>, which between them grant access to specific methods of the service for specific users.</span></span> <span data-ttu-id="4af6e-111">Questo esempio si basa sul [nome utente di sicurezza del messaggio](message-security-user-name.md), ma illustra come eseguire una trasformazione attestazione prima che <xref:System.ServiceModel.ServiceAuthorizationManager> venga chiamato.</span><span class="sxs-lookup"><span data-stu-id="4af6e-111">This sample is based on the [Message Security User Name](message-security-user-name.md), but demonstrates how to perform a claim transformation prior to the <xref:System.ServiceModel.ServiceAuthorizationManager> being called.</span></span>

> [!NOTE]
> <span data-ttu-id="4af6e-112">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="4af6e-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="4af6e-113">In sintesi, nell'esempio viene illustrato in che modo eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4af6e-113">In summary, this sample demonstrates how:</span></span>

- <span data-ttu-id="4af6e-114">Il client può essere autenticato utilizzando un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="4af6e-114">The client can be authenticated using a user name-password.</span></span>

- <span data-ttu-id="4af6e-115">Il client può essere autenticato tramite un certificato X.509.</span><span class="sxs-lookup"><span data-stu-id="4af6e-115">The client can be authenticated using an X.509 certificate.</span></span>

- <span data-ttu-id="4af6e-116">Il server verifica le credenziali client rispetto a un validator `UsernamePassword` personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4af6e-116">The server validates the client credentials against a custom `UsernamePassword` validator.</span></span>

- <span data-ttu-id="4af6e-117">Il server viene autenticato tramite il certificato X.509 del server.</span><span class="sxs-lookup"><span data-stu-id="4af6e-117">The server is authenticated using the server's X.509 certificate.</span></span>

- <span data-ttu-id="4af6e-118">Il server può utilizzare <xref:System.ServiceModel.ServiceAuthorizationManager> per controllare l'accesso a determinati metodi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="4af6e-118">The server can use <xref:System.ServiceModel.ServiceAuthorizationManager> to control access to certain methods in the service.</span></span>

- <span data-ttu-id="4af6e-119">Come implementare <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span><span class="sxs-lookup"><span data-stu-id="4af6e-119">How to implement <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>

<span data-ttu-id="4af6e-120">Il servizio espone due endpoint per la comunicazione con il servizio, definito utilizzando il file di configurazione app. config. Ogni endpoint è costituito da un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="4af6e-120">The service exposes two endpoints for communicating with the service, defined using the configuration file App.config. Each endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="4af6e-121">Un'associazione è configurata con un'associazione `wsHttpBinding` standard che utilizza WS-Security e l'autenticazione del nome utente del client.</span><span class="sxs-lookup"><span data-stu-id="4af6e-121">One binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client username authentication.</span></span> <span data-ttu-id="4af6e-122">L'altra associazione è configurata con un'associazione `wsHttpBinding` standard che utilizza WS-Security e l'autenticazione del certificato client.</span><span class="sxs-lookup"><span data-stu-id="4af6e-122">The other binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client certificate authentication.</span></span> <span data-ttu-id="4af6e-123">[\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)Specifica che le credenziali utente devono essere utilizzate per l'autenticazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="4af6e-123">The [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) specifies that the user credentials are to be used for service authentication.</span></span> <span data-ttu-id="4af6e-124">Il certificato server deve contenere lo stesso valore per la `SubjectName` proprietà dell' `findValue` attributo in [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="4af6e-124">The server certificate must contain the same value for the `SubjectName` property as the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <!-- configure base address provided by host -->
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service"/>
        </baseAddresses>
      </host>
      <!-- use base address provided by host, provide two endpoints -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <endpoint address="certificate"
                binding="wsHttpBinding"
                bindingConfiguration="Binding2"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
    <message clientCredentialType="UserName" />
        </security>
      </binding>
      <!-- X509 certificate binding -->
      <binding name="Binding2">
        <security mode="Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior" >
        <serviceDebug includeExceptionDetailInFaults ="true" />
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to specify authentication constraints on client certificates.
          -->
          <clientCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
          <!--
          The serviceCredentials behavior allows one to define a service certificate.
          A service certificate is used by a client to authenticate the service and provide message protection.
          This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
        <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
          <!--
          The serviceAuthorization behavior allows one to specify custom authorization policies.
          -->
          <authorizationPolicies>
            <add policyType="Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary" />
          </authorizationPolicies>
        </serviceAuthorization>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

<span data-ttu-id="4af6e-125">Ogni configurazione dell'endpoint client è costituita da un nome di configurazione, un indirizzo assoluto per l'endpoint del servizio, l'associazione e il contratto.</span><span class="sxs-lookup"><span data-stu-id="4af6e-125">Each client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="4af6e-126">L'associazione client viene configurata con la modalità di sicurezza appropriata come specificato in questo caso in [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) e `clientCredentialType` come specificato in [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="4af6e-126">The client binding is configured with the appropriate security mode as specified in this case in the [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) and `clientCredentialType` as specified in the [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md).</span></span>

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
            address="http://localhost:8001/servicemodelsamples/service/username"
    binding="wsHttpBinding"
    bindingConfiguration="Binding1"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator" >
      </endpoint>
      <!-- X509 certificate based endpoint -->
      <endpoint name="Certificate"
                        address="http://localhost:8001/servicemodelsamples/service/certificate"
                binding="wsHttpBinding"
            bindingConfiguration="Binding2"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
        <!-- X509 certificate binding -->
        <binding name="Binding2">
          <security mode="Message">
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
    </wsHttpBinding>
    </bindings>

    <behaviors>
      <behavior name="ClientCertificateBehavior">
        <clientCredentials>
          <serviceCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust
            means that if the certificate
            is in the user's Trusted People store, then it will be
            trusted without performing a
            validation of the certificate's issuer chain. This setting
            is used here for convenience so that the
            sample can be run without having to have certificates
            issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust.
            The security implications of this
            setting should be carefully considered before using
            PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode = "PeerOrChainTrust" />
          </serviceCertificate>
        </clientCredentials>
      </behavior>
    </behaviors>

  </system.serviceModel>
```

<span data-ttu-id="4af6e-127">Per l'endpoint basato sul nome utente, l'implementazione client imposta il nome utente la e password da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4af6e-127">For the user name-based endpoint, the client implementation sets the user name and password to use.</span></span>

```csharp
// Create a client with Username endpoint configuration
CalculatorClient client1 = new CalculatorClient("Username");

client1.ClientCredentials.UserName.UserName = "test1";
client1.ClientCredentials.UserName.Password = "1tset";

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client1.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client1.Close();
```

<span data-ttu-id="4af6e-128">Per l'endpoint basato sul certificato, l'implementazione client imposta il certificato client da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4af6e-128">For the certificate-based endpoint, the client implementation sets the client certificate to use.</span></span>

```csharp
// Create a client with Certificate endpoint configuration
CalculatorClient client2 = new CalculatorClient("Certificate");

client2.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client2.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client2.Close();
```

<span data-ttu-id="4af6e-129">In questo esempio viene utilizzato un <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> personalizzato per convalidare i nomi utente e le password.</span><span class="sxs-lookup"><span data-stu-id="4af6e-129">This sample uses a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> to validate user names and passwords.</span></span> <span data-ttu-id="4af6e-130">Nell'esempio viene implementato `MyCustomUserNamePasswordValidator`, derivato da <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="4af6e-130">The sample implements `MyCustomUserNamePasswordValidator`, derived from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span> <span data-ttu-id="4af6e-131">Per ulteriori informazioni, vedere la documentazione relativa a <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="4af6e-131">See the documentation about <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> for more information.</span></span> <span data-ttu-id="4af6e-132">Allo scopo di illustrare l'integrazione con <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, in questo esempio di validator personalizzato viene implementato il metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> per accettare coppie di nome utente/password quando il nome utente corrisponde alla password come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="4af6e-132">For the purposes of demonstrating the integration with the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, this custom validator sample implements the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method to accept user name/password pairs where the user name matches the password as shown in the following code.</span></span>

```csharp
public class MyCustomUserNamePasswordValidator : UserNamePasswordValidator
{
  // This method validates users. It allows in two users,
  // test1 and test2 with passwords 1tset and 2tset respectively.
  // This code is for illustration purposes only and
  // MUST NOT be used in a production environment because it
  // is NOT secure.
  public override void Validate(string userName, string password)
  {
    if (null == userName || null == password)
    {
      throw new ArgumentNullException();
    }

    if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))
    {
      throw new SecurityTokenException("Unknown Username or Password");
    }
  }
}
```

<span data-ttu-id="4af6e-133">Quando il validator è stato implementato nel codice del servizio, l'host del servizio deve essere informato dell'istanza del validator da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4af6e-133">Once the validator is implemented in service code, the service host must be informed about the validator instance to use.</span></span> <span data-ttu-id="4af6e-134">Questa operazione viene eseguita usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4af6e-134">This is done using the following code:</span></span>

```csharp
Servicehost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials.UserNameAuthentication.CustomUserNamePasswordValidator = new MyCustomUserNamePasswordValidatorProvider();
```

<span data-ttu-id="4af6e-135">In alternativa, è possibile eseguire la stessa operazione nella configurazione:</span><span class="sxs-lookup"><span data-stu-id="4af6e-135">Or you can do the same thing in configuration:</span></span>

```xml
<behavior>
    <serviceCredentials>
      <!--
      The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
      -->
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
    ...
    </serviceCredentials>
</behavior>
```

<span data-ttu-id="4af6e-136">Windows Communication Foundation (WCF) fornisce un modello avanzato basato sulle attestazioni per l'esecuzione dei controlli di accesso.</span><span class="sxs-lookup"><span data-stu-id="4af6e-136">Windows Communication Foundation (WCF) provides a rich claims-based model for performing access checks.</span></span> <span data-ttu-id="4af6e-137">L'oggetto <xref:System.ServiceModel.ServiceAuthorizationManager> viene utilizzato per eseguire il controllo dell'accesso e determinare se le attestazioni associate al client soddisfano i requisiti necessari per accedere al metodo del servizio.</span><span class="sxs-lookup"><span data-stu-id="4af6e-137">The <xref:System.ServiceModel.ServiceAuthorizationManager> object is used to perform the access check and determine whether the claims associated with the client satisfy the requirements necessary to access the service method.</span></span>

<span data-ttu-id="4af6e-138">Ai fini della dimostrazione, in questo esempio viene illustrata un'implementazione di <xref:System.ServiceModel.ServiceAuthorizationManager> che implementa il <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> metodo per consentire a un utente l'accesso ai metodi in base alle attestazioni di tipo `http://example.com/claims/allowedoperation` il cui valore è l'URI di azione dell'operazione che può essere chiamata.</span><span class="sxs-lookup"><span data-stu-id="4af6e-138">For the purposes of demonstration, this sample shows an implementation of <xref:System.ServiceModel.ServiceAuthorizationManager> that implements the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method to allow a user's access to methods based on claims of type `http://example.com/claims/allowedoperation` whose value is the Action URI of the operation that is allowed to be called.</span></span>

```csharp
public class MyServiceAuthorizationManager : ServiceAuthorizationManager
{
  protected override bool CheckAccessCore(OperationContext operationContext)
  {
    string action = operationContext.RequestContext.RequestMessage.Headers.Action;
    Console.WriteLine("action: {0}", action);
    foreach(ClaimSet cs in operationContext.ServiceSecurityContext.AuthorizationContext.ClaimSets)
    {
      if ( cs.Issuer == ClaimSet.System )
      {
        foreach (Claim c in cs.FindClaims("http://example.com/claims/allowedoperation", Rights.PossessProperty))
        {
          Console.WriteLine("resource: {0}", c.Resource.ToString());
          if (action == c.Resource.ToString())
            return true;
        }
      }
    }
    return false;
  }
}
```

<span data-ttu-id="4af6e-139">Quando il <xref:System.ServiceModel.ServiceAuthorizationManager> personalizzato è stato implementato, l'host del servizio deve essere informato del <xref:System.ServiceModel.ServiceAuthorizationManager> da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4af6e-139">Once the custom <xref:System.ServiceModel.ServiceAuthorizationManager> is implemented, the service host must be informed about the <xref:System.ServiceModel.ServiceAuthorizationManager> to use.</span></span> <span data-ttu-id="4af6e-140">Questa operazione viene eseguita come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="4af6e-140">This is done as shown in the following code.</span></span>

```xml
<behavior>
    ...
    <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
        ...
    </serviceAuthorization>
</behavior>
```

<span data-ttu-id="4af6e-141">Il metodo <xref:System.IdentityModel.Policy.IAuthorizationPolicy> principale da implementare è il metodo <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29>.</span><span class="sxs-lookup"><span data-stu-id="4af6e-141">The primary <xref:System.IdentityModel.Policy.IAuthorizationPolicy> method to implement is the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method.</span></span>

```csharp
public class MyAuthorizationPolicy : IAuthorizationPolicy
{
    string id;

    public MyAuthorizationPolicy()
    {
    id =  Guid.NewGuid().ToString();
    }

    public bool Evaluate(EvaluationContext evaluationContext,
                                            ref object state)
    {
        bool bRet = false;
        CustomAuthState customstate = null;

        if (state == null)
        {
            customstate = new CustomAuthState();
            state = customstate;
        }
        else
            customstate = (CustomAuthState)state;
        Console.WriteLine("In Evaluate");
        if (!customstate.ClaimsAdded)
        {
           IList<Claim> claims = new List<Claim>();

           foreach (ClaimSet cs in evaluationContext.ClaimSets)
              foreach (Claim c in cs.FindClaims(ClaimTypes.Name,
                                         Rights.PossessProperty))
                  foreach (string s in
                        GetAllowedOpList(c.Resource.ToString()))
                  {
                       claims.Add(new
               Claim("http://example.com/claims/allowedoperation",
                                    s, Rights.PossessProperty));
                            Console.WriteLine("Claim added {0}", s);
                      }
                   evaluationContext.AddClaimSet(this,
                           new DefaultClaimSet(this.Issuer,claims));
                   customstate.ClaimsAdded = true;
                   bRet = true;
                }
         else
         {
              bRet = true;
         }
         return bRet;
     }
...
}
```

<span data-ttu-id="4af6e-142">Il codice precedente mostra come il metodo <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> controlla che non sia stata aggiunta nessuna nuova attestazione che influisce sull'elaborazione e aggiunge attestazioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="4af6e-142">The previous code shows how the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method checks that no new claims have been added that affect the processing and adds specific claims.</span></span> <span data-ttu-id="4af6e-143">Le attestazioni consentite vengono ottenute dal metodo `GetAllowedOpList`, implementato per restituire un elenco specifico di operazioni che l'utente può eseguire.</span><span class="sxs-lookup"><span data-stu-id="4af6e-143">The claims that are allowed are obtained from the `GetAllowedOpList` method, which is implemented to return a specific list of operations that the user is allowed to perform.</span></span> <span data-ttu-id="4af6e-144">I criteri di autorizzazione aggiungono attestazioni per l'accesso alla specifica operazione.</span><span class="sxs-lookup"><span data-stu-id="4af6e-144">The authorization policy adds claims for accessing the particular operation.</span></span> <span data-ttu-id="4af6e-145">Tale accesso verrà utilizzato in un secondo momento da <xref:System.ServiceModel.ServiceAuthorizationManager> per effettuare scelte in relazione al controllo dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="4af6e-145">This is later used by the <xref:System.ServiceModel.ServiceAuthorizationManager> to perform access check decisions.</span></span>

<span data-ttu-id="4af6e-146">Quando l'interfaccia <xref:System.IdentityModel.Policy.IAuthorizationPolicy> personalizzata è stata implementata, l'host del servizio deve essere informato dei criteri di autorizzazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4af6e-146">Once the custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> is implemented, the service host must be informed about the authorization policies to use.</span></span>

```xml
<serviceAuthorization>
       <authorizationPolicies>
            <add policyType='Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary' />
       </authorizationPolicies>
</serviceAuthorization>
```

<span data-ttu-id="4af6e-147">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="4af6e-147">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="4af6e-148">Il client chiama correttamente i metodi Add, Subtract e Multiple e ottiene un messaggio "Accesso negato" quando tenta di chiamare il metodo Divide.</span><span class="sxs-lookup"><span data-stu-id="4af6e-148">The client successfully calls the Add, Subtract and Multiple methods and gets an "Access is denied" message when trying to call the Divide method.</span></span> <span data-ttu-id="4af6e-149">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="4af6e-149">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="4af6e-150">File batch di installazione</span><span class="sxs-lookup"><span data-stu-id="4af6e-150">Setup Batch File</span></span>

<span data-ttu-id="4af6e-151">Il file batch Setup.bat incluso in questo esempio consente di configurare il server con i certificati attinenti per eseguire un'applicazione indipendente che richiede la sicurezza server basata su certificato.</span><span class="sxs-lookup"><span data-stu-id="4af6e-151">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span>

<span data-ttu-id="4af6e-152">Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch in modo che possano essere modificate per l'esecuzione nella configurazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="4af6e-152">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration:</span></span>

- <span data-ttu-id="4af6e-153">Creazione del certificato server.</span><span class="sxs-lookup"><span data-stu-id="4af6e-153">Creating the server certificate.</span></span>

    <span data-ttu-id="4af6e-154">Le righe seguenti del file batch Setup.bat creano il certificato server da usare.</span><span class="sxs-lookup"><span data-stu-id="4af6e-154">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="4af6e-155">La variabile %SERVER_NAME% specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="4af6e-155">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="4af6e-156">Modificare questa variabile per specificare nome del server.</span><span class="sxs-lookup"><span data-stu-id="4af6e-156">Change this variable to specify your own server name.</span></span> <span data-ttu-id="4af6e-157">Il valore predefinito è localhost.</span><span class="sxs-lookup"><span data-stu-id="4af6e-157">The default value is localhost.</span></span>

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="4af6e-158">Installazione del certificato server nell'archivio certificati attendibili del client</span><span class="sxs-lookup"><span data-stu-id="4af6e-158">Installing the server certificate into client's trusted certificate store.</span></span>

    <span data-ttu-id="4af6e-159">Le righe seguenti nel file batch Setup.bat copiano il certificato server nell'archivio di persone attendibile del client.</span><span class="sxs-lookup"><span data-stu-id="4af6e-159">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="4af6e-160">Questo passaggio è necessario perché i certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="4af6e-160">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="4af6e-161">Se è già disponibile un certificato con radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il passaggio del popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="4af6e-161">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- <span data-ttu-id="4af6e-162">Creazione del certificato del client.</span><span class="sxs-lookup"><span data-stu-id="4af6e-162">Creating the client certificate.</span></span>

    <span data-ttu-id="4af6e-163">Le righe seguenti del file batch Setup.bat creano il certificato client da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4af6e-163">The following lines from the Setup.bat batch file create the client certificate to be used.</span></span> <span data-ttu-id="4af6e-164">La variabile %USER_NAME% specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="4af6e-164">The %USER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="4af6e-165">Questo valore è impostato su "test1" perché questo è il nome cercato da `IAuthorizationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="4af6e-165">This value is set to "test1" because this is the name the `IAuthorizationPolicy` looks for.</span></span> <span data-ttu-id="4af6e-166">Se si modifica il valore di %USER_NAME%, è necessario modificare il valore corrispondente nel metodo `IAuthorizationPolicy.Evaluate`.</span><span class="sxs-lookup"><span data-stu-id="4af6e-166">If you change the value of %USER_NAME% you must change the corresponding value in the `IAuthorizationPolicy.Evaluate` method.</span></span>

    <span data-ttu-id="4af6e-167">Il certificato viene memorizzato nell'archivio personale nel percorso di archivio CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="4af6e-167">The certificate is stored in My (Personal) store under the CurrentUser store location.</span></span>

    ```bat
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="4af6e-168">Installazione del certificato client nell'archivio certificati attendibili del server</span><span class="sxs-lookup"><span data-stu-id="4af6e-168">Installing the client certificate into server's trusted certificate store.</span></span>

    <span data-ttu-id="4af6e-169">Le righe seguenti nel file batch Setup.bat copiano il certificato client nell'archivio delle persone attendibile.</span><span class="sxs-lookup"><span data-stu-id="4af6e-169">The following lines in the Setup.bat batch file copy the client certificate into the trusted people store.</span></span> <span data-ttu-id="4af6e-170">Questo passaggio è necessario perché i certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema del server.</span><span class="sxs-lookup"><span data-stu-id="4af6e-170">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the server system.</span></span> <span data-ttu-id="4af6e-171">Se è già disponibile un certificato che è impostato come radice in un certificato radice attendibile, ad esempio un certificato rilasciato da Microsoft, il passaggio della popolazione dell'archivio certificati server con il certificato client non è necessario.</span><span class="sxs-lookup"><span data-stu-id="4af6e-171">If you already have a certificate that is rooted in a trusted root certificate—for example, a Microsoft issued certificate—this step of populating the server certificate store with the client certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="4af6e-172">Per impostare e compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="4af6e-172">To set up and build the sample</span></span>

1. <span data-ttu-id="4af6e-173">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4af6e-173">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

2. <span data-ttu-id="4af6e-174">Per eseguire l'esempio su un solo computer o tra computer diversi, seguire le istruzioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="4af6e-174">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="4af6e-175">Se si usa Svcutil.exe per rigenerare la configurazione di questo esempio, assicurarsi di modificare il nome dell'endpoint nella configurazione client in modo che corrisponda al codice client.</span><span class="sxs-lookup"><span data-stu-id="4af6e-175">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="4af6e-176">Per eseguire l'esempio nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="4af6e-176">To run the sample on the same computer</span></span>

1. <span data-ttu-id="4af6e-177">Aprire Prompt dei comandi per gli sviluppatori per Visual Studio con privilegi di amministratore ed eseguire *Setup. bat* dalla cartella di installazione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="4af6e-177">Open Developer Command Prompt for Visual Studio with administrator privileges and run *Setup.bat* from the sample install folder.</span></span> <span data-ttu-id="4af6e-178">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="4af6e-178">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4af6e-179">Il file batch Setup. bat è progettato per essere eseguito da Prompt dei comandi per gli sviluppatori per Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4af6e-179">The Setup.bat batch file is designed to be run from Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="4af6e-180">La variabile di ambiente PATH impostata all'interno Prompt dei comandi per gli sviluppatori per Visual Studio punta alla directory che contiene i file eseguibili richiesti dallo script *Setup. bat* .</span><span class="sxs-lookup"><span data-stu-id="4af6e-180">The PATH environment variable set within Developer Command Prompt for Visual Studio points to the directory that contains executables required by the *Setup.bat* script.</span></span>

1. <span data-ttu-id="4af6e-181">Avviare Service. exe da *service\bin*.</span><span class="sxs-lookup"><span data-stu-id="4af6e-181">Launch Service.exe from *service\bin*.</span></span>

1. <span data-ttu-id="4af6e-182">Avviare client. exe da \*\client\bin\*.</span><span class="sxs-lookup"><span data-stu-id="4af6e-182">Launch Client.exe from *\client\bin*.</span></span> <span data-ttu-id="4af6e-183">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="4af6e-183">Client activity is displayed on the client console application.</span></span>

<span data-ttu-id="4af6e-184">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="4af6e-184">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="4af6e-185">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="4af6e-185">To run the sample across computers</span></span>

1. <span data-ttu-id="4af6e-186">Creare una directory sul computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="4af6e-186">Create a directory on the service computer.</span></span>

2. <span data-ttu-id="4af6e-187">Copiare i file di programma del servizio da *\service\bin* nella directory del computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="4af6e-187">Copy the service program files from *\service\bin* to the directory on the service computer.</span></span> <span data-ttu-id="4af6e-188">Copiare inoltre i file Setup.bat, Cleanup.bat,GetComputerName.vbs e ImportClientCert.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="4af6e-188">Also copy the Setup.bat, Cleanup.bat, GetComputerName.vbs and ImportClientCert.bat files to the service computer.</span></span>

3. <span data-ttu-id="4af6e-189">Creare una directory sul client del servizio per i file binari del client.</span><span class="sxs-lookup"><span data-stu-id="4af6e-189">Create a directory on the client computer for the client binaries.</span></span>

4. <span data-ttu-id="4af6e-190">Copiare i file di programma del client nella directory del client sul computer relativo</span><span class="sxs-lookup"><span data-stu-id="4af6e-190">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="4af6e-191">e i file Setup.bat, Cleanup.bat e ImportServiceCert.bat nel client.</span><span class="sxs-lookup"><span data-stu-id="4af6e-191">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>

5. <span data-ttu-id="4af6e-192">Sul server, eseguire `setup.bat service` prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4af6e-192">On the server, run `setup.bat service` in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="4af6e-193">Quando `setup.bat` si esegue con l' `service` argomento viene creato un certificato del servizio con il nome di dominio completo del computer e il certificato del servizio viene esportato in un file denominato *Service. cer*.</span><span class="sxs-lookup"><span data-stu-id="4af6e-193">Running `setup.bat` with the `service` argument creates a service certificate with the fully qualified domain name of the computer, and exports the service certificate to a file named *Service.cer*.</span></span>

6. <span data-ttu-id="4af6e-194">Modificare *Service. exe. config* per riflettere il nuovo nome del certificato (nell' `findValue` attributo in [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ) che corrisponde al nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="4af6e-194">Edit *Service.exe.config* to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully qualified domain name of the computer.</span></span> <span data-ttu-id="4af6e-195">Modificare anche **nomecomputer** nell' \<service> / \<baseAddresses> elemento da localhost al nome completo del computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="4af6e-195">Also change the **computername** in the \<service>/\<baseAddresses> element from localhost to the fully qualified name of your service computer.</span></span>

7. <span data-ttu-id="4af6e-196">Copiare il file *Service. cer* dalla directory del servizio alla directory client nel computer client.</span><span class="sxs-lookup"><span data-stu-id="4af6e-196">Copy the *Service.cer* file from the service directory to the client directory on the client computer.</span></span>

8. <span data-ttu-id="4af6e-197">Nel client, eseguire `setup.bat client` in prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4af6e-197">On the client, run `setup.bat client` in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="4af6e-198">Quando `setup.bat` si esegue con l' `client` argomento viene creato un certificato client denominato **test1** e il certificato client viene esportato in un file denominato *client. cer*.</span><span class="sxs-lookup"><span data-stu-id="4af6e-198">Running `setup.bat` with the `client` argument creates a client certificate named **test1** and exports the client certificate to a file named *Client.cer*.</span></span>

9. <span data-ttu-id="4af6e-199">Nel file *client. exe. config* nel computer client, modificare il valore dell'indirizzo dell'endpoint in modo che corrisponda al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="4af6e-199">In the *Client.exe.config* file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="4af6e-200">A tale scopo, sostituire **localhost** con il nome di dominio completo del server.</span><span class="sxs-lookup"><span data-stu-id="4af6e-200">Do this by replacing **localhost** with the fully qualified domain name of the server.</span></span>

10. <span data-ttu-id="4af6e-201">Copiare il file Client.cer dalla directory del client nella directory del servizio sul server.</span><span class="sxs-lookup"><span data-stu-id="4af6e-201">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>

11. <span data-ttu-id="4af6e-202">Sul client, eseguire *ImportServiceCert. bat* in prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4af6e-202">On the client, run *ImportServiceCert.bat* in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="4af6e-203">Questa operazione importa il certificato del servizio dal file Service. cer nell'archivio **CurrentUser-TrustedPeople** .</span><span class="sxs-lookup"><span data-stu-id="4af6e-203">This imports the service certificate from the Service.cer file into the **CurrentUser - TrustedPeople** store.</span></span>

12. <span data-ttu-id="4af6e-204">Sul server, eseguire *ImportClientCert. bat* in prompt dei comandi per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4af6e-204">On the server, run *ImportClientCert.bat* in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

    <span data-ttu-id="4af6e-205">Il certificato client viene importato dal file client. cer nell'archivio **LocalMachine-TrustedPeople** .</span><span class="sxs-lookup"><span data-stu-id="4af6e-205">This imports the client certificate from the Client.cer file into the **LocalMachine - TrustedPeople** store.</span></span>

13. <span data-ttu-id="4af6e-206">Sul computer server avviare Service.exe dalla finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="4af6e-206">On the server computer, launch Service.exe from the command prompt window.</span></span>

14. <span data-ttu-id="4af6e-207">Sul computer client avviare Client.exe da una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="4af6e-207">On the client computer, launch Client.exe from a command prompt window.</span></span>

    <span data-ttu-id="4af6e-208">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="4af6e-208">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

### <a name="clean-up-after-the-sample"></a><span data-ttu-id="4af6e-209">Esegui la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="4af6e-209">Clean up after the sample</span></span>

<span data-ttu-id="4af6e-210">Per eseguire la pulizia dopo l'esempio, eseguire *Cleanup. bat* nella cartella Samples al termine dell'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="4af6e-210">To clean up after the sample, run *Cleanup.bat* in the samples folder when you have finished running the sample.</span></span> <span data-ttu-id="4af6e-211">In questo modo i certificati server e client vengono rimossi dall'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="4af6e-211">This removes the server and client certificates from the certificate store.</span></span>

> [!NOTE]
> <span data-ttu-id="4af6e-212">Questo script non rimuove i certificati del servizio da un client quando si esegue l'esempio tra più computer.</span><span class="sxs-lookup"><span data-stu-id="4af6e-212">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="4af6e-213">Se sono stati eseguiti esempi WCF che usano certificati tra computer, assicurarsi di cancellare i certificati del servizio installati nell'archivio CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="4af6e-213">If you have run WCF samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="4af6e-214">Per eseguire questa operazione, usare il seguente comando: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Ad esempio: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="4af6e-214">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
