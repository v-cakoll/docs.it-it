---
title: Token personalizzato
ms.date: 03/30/2017
ms.assetid: e7fd8b38-c370-454f-ba3e-19759019f03d
ms.openlocfilehash: 11b89f6d4f2800f079ba6576801b39c85324f6e0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425077"
---
# <a name="custom-token"></a><span data-ttu-id="eaed2-102">Token personalizzato</span><span class="sxs-lookup"><span data-stu-id="eaed2-102">Custom Token</span></span>
<span data-ttu-id="eaed2-103">Questo esempio viene illustrato come aggiungere un'implementazione del token personalizzata in un'applicazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="eaed2-103">This sample demonstrates how to add a custom token implementation into a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="eaed2-104">Nell'esempio viene usato un `CreditCardToken` per passare in modo protetto le informazioni sulle carte di credito del client al servizio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-104">The example uses a `CreditCardToken` to securely pass information about client credit cards to the service.</span></span> <span data-ttu-id="eaed2-105">Il token viene passato nell'intestazione del messaggio WS-Security e viene firmato e crittografato usando l'elemento di associazione di sicurezza simmetrica, il corpo del messaggio e altre intestazioni del messaggio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-105">The token is passed in the WS-Security message header and is signed and encrypted using the symmetric security binding element along with message body and other message headers.</span></span> <span data-ttu-id="eaed2-106">Questa operazione è utile nei casi in cui i token incorporati non sono sufficienti</span><span class="sxs-lookup"><span data-stu-id="eaed2-106">This is useful in cases where the built-in tokens are not sufficient.</span></span> <span data-ttu-id="eaed2-107">In questo esempio viene illustrato come fornire un token di sicurezza personalizzato a un servizio, invece di usare uno dei token incorporati.</span><span class="sxs-lookup"><span data-stu-id="eaed2-107">This sample demonstrates how to provide a custom security token to a service instead of using one of the built-in tokens.</span></span> <span data-ttu-id="eaed2-108">Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta.</span><span class="sxs-lookup"><span data-stu-id="eaed2-108">The service implements a contract that defines a request-reply communication pattern.</span></span>

> [!NOTE]
>  <span data-ttu-id="eaed2-109">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="eaed2-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="eaed2-110">Per riassumere, questo esempio dimostra quanto segue.</span><span class="sxs-lookup"><span data-stu-id="eaed2-110">To summarize, this sample demonstrates the following:</span></span>

- <span data-ttu-id="eaed2-111">In che modo un client può passare un token di sicurezza personalizzato a un servizio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-111">How a client can pass a custom security token to a service.</span></span>

- <span data-ttu-id="eaed2-112">In che modo il servizio può usare e convalidare un token di sicurezza personalizzato.</span><span class="sxs-lookup"><span data-stu-id="eaed2-112">How the service can consume and validate a custom security token.</span></span>

- <span data-ttu-id="eaed2-113">Modo in cui il codice del servizio WCF è possibile ottenere le informazioni sui token di sicurezza ricevuto includendo il token di sicurezza personalizzato.</span><span class="sxs-lookup"><span data-stu-id="eaed2-113">How the WCF service code can obtain the information about received security tokens including the custom security token.</span></span>

- <span data-ttu-id="eaed2-114">Come viene usato il certificato X.509 del server per proteggere la chiave simmetrica usata per crittografare il messaggio e la firma.</span><span class="sxs-lookup"><span data-stu-id="eaed2-114">How the server's X.509 certificate is used to protect the symmetric key used for message encryption and signature.</span></span>

## <a name="client-authentication-using-a-custom-security-token"></a><span data-ttu-id="eaed2-115">Autenticazione client tramite un token di sicurezza personalizzato</span><span class="sxs-lookup"><span data-stu-id="eaed2-115">Client Authentication Using a Custom Security Token</span></span>
 <span data-ttu-id="eaed2-116">Il servizio espone un solo endpoint che viene creato a livello di programmazione usando le classi `BindingHelper` e `EchoServiceHost`.</span><span class="sxs-lookup"><span data-stu-id="eaed2-116">The service exposes a single endpoint that is programmatically created using `BindingHelper` and `EchoServiceHost` classes.</span></span> <span data-ttu-id="eaed2-117">L'endpoint è costituito da un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="eaed2-117">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="eaed2-118">L'associazione è configurata con un'associazione personalizzata usando `SymmetricSecurityBindingElement` e `HttpTransportBindingElement`.</span><span class="sxs-lookup"><span data-stu-id="eaed2-118">The binding is configured with a custom binding using `SymmetricSecurityBindingElement` and `HttpTransportBindingElement`.</span></span> <span data-ttu-id="eaed2-119">Questo esempio imposta `SymmetricSecurityBindingElement` per usare un certificato X.509 del servizio per proteggere la chiave simmetrica durante la trasmissione e per passare un `CreditCardToken` personalizzato in un'intestazione del messaggio WS-Security come token di sicurezza firmato e crittografato.</span><span class="sxs-lookup"><span data-stu-id="eaed2-119">This sample sets the `SymmetricSecurityBindingElement` to use a service's X.509 certificate to protect the symmetric key during transmission and to pass a custom `CreditCardToken` in a WS-Security message header as a signed and encrypted security token.</span></span> <span data-ttu-id="eaed2-120">Il comportamento specifica le credenziali del servizio che devono essere usate per l'autenticazione del client e anche informazioni sul certificato X.509 del servizio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-120">The behavior specifies the service credentials that are to be used for client authentication and also information about the service X.509 certificate.</span></span>

