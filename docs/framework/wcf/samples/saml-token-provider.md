---
title: Provider di token SAML
ms.date: 03/30/2017
ms.assetid: eb16e5e2-4c8d-4f61-a479-9c965fcec80c
ms.openlocfilehash: db1307b0f440f8bd55f1728b6645aec706dfe442
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602414"
---
# <a name="saml-token-provider"></a><span data-ttu-id="e2126-102">Provider di token SAML</span><span class="sxs-lookup"><span data-stu-id="e2126-102">SAML Token Provider</span></span>
<span data-ttu-id="e2126-103">Questo esempio dimostra come implementare un provider di token SAML client personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e2126-103">This sample demonstrates how to implement a custom client SAML token provider.</span></span> <span data-ttu-id="e2126-104">Un provider di token in Windows Communication Foundation (WCF) viene utilizzato per fornire le credenziali all'infrastruttura di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e2126-104">A token provider in Windows Communication Foundation (WCF) is used for supplying credentials to the security infrastructure.</span></span> <span data-ttu-id="e2126-105">In generale, il provider di token esamina la destinazione ed emette credenziali adatte in modo che l'infrastruttura di sicurezza possa proteggere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="e2126-105">The token provider in general examines the target and issues appropriate credentials so that the security infrastructure can secure the message.</span></span> <span data-ttu-id="e2126-106">WCF viene fornito con il provider di token di gestione credenziali predefinito.</span><span class="sxs-lookup"><span data-stu-id="e2126-106">WCF ships with the default Credential Manager Token Provider.</span></span> <span data-ttu-id="e2126-107">WCF viene inoltre fornito con un provider di token CardSpace.</span><span class="sxs-lookup"><span data-stu-id="e2126-107">WCF also ships with a CardSpace token provider.</span></span> <span data-ttu-id="e2126-108">I provider di token personalizzati sono utili nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2126-108">Custom token providers are useful in the following cases:</span></span>

- <span data-ttu-id="e2126-109">Se è disponibile un archivio di credenziali con cui questi provider di token non sono in grado di operare.</span><span class="sxs-lookup"><span data-stu-id="e2126-109">If you have a credential store that these token providers cannot operate with.</span></span>

- <span data-ttu-id="e2126-110">Se si desidera fornire un meccanismo personalizzato per la trasformazione delle credenziali dal punto in cui l'utente fornisce i dettagli su quando il framework client WCF usa le credenziali.</span><span class="sxs-lookup"><span data-stu-id="e2126-110">If you want to provide your own custom mechanism for transforming the credentials from the point when the user provides the details to when the WCF client framework uses the credentials.</span></span>

- <span data-ttu-id="e2126-111">Se si sta compilando un token personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e2126-111">If you are building a custom token.</span></span>

 <span data-ttu-id="e2126-112">Questo esempio illustra come compilare un provider di token personalizzato che consente l'uso di un token SAML ottenuto dall'esterno del framework client WCF.</span><span class="sxs-lookup"><span data-stu-id="e2126-112">This sample shows how to build a custom token provider that allows a SAML token obtained from outside of the WCF client framework to be used.</span></span>

 <span data-ttu-id="e2126-113">Per riassumere, questo esempio dimostra quanto segue.</span><span class="sxs-lookup"><span data-stu-id="e2126-113">To summarize, this sample demonstrates the following:</span></span>

- <span data-ttu-id="e2126-114">Come è possibile configurare un client con un provider personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e2126-114">How a client can be configured with a custom token provider.</span></span>

- <span data-ttu-id="e2126-115">Come è possibile passare un token SAML alle credenziali client personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e2126-115">How a SAML token can be passed to the custom client credentials.</span></span>

- <span data-ttu-id="e2126-116">Come viene fornito il token SAML al framework client WCF.</span><span class="sxs-lookup"><span data-stu-id="e2126-116">How the SAML token is provided to the WCF client framework.</span></span>

- <span data-ttu-id="e2126-117">Come viene autenticato il servizio dal client mediante il certificato X.509 del server.</span><span class="sxs-lookup"><span data-stu-id="e2126-117">How the server is authenticated by the client using the server's X.509 certificate.</span></span>

 <span data-ttu-id="e2126-118">Il servizio espone due endpoint per la comunicazione con il servizio, definito utilizzando il file di configurazione app. config. Ogni endpoint è costituito da un indirizzo, un'associazione e un contratto.</span><span class="sxs-lookup"><span data-stu-id="e2126-118">The service exposes two endpoints for communicating with the service, defined using the configuration file App.config. Each endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="e2126-119">L'associazione è configurata con una classe `wsFederationHttpBinding` standard che usa la sicurezza del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e2126-119">The binding is configured with a standard `wsFederationHttpBinding`, which uses Message security.</span></span> <span data-ttu-id="e2126-120">Un endpoint attende che il client si autentichi con un token SAML che usa una chiave di prova simmetrica mentre l'altro attende che il client si autentichi con un token SAML che usa una chiave di prova asimmetrica.</span><span class="sxs-lookup"><span data-stu-id="e2126-120">One endpoint expects the client to authenticate with a SAML token that uses a symmetric proof key while the other expects the client to authenticate with a SAML token that uses an asymmetric proof key.</span></span> <span data-ttu-id="e2126-121">Il servizio configura anche il certificato del servizio usando il comportamento `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="e2126-121">The service also configures the service certificate using `serviceCredentials` behavior.</span></span> <span data-ttu-id="e2126-122">Il comportamento `serviceCredentials` consente di configurare un certificato del servizio.</span><span class="sxs-lookup"><span data-stu-id="e2126-122">The `serviceCredentials` behavior allows you to configure a service certificate.</span></span> <span data-ttu-id="e2126-123">Un certificato del servizio viene usato da un client per autenticare il servizio e fornire protezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e2126-123">A service certificate is used by a client to authenticate the service and provide message protection.</span></span> <span data-ttu-id="e2126-124">La configurazione seguente fa riferimento al certificato "localhost" installato durante l'installazione dell'esempio come descritto nelle istruzioni fornite alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e2126-124">The following configuration references the "localhost" certificate installed during the sample setup as described in the setup instructions at the end of this topic.</span></span> <span data-ttu-id="e2126-125">Il comportamento `serviceCredentials` consente anche di configurare certificati che sono attendibili per la firma di token SAML.</span><span class="sxs-lookup"><span data-stu-id="e2126-125">The `serviceCredentials` behavior also allows you to configure certificates that are trusted to sign SAML tokens.</span></span> <span data-ttu-id="e2126-126">La configurazione seguente fa riferimento al certificato 'Alice' installato durante l'esempio.</span><span class="sxs-lookup"><span data-stu-id="e2126-126">The following configuration references the 'Alice' certificate installed during the sample.</span></span>