```csharp
public static class BindingHelper
{
    public static Binding CreateCreditCardBinding()
    {
        HttpTransportBindingElement httpTransport = new HttpTransportBindingElement();

        // The message security binding element will be configured to require a credit card.
        // The token that is encrypted with the service's certificate.
        SymmetricSecurityBindingElement messageSecurity = new SymmetricSecurityBindingElement();
        messageSecurity.EndpointSupportingTokenParameters.SignedEncrypted.Add(new CreditCardTokenParameters());
        X509SecurityTokenParameters x509ProtectionParameters = new X509SecurityTokenParameters();
        x509ProtectionParameters.InclusionMode = SecurityTokenInclusionMode.Never;
        messageSecurity.ProtectionTokenParameters = x509ProtectionParameters;
        return new CustomBinding(messageSecurity, httpTransport);
    }
}
```

 <span data-ttu-id="eaed2-121">Per usare un token della carta di credito nel messaggio l'esempio usa credenziali del servizio personalizzate per fornire questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="eaed2-121">To consume a credit card token in the message, the sample uses custom service credentials to provide this functionality.</span></span> <span data-ttu-id="eaed2-122">La classe delle credenziali del servizio si trova nella classe `CreditCardServiceCredentials` e viene aggiunta alle raccolte di comportamenti dell'host del servizio nel metodo `EchoServiceHost.InitializeRuntime`.</span><span class="sxs-lookup"><span data-stu-id="eaed2-122">The service credentials class is located in the `CreditCardServiceCredentials` class and is added to the behaviors collections of the service host in the `EchoServiceHost.InitializeRuntime` method.</span></span>

```csharp
class EchoServiceHost : ServiceHost
{
    string creditCardFile;

    public EchoServiceHost(parameters Uri[] addresses)
        : base(typeof(EchoService), addresses)
    {
        creditCardFile = ConfigurationManager.AppSettings["creditCardFile"];
        if (string.IsNullOrEmpty(creditCardFile))
        {
            throw new ConfigurationErrorsException("creditCardFile not specified in service config");
        }

        creditCardFile = String.Format("{0}\\{1}", System.Web.Hosting.HostingEnvironment.ApplicationPhysicalPath, creditCardFile);
    }

    override protected void InitializeRuntime()
    {
        // Create a credit card service credentials and add it to the behaviors.
        CreditCardServiceCredentials serviceCredentials = new CreditCardServiceCredentials(this.creditCardFile);
        serviceCredentials.ServiceCertificate.SetCertificate("CN=localhost", StoreLocation.LocalMachine, StoreName.My);
        this.Description.Behaviors.Remove((typeof(ServiceCredentials)));
        this.Description.Behaviors.Add(serviceCredentials);

        // Register a credit card binding for the endpoint.
        Binding creditCardBinding = BindingHelper.CreateCreditCardBinding();
        this.AddServiceEndpoint(typeof(IEchoService), creditCardBinding, string.Empty);

        base.InitializeRuntime();
    }
}
```

 <span data-ttu-id="eaed2-123">L'endpoint del client viene configurato in modo simile all'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-123">The client endpoint is configured in a similar manner as the service endpoint.</span></span> <span data-ttu-id="eaed2-124">Il client usa la stessa classe `BindingHelper` per creare un'associazione.</span><span class="sxs-lookup"><span data-stu-id="eaed2-124">The client uses the same `BindingHelper` class to create a binding.</span></span> <span data-ttu-id="eaed2-125">Il resto dell'installazione è situato nella classe `Client`.</span><span class="sxs-lookup"><span data-stu-id="eaed2-125">The rest of the setup is located in the `Client` class.</span></span> <span data-ttu-id="eaed2-126">Il client imposta inoltre le informazioni contenute nel `CreditCardToken` e le informazioni sul certificato X.509 del servizio nel codice di impostazione aggiungendo un'istanza `CreditCardClientCredentials` con i dati appropriati alla raccolta di comportamenti dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="eaed2-126">The client also sets information to be contained in the `CreditCardToken` and information about the service X.509 certificate in the setup code by adding a `CreditCardClientCredentials` instance with the proper data to the client endpoint behaviors collection.</span></span> <span data-ttu-id="eaed2-127">L'esempio usa il certificato X.509 con il nome del soggetto impostato su `CN=localhost` come certificato del servizio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-127">The sample uses X.509 certificate with subject name set to `CN=localhost` as the service certificate.</span></span>

```csharp
Binding creditCardBinding = BindingHelper.CreateCreditCardBinding();
EndpointAddress serviceAddress = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");

// Create a client with given client endpoint configuration
channelFactory = new ChannelFactory<IEchoService>(creditCardBinding, serviceAddress);

// configure the credit card credentials on the channel factory
CreditCardClientCredentials credentials =
      new CreditCardClientCredentials(
      new CreditCardInfo(creditCardNumber, issuer, expirationTime));
// configure the service certificate on the credentials
credentials.ServiceCertificate.SetDefaultCertificate(
      "CN=localhost", StoreLocation.LocalMachine, StoreName.My);

// replace ClientCredentials with CreditCardClientCredentials
channelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));
channelFactory.Endpoint.Behaviors.Add(credentials);

client = channelFactory.CreateChannel();

Console.WriteLine("Echo service returned: {0}", client.Echo());

((IChannel)client).Close();
channelFactory.Close();
```