```xml
<system.serviceModel>
 <services>
  <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
   <host>
    <baseAddresses>
     <!-- configure base address provided by host -->
     <add
  baseAddress="http://localhost:8000/servicemodelsamples/service/" />
    </baseAddresses>
   </host>
   <!-- use base address provided by host -->
   <!-- Endpoint that expect SAML tokens with Symmetric proof keys -->
   <endpoint address="calc/symm"
             binding="wsFederationHttpBinding"
             bindingConfiguration="Binding1"
             contract="Microsoft.ServiceModel.Samples.ICalculator" />
   <!-- Endpoint that expect SAML tokens with Asymmetric proof keys -->
   <endpoint address="calc/asymm"
             binding="wsFederationHttpBinding"
             bindingConfiguration="Binding2"
             contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </service>
 </services>

 <bindings>
  <wsFederationHttpBinding>
   <!-- Binding that expect SAML tokens with Symmetric proof keys -->
   <binding name="Binding1">
    <security mode="Message">
     <message negotiateServiceCredential ="false"
              issuedKeyType="SymmetricKey"
              issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"  />
    </security>
   </binding>
   <!-- Binding that expect SAML tokens with Asymmetric proof keys -->
   <binding name="Binding2">
    <security mode="Message">
     <message negotiateServiceCredential ="false"
              issuedKeyType="AsymmetricKey"
              issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"  />
    </security>
   </binding>
  </wsFederationHttpBinding>
 </bindings>

 <behaviors>
  <serviceBehaviors>
   <behavior name="CalculatorServiceBehavior">
    <!--
    The serviceCredentials behavior allows one to define a service certificate.
    A service certificate is used by a client to authenticate the service and provide message protection.
    This configuration references the "localhost" certificate installed during the setup instructions.
    -->
    <serviceCredentials>
     <!-- Set allowUntrustedRsaIssuers to true to allow self-signed, asymmetric key based SAML tokens -->
     <issuedTokenAuthentication allowUntrustedRsaIssuers ="true" >
      <!-- Add Alice to the list of certs trusted to issue SAML tokens -->
      <knownCertificates>
       <add storeLocation="LocalMachine"
            storeName="TrustedPeople"
            x509FindType="FindBySubjectName"
            findValue="Alice"/>
      </knownCertificates>
     </issuedTokenAuthentication>
     <serviceCertificate storeLocation="LocalMachine"
                         storeName="My"
                         x509FindType="FindBySubjectName"
                         findValue="localhost"  />
    </serviceCredentials>
   </behavior>
  </serviceBehaviors>
 </behaviors>

</system.serviceModel>
```

 <span data-ttu-id="e2126-127">I passaggi seguenti illustrano come sviluppare un provider di token SAML personalizzato e integrarlo con WCF: Security Framework:</span><span class="sxs-lookup"><span data-stu-id="e2126-127">The following steps show how to develop a custom SAML token provider and integrate it with WCF: security framework:</span></span>

1. <span data-ttu-id="e2126-128">Scrivere un provider di token SAML personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e2126-128">Write a custom SAML token provider.</span></span>

     <span data-ttu-id="e2126-129">L'esempio implementa un provider di token SAML personalizzato che restituisce un token di sicurezza basato su un'asserzione SAML fornita in fase di costruzione.</span><span class="sxs-lookup"><span data-stu-id="e2126-129">The sample implements a custom SAML token provider that returns a security token based on a SAML assertion that is provided at construction time.</span></span>

     <span data-ttu-id="e2126-130">Per eseguire questa attività il provider di token personalizzato viene derivato dalla classe <xref:System.IdentityModel.Selectors.SecurityTokenProvider> ed esegue l'override del metodo <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2126-130">To perform this task, the custom token provider is derived from the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A> method.</span></span> <span data-ttu-id="e2126-131">Questo metodo creare e restituisce un nuovo `SecurityToken`.</span><span class="sxs-lookup"><span data-stu-id="e2126-131">This method creates and returns a new `SecurityToken`.</span></span>

    ```csharp
    protected override SecurityToken GetTokenCore(TimeSpan timeout)
    {
     // Create a SamlSecurityToken from the provided assertion
     SamlSecurityToken samlToken = new SamlSecurityToken(assertion);

     // Create a SecurityTokenSerializer that will be used to
     // serialize the SamlSecurityToken
     WSSecurityTokenSerializer ser = new WSSecurityTokenSerializer();
     // Create a memory stream to write the serialized token into
     // Use an initial size of 64Kb
     MemoryStream s = new MemoryStream(UInt16.MaxValue);

     // Create an XmlWriter over the stream
     XmlWriter xw = XmlWriter.Create(s);

     // Write the SamlSecurityToken into the stream
     ser.WriteToken(xw, samlToken);

     // Seek back to the beginning of the stream
     s.Seek(0, SeekOrigin.Begin);

     // Load the serialized token into a DOM
     XmlDocument dom = new XmlDocument();
     dom.Load(s);

     // Create a KeyIdentifierClause for the SamlSecurityToken
     SamlAssertionKeyIdentifierClause samlKeyIdentifierClause = samlToken.CreateKeyIdentifierClause<SamlAssertionKeyIdentifierClause>();

    // Return a GenericXmlToken from the XML for the
    // SamlSecurityToken, the proof token, the valid from and valid
    // until times from the assertion and the key identifier clause
    // created above
    return new GenericXmlSecurityToken(dom.DocumentElement, proofToken, assertion.Conditions.NotBefore, assertion.Conditions.NotOnOrAfter, samlKeyIdentifierClause, samlKeyIdentifierClause, null);
    }
    ```

2. <span data-ttu-id="e2126-132">Scrivere il gestore di token di sicurezza personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e2126-132">Write custom security token manager.</span></span>

     <span data-ttu-id="e2126-133">La classe <xref:System.IdentityModel.Selectors.SecurityTokenManager> viene usata per creare <xref:System.IdentityModel.Selectors.SecurityTokenProvider> per il <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> specifico che viene passato nel metodo `CreateSecurityTokenProvider`.</span><span class="sxs-lookup"><span data-stu-id="e2126-133">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> class is used to create <xref:System.IdentityModel.Selectors.SecurityTokenProvider> for specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> that is passed to it in `CreateSecurityTokenProvider` method.</span></span> <span data-ttu-id="e2126-134">Viene inoltre usato un gestore del token di sicurezza per creare autenticatori del token e serializzatori del token, che però non sono trattati in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="e2126-134">A security token manager is also used to create token authenticators and token serializer, but those are not covered by this sample.</span></span> <span data-ttu-id="e2126-135">In questo esempio il gestore del token di sicurezza personalizzato eredita dalla classe <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> ed esegue l'override del metodo `CreateSecurityTokenProvider` per restituire il provider di token SAML personalizzato quando i requisiti del token passati indicano che il token SAML è richiesto.</span><span class="sxs-lookup"><span data-stu-id="e2126-135">In this sample the custom security token manager inherits from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenProvider` method to return the custom SAML token provider when the passed token requirements indicate that the SAML token is requested.</span></span> <span data-ttu-id="e2126-136">Se la classe delle credenziali client (vedere il passaggio 3) non ha specificato un'asserzione, il gestore del token di sicurezza crea un'istanza appropriata.</span><span class="sxs-lookup"><span data-stu-id="e2126-136">If the client credentials class (see step 3) has not specified an assertion, the security token manager creates an appropriate instance.</span></span>

    ```csharp
    public class SamlSecurityTokenManager : ClientCredentialsSecurityTokenManager
    {
     SamlClientCredentials samlClientCredentials;

     public SamlSecurityTokenManager ( SamlClientCredentials samlClientCredentials)
      : base(samlClientCredentials)
     {
      // Store the creating client credentials
      this.samlClientCredentials = samlClientCredentials;
     }

     public override SecurityTokenProvider CreateSecurityTokenProvider ( SecurityTokenRequirement tokenRequirement )
     {
      // If token requirement matches SAML token return the
      // custom SAML token provider
      if (tokenRequirement.TokenType == SecurityTokenTypes.Saml ||
          tokenRequirement.TokenType == "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1")
      {
       // Retrieve the SAML assertion and proof token from the
       // client credentials
       SamlAssertion assertion = this.samlClientCredentials.Assertion;
       SecurityToken prooftoken = this.samlClientCredentials.ProofToken;

       // If either the assertion of proof token is null...
       if (assertion == null || prooftoken == null)
       {
        // ...get the SecurityBindingElement and then the
        // specified algorithm suite
        SecurityBindingElement sbe = null;
        SecurityAlgorithmSuite sas = null;

        if ( tokenRequirement.TryGetProperty<SecurityBindingElement> ( "http://schemas.microsoft.com/ws/2006/05/servicemodel/securitytokenrequirement/SecurityBindingElement", out sbe))
        {
         sas = sbe.DefaultAlgorithmSuite;
        }

        // If the token requirement is for a SymmetricKey based token..
        if (tokenRequirement.KeyType == SecurityKeyType.SymmetricKey)
        {
         // Create a symmetric proof token
         prooftoken = SamlUtilities.CreateSymmetricProofToken ( tokenRequirement.KeySize );
         // and a corresponding assertion based on the claims specified in the client credentials
         assertion = SamlUtilities.CreateSymmetricKeyBasedAssertion ( this.samlClientCredentials.Claims, new X509SecurityToken ( samlClientCredentials.ClientCertificate.Certificate ), new X509SecurityToken ( samlClientCredentials.ServiceCertificate.DefaultCertificate ), (BinarySecretSecurityToken)prooftoken, sas);
        }
        // otherwise...
        else
        {
         // Create an asymmetric proof token
         prooftoken = SamlUtilities.CreateAsymmetricProofToken();
         // and a corresponding assertion based on the claims
         // specified in the client credentials
         assertion = SamlUtilities.CreateAsymmetricKeyBasedAssertion ( this.samlClientCredentials.Claims, prooftoken, sas );
        }
       }

       // Create a SamlSecurityTokenProvider based on the assertion and proof token
       return new SamlSecurityTokenProvider(assertion, prooftoken);
      }
      // otherwise use base implementation
      else
      {
       return base.CreateSecurityTokenProvider(tokenRequirement);
      }
    }
    ```