## <a name="custom-security-token-implementation"></a><span data-ttu-id="eaed2-128">Implementazione del token di sicurezza personalizzato</span><span class="sxs-lookup"><span data-stu-id="eaed2-128">Custom Security Token Implementation</span></span>
 <span data-ttu-id="eaed2-129">Per abilitare un token di sicurezza personalizzato in WCF, creare una rappresentazione di oggetto del token di sicurezza personalizzato.</span><span class="sxs-lookup"><span data-stu-id="eaed2-129">To enable a custom security token in WCF, create an object representation of the custom security token.</span></span> <span data-ttu-id="eaed2-130">Nell'esempio la rappresentazione si trova nella classe `CreditCardToken`.</span><span class="sxs-lookup"><span data-stu-id="eaed2-130">The sample has this representation in the `CreditCardToken` class.</span></span> <span data-ttu-id="eaed2-131">La rappresentazione dell'oggetto contiene tutte le informazioni del token di sicurezza pertinenti e fornisce un elenco di chiavi di sicurezza contenute nel token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="eaed2-131">The object representation is responsible for holding all relevant security token information and to provide a list of security keys contained in the security token.</span></span> <span data-ttu-id="eaed2-132">In questo caso, il token di sicurezza della carta di credito non contiene chiavi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="eaed2-132">In this case, the credit card security token does not contain any security key.</span></span>

 <span data-ttu-id="eaed2-133">La sezione successiva descrive ciò che deve essere eseguita per abilitare un token personalizzato essere trasmessi in rete e utilizzati da un endpoint WCF.</span><span class="sxs-lookup"><span data-stu-id="eaed2-133">The next section describes what must be done to enable a custom token to be transmitted over the wire and consumed by a WCF endpoint.</span></span>

```csharp
class CreditCardToken : SecurityToken
{
    CreditCardInfo cardInfo;
    DateTime effectiveTime = DateTime.UtcNow;
    string id;
    ReadOnlyCollection<SecurityKey> securityKeys;

    public CreditCardToken(CreditCardInfo cardInfo) : this(cardInfo, Guid.NewGuid().ToString()) { }

    public CreditCardToken(CreditCardInfo cardInfo, string id)
    {
        if (cardInfo == null)
            throw new ArgumentNullException("cardInfo");

        if (id == null)
            throw new ArgumentNullException("id");

        this.cardInfo = cardInfo;
        this.id = id;

        // The credit card token is not capable of any cryptography.
        this.securityKeys = new ReadOnlyCollection<SecurityKey>(new List<SecurityKey>());
    }

    public CreditCardInfo CardInfo { get { return this.cardInfo; } }

    public override ReadOnlyCollection<SecurityKey> SecurityKeys { get { return this.securityKeys; } }

    public override DateTime ValidFrom { get { return this.effectiveTime; } }
    public override DateTime ValidTo { get { return this.cardInfo.ExpirationDate; } }
    public override string Id { get { return this.id; } }
}
```

## <a name="getting-the-custom-credit-card-token-to-and-from-the-message"></a><span data-ttu-id="eaed2-134">Recupero del token della carta di credito personalizzato a e da il messaggio</span><span class="sxs-lookup"><span data-stu-id="eaed2-134">Getting the Custom Credit Card Token to and from the Message</span></span>
 <span data-ttu-id="eaed2-135">I serializzatori di token di sicurezza in WCF sono responsabili per la creazione di una rappresentazione di oggetto del token di sicurezza dal XML nel messaggio e la creazione di un formato XML del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="eaed2-135">Security token serializers in WCF are responsible for creating an object representation of security tokens from the XML in the message and creating a XML form of the security tokens.</span></span> <span data-ttu-id="eaed2-136">Sono inoltre responsabili per altre funzionalità, ad esempio per la lettura e la scrittura degli identificatori di chiave che puntano ai token di sicurezza, ma in questo esempio viene usata solo la funzionalità relativa al token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="eaed2-136">They are also responsible for other functionality such as reading and writing key identifiers pointing to security tokens, but this example uses only security token-related functionality.</span></span> <span data-ttu-id="eaed2-137">Per abilitare un token personalizzato è necessario implementare un serializzatore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="eaed2-137">To enable a custom token you must implement your own security token serializer.</span></span> <span data-ttu-id="eaed2-138">In questo esempio viene usata la classe `CreditCardSecurityTokenSerializer` a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="eaed2-138">This sample uses the `CreditCardSecurityTokenSerializer` class for this purpose.</span></span>

 <span data-ttu-id="eaed2-139">Nel servizio, il serializzatore personalizzato legge il modulo XML del token personalizzato e lo usa per creare la rappresentazione dell'oggetto del token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="eaed2-139">On the service, the custom serializer reads the XML form of the custom token and creates the custom token object representation from it.</span></span>

 <span data-ttu-id="eaed2-140">Nel client, la classe `CreditCardSecurityTokenSerializer` scrive le informazioni contenute nella rappresentazione dell'oggetto del token di sicurezza nel writer XML.</span><span class="sxs-lookup"><span data-stu-id="eaed2-140">On the client, the `CreditCardSecurityTokenSerializer` class writes the information contained in the security token object representation into the XML writer.</span></span>