3. <span data-ttu-id="e2126-137">Scrivere una credenziale client personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e2126-137">Write a custom client credential.</span></span>

     <span data-ttu-id="e2126-138">La classe delle credenziali client viene  usata per rappresentare le credenziali configurate per il proxy client e crea un gestore del token di sicurezza usato per ottenere gli autenticatori del token, i provider di token e il serializzatore di token.</span><span class="sxs-lookup"><span data-stu-id="e2126-138">Client credentials class is used to represent the credentials that are configured for the client proxy and creates a security token manager that is used to obtain token authenticators, token providers and token serializer.</span></span>

    ```csharp
    public class SamlClientCredentials : ClientCredentials
    {
     ClaimSet claims;
     SamlAssertion assertion;
     SecurityToken proofToken;

     public SamlClientCredentials() : base()
     {
      // Set SupportInteractive to false to suppress Cardspace UI
      base.SupportInteractive = false;
     }

     protected SamlClientCredentials(SamlClientCredentials other) : base ( other )
     {
      // Just do reference copy given sample nature
      this.assertion = other.assertion;
      this.claims = other.claims;
      this.proofToken = other.proofToken;
     }

     public SamlAssertion Assertion { get { return assertion; } set { assertion = value; } }

     public SecurityToken ProofToken { get { return proofToken; } set { proofToken = value; } }
     public ClaimSet Claims { get { return claims; } set { claims = value; } }

     protected override ClientCredentials CloneCore()
     {
      return new SamlClientCredentials(this);
     }

     public override SecurityTokenManager CreateSecurityTokenManager()
     {
      // return custom security token manager
      return new SamlSecurityTokenManager(this);
     }
    }
    ```

4. <span data-ttu-id="e2126-139">Configurare il client per l'uso della credenziale client personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e2126-139">Configure the client to use the custom client credential.</span></span>

     <span data-ttu-id="e2126-140">L'esempio elimina la classe della credenziale client predefinita e fornisce la nuova classe della credenziale client così il client possa usare la credenziale client personalizzata.</span><span class="sxs-lookup"><span data-stu-id="e2126-140">The sample deletes the default client credential class and supplies the new client credential class so the client can use the custom client credential.</span></span>

    ```csharp
    // Create new credentials class
    SamlClientCredentials samlCC = new SamlClientCredentials();

    // Set the client certificate. This is the cert that will be used to sign the SAML token in the symmetric proof key case
    samlCC.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "Alice");

    // Set the service certificate. This is the cert that will be used to encrypt the proof key in the symmetric proof key case
    samlCC.ServiceCertificate.SetDefaultCertificate(StoreLocation.CurrentUser, StoreName.TrustedPeople, X509FindType.FindBySubjectName, "localhost");

    // Create some claims to put in the SAML assertion
    IList<Claim> claims = new List<Claim>();
    claims.Add(Claim.CreateNameClaim(samlCC.ClientCertificate.Certificate.Subject));
    ClaimSet claimset = new DefaultClaimSet(claims);
    samlCC.Claims = claimset;

    // set new credentials
    client.ChannelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));
    client.ChannelFactory.Endpoint.Behaviors.Add(samlCC);
    ```

 <span data-ttu-id="e2126-141">Nel servizio, vengono visualizzate le richieste associate al chiamante.</span><span class="sxs-lookup"><span data-stu-id="e2126-141">On the service, the claims associated with the caller are displayed.</span></span> <span data-ttu-id="e2126-142">Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client.</span><span class="sxs-lookup"><span data-stu-id="e2126-142">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="e2126-143">Premere INVIO nella finestra del client per arrestare il client.</span><span class="sxs-lookup"><span data-stu-id="e2126-143">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="e2126-144">File batch di installazione</span><span class="sxs-lookup"><span data-stu-id="e2126-144">Setup Batch File</span></span>
 <span data-ttu-id="e2126-145">Il file batch Setup.bat incluso con questo esempio consente di configurare il server con il certificato attinente per eseguire un'applicazione indipendente che richiede sicurezza server basata su certificato.</span><span class="sxs-lookup"><span data-stu-id="e2126-145">The Setup.bat batch file included with this sample allows you to configure the server with the relevant certificate to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="e2126-146">Questo file batch deve essere modificato per funzionare tra computer diversi o nel caso in cui non sia ospitato.</span><span class="sxs-lookup"><span data-stu-id="e2126-146">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

 <span data-ttu-id="e2126-147">Di seguito viene fornita una breve panoramica delle varie sezioni dei file batch in modo che possano essere modificate per l'esecuzione nella configurazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="e2126-147">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>

- <span data-ttu-id="e2126-148">Creazione del certificato server:</span><span class="sxs-lookup"><span data-stu-id="e2126-148">Creating the server certificate:</span></span>

     <span data-ttu-id="e2126-149">Le righe seguenti del file batch Setup.bat creano il certificato server da usare.</span><span class="sxs-lookup"><span data-stu-id="e2126-149">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="e2126-150">La variabile `%SERVER_NAME%` specifica il nome del server.</span><span class="sxs-lookup"><span data-stu-id="e2126-150">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="e2126-151">Modificare questa variabile per specificare nome del server.</span><span class="sxs-lookup"><span data-stu-id="e2126-151">Change this variable to specify your own server name.</span></span> <span data-ttu-id="e2126-152">Il valore predefinito in questo file batch è localhost.</span><span class="sxs-lookup"><span data-stu-id="e2126-152">The default value in this batch file is localhost.</span></span>

     <span data-ttu-id="e2126-153">Il certificato viene memorizzato nell'archivio personale nel percorso di archivio LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="e2126-153">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss My -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="e2126-154">Installazione del certificato server nell'archivio certificati attendibile del client:</span><span class="sxs-lookup"><span data-stu-id="e2126-154">Installing the server certificate into the client's trusted certificate store:</span></span>

     <span data-ttu-id="e2126-155">Le righe seguenti nel file batch Setup.bat copiano il certificato server nell'archivio di persone attendibile del client.</span><span class="sxs-lookup"><span data-stu-id="e2126-155">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="e2126-156">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="e2126-156">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="e2126-157">Se è già disponibile un certificato impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il popolamento dell'archivio certificati client con il certificato server non è necessario.</span><span class="sxs-lookup"><span data-stu-id="e2126-157">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r LocalMachine -s TrustedPeople
    ```

- <span data-ttu-id="e2126-158">Creazione del certificato emittente:</span><span class="sxs-lookup"><span data-stu-id="e2126-158">Creating the issuer certificate.</span></span>

     <span data-ttu-id="e2126-159">Le righe seguenti del file batch Setup.bat creano il certificato emittente da usare.</span><span class="sxs-lookup"><span data-stu-id="e2126-159">The following lines from the Setup.bat batch file create the issuer certificate to be used.</span></span> <span data-ttu-id="e2126-160">La variabile `%USER_NAME%` specifica il nome dell'emittente.</span><span class="sxs-lookup"><span data-stu-id="e2126-160">The `%USER_NAME%` variable specifies the issuer name.</span></span> <span data-ttu-id="e2126-161">Modificare questa variabile per specificare nome dell'emittente.</span><span class="sxs-lookup"><span data-stu-id="e2126-161">Change this variable to specify your own issuer name.</span></span> <span data-ttu-id="e2126-162">Il valore predefinito in questo file batch è Alice.</span><span class="sxs-lookup"><span data-stu-id="e2126-162">The default value in this batch file is Alice.</span></span>

     <span data-ttu-id="e2126-163">Il certificato viene memorizzato nell'archivio personale nel percorso di archivio LocalUser.</span><span class="sxs-lookup"><span data-stu-id="e2126-163">The certificate is stored in My store under the CurrentUser store location.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr CurrentUser -ss My -a sha1 -n CN=%USER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="e2126-164">Installazione del certificato emittente nell'archivio certificati attendibile del server:</span><span class="sxs-lookup"><span data-stu-id="e2126-164">Installing the issuer certificate into the server's trusted certificate store.</span></span>

     <span data-ttu-id="e2126-165">Le righe seguenti nel file batch Setup.bat copiano il certificato server nell'archivio di persone attendibile del client.</span><span class="sxs-lookup"><span data-stu-id="e2126-165">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="e2126-166">Questo passaggio è necessario perché certificati generati da Makecert.exe non sono considerati implicitamente attendibili dal sistema client.</span><span class="sxs-lookup"><span data-stu-id="e2126-166">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="e2126-167">Se è già disponibile un certificato che impostato come radice in un certificato radice client attendibile, ad esempio un certificato rilasciato da Microsoft, il passaggio della popolazione dell'archivio certificati server con il certificato emittente  non è necessario.</span><span class="sxs-lookup"><span data-stu-id="e2126-167">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the server certificate store with the issuer certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r CurrentUser -s My -c -n %USER_NAME% -r LocalMachine -s TrustedPeople
    ```

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="e2126-168">Per impostare e compilare l'esempio</span><span class="sxs-lookup"><span data-stu-id="e2126-168">To set up and build the sample</span></span>