```csharp
public class CreditCardSecurityTokenSerializer : WSSecurityTokenSerializer
{
    public CreditCardSecurityTokenSerializer(SecurityTokenVersion version) : base() { }

    protected override bool CanReadTokenCore(XmlReader reader)
    {
        XmlDictionaryReader localReader = XmlDictionaryReader.CreateDictionaryReader(reader);

        if (reader == null) throw new ArgumentNullException("reader");

        if (reader.IsStartElement(Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace))
            return true;

        return base.CanReadTokenCore(reader);
    }

    protected override SecurityToken ReadTokenCore(XmlReader reader, SecurityTokenResolver tokenResolver)
    {
        if (reader == null) throw new ArgumentNullException("reader");

        if (reader.IsStartElement(Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace))
        {
            string id = reader.GetAttribute(Constants.Id, Constants.WsUtilityNamespace);

            reader.ReadStartElement();

            // Read the credit card number.
            string creditCardNumber = reader.ReadElementString(Constants.CreditCardNumberElementName, Constants.CreditCardTokenNamespace);

            // Read the expiration date.
            string expirationTimeString = reader.ReadElementString(Constants.CreditCardExpirationElementName, Constants.CreditCardTokenNamespace);
            DateTime expirationTime = XmlConvert.ToDateTime(expirationTimeString, XmlDateTimeSerializationMode.Utc);

            // Read the issuer of the credit card.
            string creditCardIssuer = reader.ReadElementString(Constants.CreditCardIssuerElementName, Constants.CreditCardTokenNamespace);
            reader.ReadEndElement();

            CreditCardInfo cardInfo = new CreditCardInfo(creditCardNumber, creditCardIssuer, expirationTime);

            return new CreditCardToken(cardInfo, id);
        }
        else
        {
            return WSSecurityTokenSerializer.DefaultInstance.ReadToken(reader, tokenResolver);
        }
    }

    protected override bool CanWriteTokenCore(SecurityToken token)
    {
        if (token is CreditCardToken)
            return true;

        else
            return base.CanWriteTokenCore(token);
    }

    protected override void WriteTokenCore(XmlWriter writer, SecurityToken token)
    {
        if (writer == null) { throw new ArgumentNullException("writer"); }
        if (token == null) { throw new ArgumentNullException("token"); }

        CreditCardToken c = token as CreditCardToken;
        if (c != null)
        {
            writer.WriteStartElement(Constants.CreditCardTokenPrefix, Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace);
            writer.WriteAttributeString(Constants.WsUtilityPrefix, Constants.Id, Constants.WsUtilityNamespace, token.Id);
            writer.WriteElementString(Constants.CreditCardNumberElementName, Constants.CreditCardTokenNamespace, c.CardInfo.CardNumber);
            writer.WriteElementString(Constants.CreditCardExpirationElementName, Constants.CreditCardTokenNamespace, XmlConvert.ToString(c.CardInfo.ExpirationDate, XmlDateTimeSerializationMode.Utc));
            writer.WriteElementString(Constants.CreditCardIssuerElementName, Constants.CreditCardTokenNamespace, c.CardInfo.CardIssuer);
            writer.WriteEndElement();
            writer.Flush();
        }
        else
        {
            base.WriteTokenCore(writer, token);
        }
    }
}
```

## <a name="how-token-provider-and-token-authenticator-classes-are-created"></a><span data-ttu-id="eaed2-141">Come creare classi di provider di token e di autenticatori del token</span><span class="sxs-lookup"><span data-stu-id="eaed2-141">How Token Provider and Token Authenticator Classes are Created</span></span>
 <span data-ttu-id="eaed2-142">Le credenziali del client e del servizio sono responsabili per fornire l'istanza del gestore del token di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="eaed2-142">Client and service credentials are responsible for providing the security token manager instance.</span></span> <span data-ttu-id="eaed2-143">L'istanza del gestore del token di sicurezza viene usato per ottenere i provider di token, gli autenticatori del token e i serializzatori di token.</span><span class="sxs-lookup"><span data-stu-id="eaed2-143">The security token manager instance is used to get token providers, token authenticators and token serializers.</span></span>

 <span data-ttu-id="eaed2-144">Il provider di token crea una rappresentazione dell'oggetto del token in base alle informazioni contenute nelle credenziali del client o del servizio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-144">The token provider creates an object representation of the token based on the information contained in the client or service credentials.</span></span> <span data-ttu-id="eaed2-145">La rappresentazione dell'oggetto del token viene quindi scritta nel messaggio usando il serializzatore di token (descritto nella sezione precedente).</span><span class="sxs-lookup"><span data-stu-id="eaed2-145">The token object representation is then written to the message using the token serializer (discussed in the previous section).</span></span>

 <span data-ttu-id="eaed2-146">L'autenticatore del token convalida i token che arrivano nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-146">The token authenticator validates tokens that arrive in the message.</span></span> <span data-ttu-id="eaed2-147">La rappresentazione dell'oggetto del token in arrivo viene creata dal serializzatore di token.</span><span class="sxs-lookup"><span data-stu-id="eaed2-147">The incoming token object representation is created by the token serializer.</span></span> <span data-ttu-id="eaed2-148">Questa rappresentazione dell'oggetto viene quindi passata all'autenticatore del token per la convalida.</span><span class="sxs-lookup"><span data-stu-id="eaed2-148">This object representation is then passed to the token authenticator for validation.</span></span> <span data-ttu-id="eaed2-149">Una volta convalidato correttamente il token, l'autenticatore del token restituisce una raccolta di oggetti `IAuthorizationPolicy` che rappresentano le informazioni contenute nel token.</span><span class="sxs-lookup"><span data-stu-id="eaed2-149">After the token is successfully validated, the token authenticator returns a collection of `IAuthorizationPolicy` objects that represent the information contained in the token.</span></span> <span data-ttu-id="eaed2-150">Queste informazioni vengono usate in un secondo momento durante l'elaborazione del messaggio per prendere decisioni di autorizzazione e fornire attestazioni per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eaed2-150">This information is used later during the message processing to perform authorization decisions and to provide claims for the application.</span></span> <span data-ttu-id="eaed2-151">In questo esempio, l'autenticatore del token della carta di credito usa `CreditCardTokenAuthorizationPolicy` a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="eaed2-151">In this example, the credit card token authenticator uses `CreditCardTokenAuthorizationPolicy` for this purpose.</span></span>

 <span data-ttu-id="eaed2-152">Il serializzatore di token ha la responsabilità di ottenere la rappresentazione dell'oggetto del token alla e dalla rete.</span><span class="sxs-lookup"><span data-stu-id="eaed2-152">The token serializer is responsible for getting the object representation of the token to and from the wire.</span></span> <span data-ttu-id="eaed2-153">Questa operazione viene descritta nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="eaed2-153">This is discussed in the previous section.</span></span>

 <span data-ttu-id="eaed2-154">In questo esempio, si usa un provider di token solo nel client e un autenticatore del token solo nel servizio, per trasmettere un token della carta di credito solo nella direzione dal client al servizio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-154">In this sample, we use a token provider only on the client and a token authenticator only on the service, because we want to transmit a credit card token only in the client-to-service direction.</span></span>

 <span data-ttu-id="eaed2-155">Nel client la funzionalità si trova nelle classi `CreditCardClientCredentials`, `CreditCardClientCredentialsSecurityTokenManager` e `CreditCardTokenProvider`.</span><span class="sxs-lookup"><span data-stu-id="eaed2-155">The functionality on the client is located in the `CreditCardClientCredentials`, `CreditCardClientCredentialsSecurityTokenManager` and `CreditCardTokenProvider` classes.</span></span>

 <span data-ttu-id="eaed2-156">Nel servizio, la funzionalità si trova nelle classi `CreditCardServiceCredentials`, `CreditCardServiceCredentialsSecurityTokenManager`, `CreditCardTokenAuthenticator` e `CreditCardTokenAuthorizationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="eaed2-156">On the service, the functionality resides in the `CreditCardServiceCredentials`, `CreditCardServiceCredentialsSecurityTokenManager`, `CreditCardTokenAuthenticator` and `CreditCardTokenAuthorizationPolicy` classes.</span></span>

```csharp
    public class CreditCardClientCredentials : ClientCredentials
    {
        CreditCardInfo creditCardInfo;

        public CreditCardClientCredentials(CreditCardInfo creditCardInfo)
            : base()
        {
            if (creditCardInfo == null)
                throw new ArgumentNullException("creditCardInfo");

            this.creditCardInfo = creditCardInfo;
        }

        public CreditCardInfo CreditCardInfo
        {
            get { return this.creditCardInfo; }
        }

        protected override ClientCredentials CloneCore()
        {
            return new CreditCardClientCredentials(this.creditCardInfo);
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new CreditCardClientCredentialsSecurityTokenManager(this);
        }
    }

    public class CreditCardClientCredentialsSecurityTokenManager : ClientCredentialsSecurityTokenManager
    {
        CreditCardClientCredentials creditCardClientCredentials;

        public CreditCardClientCredentialsSecurityTokenManager(CreditCardClientCredentials creditCardClientCredentials)
            : base (creditCardClientCredentials)
        {
            this.creditCardClientCredentials = creditCardClientCredentials;
        }

        public override SecurityTokenProvider CreateSecurityTokenProvider(SecurityTokenRequirement tokenRequirement)
        {
            // handle this token for Custom
            if (tokenRequirement.TokenType == Constants.CreditCardTokenType)
                return new CreditCardTokenProvider(this.creditCardClientCredentials.CreditCardInfo);
            // return server cert
            else if (tokenRequirement is InitiatorServiceModelSecurityTokenRequirement)
            {
                if (tokenRequirement.TokenType == SecurityTokenTypes.X509Certificate)
                {
                    return new X509SecurityTokenProvider(creditCardClientCredentials.ServiceCertificate.DefaultCertificate);
                }
            }

            return base.CreateSecurityTokenProvider(tokenRequirement);
        }

        public override SecurityTokenSerializer CreateSecurityTokenSerializer(SecurityTokenVersion version)
        {

            return new CreditCardSecurityTokenSerializer(version);
        }

    }

    class CreditCardTokenProvider : SecurityTokenProvider
    {
        CreditCardInfo creditCardInfo;

        public CreditCardTokenProvider(CreditCardInfo creditCardInfo) : base()
        {
            if (creditCardInfo == null)
            {
                throw new ArgumentNullException("creditCardInfo");
            }
            this.creditCardInfo = creditCardInfo;
        }

        protected override SecurityToken GetTokenCore(TimeSpan timeout)
        {
            SecurityToken result = new CreditCardToken(this.creditCardInfo);
            return result;
        }
    }

    public class CreditCardServiceCredentials : ServiceCredentials
    {
        string creditCardFile;

        public CreditCardServiceCredentials(string creditCardFile)
            : base()
        {
            if (creditCardFile == null)
                throw new ArgumentNullException("creditCardFile");

            this.creditCardFile = creditCardFile;
        }

        public string CreditCardDataFile
        {
            get { return this.creditCardFile; }
        }

        protected override ServiceCredentials CloneCore()
        {
            return new CreditCardServiceCredentials(this.creditCardFile);
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new CreditCardServiceCredentialsSecurityTokenManager(this);
        }
    }

    public class CreditCardServiceCredentialsSecurityTokenManager : ServiceCredentialsSecurityTokenManager
    {
        CreditCardServiceCredentials creditCardServiceCredentials;

        public CreditCardServiceCredentialsSecurityTokenManager(CreditCardServiceCredentials creditCardServiceCredentials)
            : base(creditCardServiceCredentials)
        {
            this.creditCardServiceCredentials = creditCardServiceCredentials;
        }

        public override SecurityTokenAuthenticator CreateSecurityTokenAuthenticator(SecurityTokenRequirement tokenRequirement, out SecurityTokenResolver outOfBandTokenResolver)
        {
            if (tokenRequirement.TokenType == Constants.CreditCardTokenType)
            {
                outOfBandTokenResolver = null;
                return new CreditCardTokenAuthenticator(creditCardServiceCredentials.CreditCardDataFile);
            }

            return base.CreateSecurityTokenAuthenticator(tokenRequirement, out outOfBandTokenResolver);
        }

        public override SecurityTokenSerializer CreateSecurityTokenSerializer(SecurityTokenVersion version)
        {
            return new CreditCardSecurityTokenSerializer(version);
        }
    }

    class CreditCardTokenAuthenticator : SecurityTokenAuthenticator
    {
        string creditCardsFile;
        public CreditCardTokenAuthenticator(string creditCardsFile)
        {
            this.creditCardsFile = creditCardsFile;
        }

        protected override bool CanValidateTokenCore(SecurityToken token)
        {
            return (token is CreditCardToken);
        }

        protected override ReadOnlyCollection<IAuthorizationPolicy> ValidateTokenCore(SecurityToken token)
        {
            CreditCardToken creditCardToken = token as CreditCardToken;

            if (creditCardToken.CardInfo.ExpirationDate < DateTime.UtcNow)
                throw new SecurityTokenValidationException("The credit card has expired");
            if (!IsCardNumberAndExpirationValid(creditCardToken.CardInfo))
                throw new SecurityTokenValidationException("Unknown or invalid credit card");

            // the credit card token has only 1 claim - the card number. The issuer for the claim is the
            // credit card issuer

            DefaultClaimSet cardIssuerClaimSet = new DefaultClaimSet(new Claim(ClaimTypes.Name, creditCardToken.CardInfo.CardIssuer, Rights.PossessProperty));
            DefaultClaimSet cardClaimSet = new DefaultClaimSet(cardIssuerClaimSet, new Claim(Constants.CreditCardNumberClaim, creditCardToken.CardInfo.CardNumber, Rights.PossessProperty));
            List<IAuthorizationPolicy> policies = new List<IAuthorizationPolicy>(1);
            policies.Add(new CreditCardTokenAuthorizationPolicy(cardClaimSet));
            return policies.AsReadOnly();
        }

        /// <summary>
        /// Helper method to check if a given credit card entry is present in the User DB
        /// </summary>
        private bool IsCardNumberAndExpirationValid(CreditCardInfo cardInfo)
        {
            try
            {
                using (StreamReader myStreamReader = new StreamReader(this.creditCardsFile))
                {
                    string line = "";
                    while ((line = myStreamReader.ReadLine()) != null)
                    {
                        string[] splitEntry = line.Split('#');
                        if (splitEntry[0] == cardInfo.CardNumber)
                        {
                            string expirationDateString = splitEntry[1].Trim();
                            DateTime expirationDateOnFile = DateTime.Parse(expirationDateString, System.Globalization.DateTimeFormatInfo.InvariantInfo, System.Globalization.DateTimeStyles.AdjustToUniversal);
                            if (cardInfo.ExpirationDate == expirationDateOnFile)
                            {
                                string issuer = splitEntry[2];
                                return issuer.Equals(cardInfo.CardIssuer, StringComparison.InvariantCultureIgnoreCase);
                            }
                            else
                            {
                                return false;
                            }
                        }
                    }
                    return false;
                }
            }
            catch (Exception e)
            {
                throw new Exception("BookStoreService: Error while retrieving credit card information from User DB " + e.ToString());
            }
        }
    }

    public class CreditCardTokenAuthorizationPolicy : IAuthorizationPolicy
    {
        string id;
        ClaimSet issuer;
        IEnumerable<ClaimSet> issuedClaimSets;

        public CreditCardTokenAuthorizationPolicy(ClaimSet issuedClaims)
        {
            if (issuedClaims == null)
                throw new ArgumentNullException("issuedClaims");
            this.issuer = issuedClaims.Issuer;
            this.issuedClaimSets = new ClaimSet[] { issuedClaims };
            this.id = Guid.NewGuid().ToString();
        }

        public ClaimSet Issuer { get { return this.issuer; } }

        public string Id { get { return this.id; } }

        public bool Evaluate(EvaluationContext context, ref object state)
        {
            foreach (ClaimSet issuance in this.issuedClaimSets)
            {
                context.AddClaimSet(this, issuance);
            }

            return true;
        }
    }