1. <span data-ttu-id="e2126-169">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e2126-169">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="e2126-170">Per compilare la soluzione, seguire le istruzioni riportate in [compilazione degli esempi di Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e2126-170">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e2126-171">Se si usa Svcutil.exe per rigenerare la configurazione di questo esempio, assicurarsi di modificare il nome dell'endpoint nella configurazione client in modo che corrisponda al codice client.</span><span class="sxs-lookup"><span data-stu-id="e2126-171">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="e2126-172">Per eseguire l'esempio nello stesso computer</span><span class="sxs-lookup"><span data-stu-id="e2126-172">To run the sample on the same computer</span></span>

1. <span data-ttu-id="e2126-173">Eseguire Setup. bat dalla cartella di installazione dell'esempio all'interno di un prompt dei comandi di Visual Studio 2012 eseguire con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="e2126-173">Run Setup.bat from the sample installation folder inside a Visual Studio 2012 command prompt run with administrator privileges.</span></span> <span data-ttu-id="e2126-174">In questo modo vengono installati tutti i certificati necessari per l'esecuzione dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="e2126-174">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e2126-175">Il file batch Setup. bat è progettato per essere eseguito da un prompt dei comandi di Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="e2126-175">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="e2126-176">La variabile di ambiente PATH impostata nel prompt dei comandi di Visual Studio 2012 punta alla directory che contiene i file eseguibili richiesti dallo script Setup. bat.</span><span class="sxs-lookup"><span data-stu-id="e2126-176">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2. <span data-ttu-id="e2126-177">Avviare Service.exe da service\bin.</span><span class="sxs-lookup"><span data-stu-id="e2126-177">Launch Service.exe from service\bin.</span></span>  
  
3. <span data-ttu-id="e2126-178">Avviare Client.exe da \client\bin.</span><span class="sxs-lookup"><span data-stu-id="e2126-178">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="e2126-179">L'attività del client viene visualizzata nella finestra dell'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="e2126-179">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="e2126-180">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="e2126-180">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="e2126-181">Per eseguire l'esempio tra più computer</span><span class="sxs-lookup"><span data-stu-id="e2126-181">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="e2126-182">Creare una directory sul computer del servizio per i file binari del servizio.</span><span class="sxs-lookup"><span data-stu-id="e2126-182">Create a directory on the service computer for the service binaries.</span></span>  
  
2. <span data-ttu-id="e2126-183">Copiare i file di programma del servizio nella directory del servizio sul computer relativo.</span><span class="sxs-lookup"><span data-stu-id="e2126-183">Copy the service program files to the service directory on the service computer.</span></span> <span data-ttu-id="e2126-184">Copiare i file Setup.bat e Cleanup.bat nel computer del servizio.</span><span class="sxs-lookup"><span data-stu-id="e2126-184">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="e2126-185">È necessario disporre di un certificato server con il nome del soggetto che contiene il nome di dominio completo del computer.</span><span class="sxs-lookup"><span data-stu-id="e2126-185">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="e2126-186">Il file Service.exe.config deve essere aggiornato per riflettere il nome del nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="e2126-186">The Service.exe.config file must be updated to reflect this new certificate name.</span></span> <span data-ttu-id="e2126-187">È possibile creare il certificato server modificando il file batch Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="e2126-187">You can create server certificate by modifying the Setup.bat batch file.</span></span> <span data-ttu-id="e2126-188">Si noti che è necessario eseguire il file Setup. bat in una Prompt dei comandi per gli sviluppatori per la finestra di Visual Studio aperta con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="e2126-188">Note that the setup.bat file must be run in a Developer Command Prompt for Visual Studio window opened with administrator privileges.</span></span> <span data-ttu-id="e2126-189">È necessario impostare la variabile `%SERVER_NAME%` sul nome host completo del computer usato per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="e2126-189">You must set the `%SERVER_NAME%` variable to the fully-qualified host name of the computer that is used to host the service.</span></span>  
  
4. <span data-ttu-id="e2126-190">Copiare il certificato server nell'archivio CurrentUser-TrustedPeople del client.</span><span class="sxs-lookup"><span data-stu-id="e2126-190">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="e2126-191">Questo passaggio non è necessario quando il certificato server è emesso da un'autorità emittente client attendibile.</span><span class="sxs-lookup"><span data-stu-id="e2126-191">This step is not necessary when the server certificate is issued by a client trusted issuer.</span></span>  
  
5. <span data-ttu-id="e2126-192">Nel file Service.exe.config sul computer del servizio modificare il valore dell'indirizzo di base per specificare un nome del computer completo anziché localhost.</span><span class="sxs-lookup"><span data-stu-id="e2126-192">In the Service.exe.config file on the service computer, change the value of the base address to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6. <span data-ttu-id="e2126-193">Sul computer del servizio eseguire Service.exe da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="e2126-193">On the service computer, run Service.exe from a command prompt.</span></span>  
  
7. <span data-ttu-id="e2126-194">Copiare i file del programma client dalla cartella \client\bin\, presente nella cartella specifica del linguaggio, nel computer client.</span><span class="sxs-lookup"><span data-stu-id="e2126-194">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
8. <span data-ttu-id="e2126-195">Nel file Client.exe.config presente nel computer client modificare il valore dell'indirizzo della definizione dell'endpoint in base al nuovo indirizzo del servizio.</span><span class="sxs-lookup"><span data-stu-id="e2126-195">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="e2126-196">Sul computer client avviare `Client.exe` da una finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="e2126-196">On the client computer, launch `Client.exe` from a command prompt window.</span></span>  
  
10. <span data-ttu-id="e2126-197">Se il client e il servizio non sono in grado di comunicare, vedere [Suggerimenti per la risoluzione dei problemi per gli esempi di WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="e2126-197">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="e2126-198">Per eseguire la pulizia dopo l'esempio</span><span class="sxs-lookup"><span data-stu-id="e2126-198">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="e2126-199">Eseguire Cleanup.bat nella cartella degli esempi una volta completato l'esempio.</span><span class="sxs-lookup"><span data-stu-id="e2126-199">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