```

## <a name="displaying-the-callers-information"></a><span data-ttu-id="eaed2-157">Visualizzazione delle informazioni sul chiamante</span><span class="sxs-lookup"><span data-stu-id="eaed2-157">Displaying the Callers' Information</span></span>
 <span data-ttu-id="eaed2-158">Per visualizzare le informazioni sul chiamante, usare `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="eaed2-158">To display the caller's information, use the `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` as shown in the following sample code.</span></span> <span data-ttu-id="eaed2-159">`ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contiene attestazioni di autorizzazione associate al chiamante corrente.</span><span class="sxs-lookup"><span data-stu-id="eaed2-159">The `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contains authorization claims associated with the current caller.</span></span> <span data-ttu-id="eaed2-160">Le attestazioni vengono fornite dalla classe `CreditCardToken` nella raccolta `AuthorizationPolicies`.</span><span class="sxs-lookup"><span data-stu-id="eaed2-160">The claims are supplied by the `CreditCardToken` class in its `AuthorizationPolicies` collection.</span></span>

```csharp
bool TryGetStringClaimValue(ClaimSet claimSet, string claimType, out string claimValue)
{
    claimValue = null;
    IEnumerable<Claim> matchingClaims = claimSet.FindClaims(claimType, Rights.PossessProperty);
    if (matchingClaims == null)
        return false;
    IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();
    enumerator.MoveNext();
    claimValue = (enumerator.Current.Resource == null) ? null :
        enumerator.Current.Resource.ToString();
    return true;
}

string GetCallerCreditCardNumber()
{
     foreach (ClaimSet claimSet in
         ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)
     {
         string creditCardNumber = null;
         if (TryGetStringClaimValue(claimSet,
             Constants.CreditCardNumberClaim, out creditCardNumber))
             {
                 string issuer;
                 if (!TryGetStringClaimValue(claimSet.Issuer,
                        ClaimTypes.Name, out issuer))
                 {
                     issuer = "Unknown";
                 }
                 return $"Credit card '{creditCardNumber}' issued by '{issuer}'";
        }
    }
    return "Credit card is not known";
}
```

 <span data-ttu-id="eaed2-161">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="eaed2-161">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="eaed2-162">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="eaed2-162">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="eaed2-163">File batch di installazione</span><span class="sxs-lookup"><span data-stu-id="eaed2-163">Setup Batch File</span></span>
 <span data-ttu-id="eaed2-164">Il file batch Setup.bat incluso con questo esempio consente di configurare il server con i certificati attinenti per eseguire l'applicazione ospitata da IIS che richiede la sicurezza server basata su certificato.</span><span class="sxs-lookup"><span data-stu-id="eaed2-164">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run the IIS-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="eaed2-165">Questo file batch deve essere modificato per funzionare tra computer diversi o nel caso in cui non sia ospitato.</span><span class="sxs-lookup"><span data-stu-id="eaed2-165">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

 <span data-ttu-id="eaed2-166">Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch in modo che possano essere modificate per l'esecuzione nella configurazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="eaed2-166">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>

- <span data-ttu-id="eaed2-167">Creazione del certificato server:</span><span class="sxs-lookup"><span data-stu-id="eaed2-167">Creating the server certificate:</span></span>

     <span data-ttu-id="eaed2-168">Le righe seguenti del file batch `Setup.bat` creano il certificato server da usare.</span><span class="sxs-lookup"><span data-stu-id="eaed2-168">The following lines from the `Setup.bat` batch file create the server certificate to be used.</span></span> <span data-ttu-id="eaed2-169">La variabile `%SERVER_NAME%` specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="eaed2-169">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="eaed2-170">Modificare questa variabile per specificare nome del server.</span><span class="sxs-lookup"><span data-stu-id="eaed2-170">Change this variable to specify your own server name.</span></span> <span data-ttu-id="eaed2-171">Il valore predefinito in questo file batch è localhost.</span><span class="sxs-lookup"><span data-stu-id="eaed2-171">The default in this batch file is localhost.</span></span> <span data-ttu-id="eaed2-172">Se si modifica la variabile `%SERVER_NAME%`, è necessario sostituire tutte le istanze di localhost nei file Client.cs e Service.cs con il nome del server che si usa nello script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="eaed2-172">If you change the `%SERVER_NAME%` variable, you must go through the Client.cs and Service.cs files and replace all instances of localhost with the server name that you use in the Setup.bat script.</span></span>

     <span data-ttu-id="eaed2-173">Il certificato viene memorizzato nell'archivio personale nel percorso di archivio `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="eaed2-173">The certificate is stored in My (Personal) store under the `LocalMachine` store location.</span></span> <span data-ttu-id="eaed2-174">Il certificato viene archiviato nell'archivio LocalMachine per i servizi ospitati su IIS.</span><span class="sxs-lookup"><span data-stu-id="eaed2-174">The certificate is stored in the LocalMachine store for the IIS-hosted services.</span></span> <span data-ttu-id="eaed2-175">Per i servizi indipendenti, è necessario modificare il file batch per archiviare il certificato del client nel percorso dell'archivio CurrentUser sostituendo la stringa LocalMachine con CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="eaed2-175">For self-hosted services, you should modify the batch file to store the client certificate in the CurrentUser store location by replacing the string LocalMachine with CurrentUser.</span></span>

    ```
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="eaed2-176">Installazione del certificato server nell'archivio certificati attendibili del client:</span><span class="sxs-lookup"><span data-stu-id="eaed2-176">Installing the server certificate into client's trusted certificate store:</span></span>

     <span data-ttu-id="eaed2-177">Le righe seguenti nel file batch Setup.bat copiano il certificato server nell'archivio di persone attendibile del client.</span><span class="sxs-lookup"><span data-stu-id="eaed2-177">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="eaed2-178">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="eaed2-178">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="eaed2-179">Se è già disponibile un certificato con radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il passaggio del popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="eaed2-179">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```
    echo ************
    echo copying server cert to client's TrustedPeople store
    echo ************
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- <span data-ttu-id="eaed2-180">Per abilitare l'accesso alla chiave privata del certificato dal servizio ospitato su IIS, è necessario concedere le autorizzazioni alla chiave privata appropriate all'account utente con cui viene eseguito il processo ospitato da IIS.</span><span class="sxs-lookup"><span data-stu-id="eaed2-180">To enable access to the certificate private key from the IIS-hosted service, the user account under which the IIS-hosted process is running must be granted appropriate permissions for the private key.</span></span> <span data-ttu-id="eaed2-181">Questa operazione viene eseguita negli ultimi passaggi dello script Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="eaed2-181">This is accomplished by last steps in the Setup.bat script.</span></span>

    ```
    echo ************
    echo setting privileges on server certificates
    echo ************
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R
    iisreset
    ```

> [!NOTE]
>  <span data-ttu-id="eaed2-182">Il file batch Setup. bat è progettato per essere eseguito dal Prompt dei comandi un Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="eaed2-182">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="eaed2-183">Variabile di ambiente PATH impostata all'interno di punti di Prompt dei comandi di Visual Studio 2012 per la directory che contiene file eseguibili richiesti dallo script Setup. bat.</span><span class="sxs-lookup"><span data-stu-id="eaed2-183">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="eaed2-184">Per impostare e compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="eaed2-184">To set up and build the sample</span></span>

1. <span data-ttu-id="eaed2-185">Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="eaed2-185">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="eaed2-186">Per compilare la soluzione, seguire le istruzioni riportate in [Building Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="eaed2-186">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="eaed2-187">Per eseguire l'esempio nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="eaed2-187">To run the sample on the same computer</span></span>

1. <span data-ttu-id="eaed2-188">Aprire una finestra del Prompt dei comandi di Visual Studio 2012 con privilegi di amministratore ed eseguire Setup. bat dalla cartella di installazione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-188">Open a Visual Studio 2012 Command Prompt window with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="eaed2-189">In questo modo vengono installati tutti i certificati richiesti per l'esecuzione dell'esempio. Verificare che percorso includa la cartella in cui è presente Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="eaed2-189">This installs all the certificates required for running the sample.Make sure that the path includes the folder where Makecert.exe is located.</span></span>

> [!NOTE]
>  <span data-ttu-id="eaed2-190">Assicurarsi di rimuovere i certificati eseguendo Cleanup.bat una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-190">Be sure to remove the certificates by running Cleanup.bat when finished with the sample.</span></span> <span data-ttu-id="eaed2-191">Negli altri esempi relativi alla sicurezza vengono usati gli stessi certificati.</span><span class="sxs-lookup"><span data-stu-id="eaed2-191">Other security samples use the same certificates.</span></span>  
  
1. <span data-ttu-id="eaed2-192">Avviare Client.exe dalla directory client\bin.</span><span class="sxs-lookup"><span data-stu-id="eaed2-192">Launch Client.exe from client\bin directory.</span></span> <span data-ttu-id="eaed2-193">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="eaed2-193">Client activity is displayed on the client console application.</span></span>  
  
2. <span data-ttu-id="eaed2-194">Se il client e il servizio non è in grado di comunicare, vedere [suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="eaed2-194">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computer"></a><span data-ttu-id="eaed2-195">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="eaed2-195">To run the sample across computer</span></span>  
  
1. <span data-ttu-id="eaed2-196">Creare una directory sul computer del servizio per i file binari del servizio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-196">Create a directory on the service computer for the service binaries.</span></span>  
  
2. <span data-ttu-id="eaed2-197">Copiare i file di programma del servizio nella directory del servizio sul computer relativo.</span><span class="sxs-lookup"><span data-stu-id="eaed2-197">Copy the service program files into the service directory on the service computer.</span></span> <span data-ttu-id="eaed2-198">Ricordarsi di copiare CreditCardFile.txt. In caso contrario l'autenticatore della carta di credito non può convalidare le informazioni della carta di credito inviate dal client.</span><span class="sxs-lookup"><span data-stu-id="eaed2-198">Do not forget to copy CreditCardFile.txt; otherwise the credit card authenticator cannot validate credit card information sent from the client.</span></span> <span data-ttu-id="eaed2-199">Copiare i file Setup.bat e Cleanup.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-199">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="eaed2-200">È necessario disporre di un certificato server con il nome del soggetto che contiene il nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="eaed2-200">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="eaed2-201">È possibile crearne uno usando Setup.bat se si modifica la variabile `%SERVER_NAME%` con il nome host completo del computer sul quale è ospitato il servizio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-201">You can create one using the Setup.bat if you change the `%SERVER_NAME%` variable to fully-qualified name of the computer where the service is hosted.</span></span> <span data-ttu-id="eaed2-202">Si noti che il file Setup. bat deve essere eseguito in un prompt dei comandi di per gli sviluppatori per Visual Studio aperto con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="eaed2-202">Note that the Setup.bat file must be run in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>  
  
4. <span data-ttu-id="eaed2-203">Copiare il certificato server nell'archivio CurrentUser-TrustedPeople del client.</span><span class="sxs-lookup"><span data-stu-id="eaed2-203">Copy the server certificate into the CurrentUser-TrustedPeople store on the client.</span></span> <span data-ttu-id="eaed2-204">Questo passaggio è necessario solo se il certificato server non è emesso da un'autorità emittente attendibile.</span><span class="sxs-lookup"><span data-stu-id="eaed2-204">You must do this only if the server certificate is not issued by a trusted issuer.</span></span>  
  
5. <span data-ttu-id="eaed2-205">Nel file EchoServiceHost.cs modificare il valore del nome del soggetto del certificato per specificare un nome del computer completo anziché localhost.</span><span class="sxs-lookup"><span data-stu-id="eaed2-205">In the EchoServiceHost.cs file, change the value of the certificate subject name to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6. <span data-ttu-id="eaed2-206">Copiare i file del programma client dalla cartella \client\bin\, presente nella cartella specifica del linguaggio, nel computer client.</span><span class="sxs-lookup"><span data-stu-id="eaed2-206">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
7. <span data-ttu-id="eaed2-207">Nel file Client.cs modificare il valore dell'indirizzo dell'endpoint affinché corrisponda al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-207">In the Client.cs file, change the address value of the endpoint to match the new address of your service.</span></span>  
  
8. <span data-ttu-id="eaed2-208">Nel file Client.cs modificare il nome del soggetto del certificato X.509 del servizio affinché corrisponda al nome del computer completo dell'host remoto anziché localhost.</span><span class="sxs-lookup"><span data-stu-id="eaed2-208">In the Client.cs file change the subject name of the service X.509 certificate to match the fully-qualified computer name of the remote host instead of localhost.</span></span>  
  
9. <span data-ttu-id="eaed2-209">Sul computer client avviare Client.exe da una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="eaed2-209">On the client computer, launch Client.exe from a command prompt window.</span></span>  
  
10. <span data-ttu-id="eaed2-210">Se il client e il servizio non è in grado di comunicare, vedere [suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="eaed2-210">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="eaed2-211">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="eaed2-211">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="eaed2-212">Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="eaed2-212">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
