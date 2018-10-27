---
title: Modalità di autenticazione di SecurityBindingElement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 12300bf4-c730-4405-9f65-d286f68b5a43
ms.openlocfilehash: 2b1601bd84e92b5a39c5c4c91fdfe67537720430
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50045665"
---
# <a name="securitybindingelement-authentication-modes"></a>Modalità di autenticazione di SecurityBindingElement
Windows Communication Foundation (WCF) sono disponibili varie modalità con cui i client e servizi l'autenticazione reciproca. È possibile creare elementi di associazione di sicurezza per tali modalità di autenticazione utilizzando metodi statici sulla classe <xref:System.ServiceModel.Channels.SecurityBindingElement> o tramite configurazione. In questo argomento vengono brevemente descritte le 18 modalità di autenticazione.  
  
 Per un esempio di uso dell'elemento per una delle modalità di autenticazione, vedere [procedura: creare un elemento SecurityBindingElement per una modalità di autenticazione specificato](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## <a name="basic-configuration-programming"></a>Programmazione della configurazione di base  
 Nella procedura seguente viene illustrato come impostare la modalità di autenticazione in un file di configurazione.  
  
#### <a name="to-set-the-authentication-mode-in-configuration"></a>Per impostare la modalità di autenticazione nella configurazione  
  
1.  Per il [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento, aggiungere un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
2.  Come elemento figlio, aggiungere un [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento per il `<customBinding>` elemento.  
  
3.  Aggiungere un elemento `<security>` all'elemento `<binding>`.  
  
4.  Impostare l'attributo `authenticationMode` su uno dei valori descritti di seguito. Ad esempio, nel codice seguente la modalità viene impostata su `AnonymousForCertificate`.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="SecureCustomBinding">  
         <security authenticationMode ="AnonymousForCertificate" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
#### <a name="to-set-the-mode-programmatically"></a>Per impostare la modalità a livello di codice  
  
1.  Determinare il tipo restituito, che può essere uno dei seguenti: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
2.  Chiamare il metodo statico appropriato della classe <xref:System.ServiceModel.Channels.SecurityBindingElement>. Ad esempio, nel codice seguente viene chiamato il metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateAnonymousForCertificateBindingElement%2A>.  
  
     [!code-csharp[c_CustomBindingsAuthMode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#3)]
     [!code-vb[c_CustomBindingsAuthMode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#3)]  
  
3.  Utilizzare l'elemento di associazione per creare l'associazione personalizzata. Per altre informazioni, vedere [associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="mode-descriptions"></a>Descrizione delle modalità  
  
### <a name="anonymousforcertificate"></a>AnonymousForCertificate  
 In questa modalità di autenticazione il client è anonimo e il servizio viene autenticato utilizzando un certificato X.509. L'elemento di associazione di sicurezza è un elemento <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateAnonymousForCertificateBindingElement%2A>. In alternativa, impostare il `authenticationMode` attributo del <`security`> elemento `AnonymousForCertificate`.  
  
### <a name="anonymousforsslnegotiated"></a>AnonymousForSslNegotiated  
 In questa modalità di autenticazione il client è anonimo e il servizio viene autenticato utilizzando un certificato X.509 negoziato a runtime. L'elemento di associazione di sicurezza è un elemento <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSslNegotiationBindingElement%2A> quando viene passato un valore `false` per il primo parametro. In alternativa, impostare l'attributo `authenticationMode` su `AnonymousForSslNegotiated`.  
  
### <a name="certificateovertransport"></a>CertificateOverTransport  
 In questa modalità di autenticazione il client viene autenticato mediante un certificato X.509 che a livello SOAP viene considerato come un token di supporto di verifica dell'autenticità, ovvero un token che firma la firma del messaggio. Il servizio viene autenticato tramite un certificato X.509 a livello di trasporto. L'elemento di associazione di sicurezza è un elemento <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateCertificateOverTransportBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `CertificateOverTransport`.  
  
### <a name="issuedtoken"></a>IssuedToken  
 In questa modalità di autenticazione il client, anziché autenticarsi presso il servizio, si autentica presso un servizio token di sicurezza e riceve un token SAML che poi presenta al server per dimostrare la conoscenza di una chiave condivisa. Inoltre, anziché prevedere l'autenticazione del servizio presso il client, questa modalità ricorre al meccanismo seguente: il servizio token di sicurezza esegue la crittografia della chiave condivisa come parte del token emesso in modo che solo il servizio possa decifrare la chiave. L'elemento di associazione di sicurezza è un elemento <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `IssuedToken`.  
  
### <a name="issuedtokenforcertificate"></a>IssuedTokenForCertificate  
 In questa modalità di autenticazione il client, anziché autenticarsi presso il servizio, si autentica presso un servizio token di sicurezza e riceve un token SAML che poi presenta al server per dimostrare la conoscenza di una chiave condivisa. Il token emesso viene considerato a livello SOAP come un token di supporto di verifica dell'autenticità o un token che firma la firma del messaggio. Il client autentica il servizio tramite un certificato X.509. L'elemento di associazione di sicurezza è un elemento <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForCertificateBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `IssuedTokenForCertificate`.  
  
### <a name="issuedtokenforsslnegotiated"></a>IssuedTokenForSslNegotiated  
 In questa modalità di autenticazione il client, anziché autenticarsi presso il servizio, si autentica presso un servizio token di sicurezza e riceve un token SAML che poi presenta al server per dimostrare la conoscenza di una chiave condivisa. Il token emesso viene considerato a livello SOAP come un token di supporto di verifica dell'autenticità o un token che firma la firma del messaggio. Il servizio viene autenticato tramite l'uso di un certificato X.509. L'elemento di associazione di sicurezza è un elemento <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForSslBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `IssuedTokenForSslnegotiated`.  
  
### <a name="issuedtokenovertransport"></a>IssuedTokenOverTransport  
 In questa modalità di autenticazione il client, anziché autenticarsi presso il servizio, si autentica presso un servizio token di sicurezza e riceve un token SAML che poi presenta al server per dimostrare la conoscenza di una chiave condivisa. Il token emesso viene considerato a livello SOAP come un token di supporto di verifica dell'autenticità o un token che firma la firma del messaggio. Il servizio viene autenticato tramite un certificato X.509 a livello di trasporto. L'elemento di associazione di sicurezza è un elemento `TransportSecurityBindingElement` restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenOverTransportBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `IssuedTokenOverTransport`.  
  
### <a name="kerberos"></a>Kerberos  
 In questa modalità di autenticazione il client viene autenticato presso il servizio mediante un ticket Kerberos. Questo stesso ticket viene inoltre usato per autenticare il server. L'elemento di associazione di sicurezza è un elemento `SymmetricSecurityBindingElement` restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `Kerberos`.  
  
> [!NOTE]
>  Per utilizzare questa modalità di autenticazione, l'account del servizio deve essere associato a un nome dell'entità servizio (SPN). A tale scopo, eseguire il servizio sotto l'account Servizio di rete o sotto l'account di sistema locale. In alternativa, utilizzare lo strumento SetSpn.exe per creare un SPN per l'account del servizio. In entrambi i casi, il client deve utilizzare il SPN corretto nel [ \<servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) elemento, oppure usando il <xref:System.ServiceModel.EndpointAddress> costruttore. Per altre informazioni, vedere [identità del servizio e autenticazione](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
> [!NOTE]
>  Quando si utilizza la modalità di autenticazione `Kerberos`, i livelli di rappresentazione <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous> e <xref:System.Security.Principal.TokenImpersonationLevel.Delegation> non sono supportati.  
  
### <a name="kerberosovertransport"></a>KerberosOverTransport  
 In questa modalità di autenticazione il client viene autenticato presso il servizio mediante un ticket Kerberos. Il token Kerberos viene considerato a livello SOAP come un token di supporto di verifica dell'autenticità, ovvero un token che firma la firma del messaggio. Il servizio viene autenticato tramite un certificato X.509 a livello di trasporto. L'elemento di associazione di sicurezza è un elemento `TransportSecurityBindingElement` restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosOverTransportBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `KerberosOverTransport`.  
  
> [!NOTE]
>  Per utilizzare questa modalità di autenticazione, l'account del servizio deve essere associato a un SPN. A tale scopo, eseguire il servizio sotto l'account Servizio di rete o sotto l'account di sistema locale. In alternativa, utilizzare lo strumento SetSpn.exe per creare un SPN per l'account del servizio. In entrambi i casi, il client deve utilizzare il SPN corretto nel [ \<servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) elemento, oppure usando il <xref:System.ServiceModel.EndpointAddress> costruttore. Per altre informazioni, vedere [identità del servizio e autenticazione](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
### <a name="mutualcertificate"></a>MutualCertificate  
 In questa modalità di autenticazione il client viene autenticato mediante un certificato X.509 che a livello SOAP viene considerato come un token di supporto di verifica dell'autenticità, ovvero un token che firma la firma del messaggio. Anche il servizio viene autenticato tramite l'uso di un certificato X.509 L'elemento di associazione di sicurezza è un elemento `SymmetricSecurityBindingElement` restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `MutualCertificate`.  
  
### <a name="mutualcertificateduplex"></a>MutualCertificateDuplex  
 In questa modalità di autenticazione il client viene autenticato mediante un certificato X.509 che a livello SOAP viene considerato come un token di supporto di verifica dell'autenticità, ovvero un token che firma la firma del messaggio. Anche il servizio viene autenticato tramite l'uso di un certificato X.509 L'associazione è un elemento `AsymmetricSecurityBindingElement` restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateDuplexBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `MutualCertificateDuplex`.  
  
### <a name="mutualsslnegotiated"></a>MutualSslNegotiated  
 In questa modalità l'autenticazione del client e del servizio si basa sull'utilizzo di certificati X.509. L'elemento di associazione di sicurezza è un elemento `SymmetricSecurityBindingElement` restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSslNegotiationBindingElement%2A> quando viene passato un valore `true` per il primo parametro. In alternativa, impostare l'attributo `authenticationMode` su `MutualSslNegotiated`.  
  
### <a name="secureconversation"></a>SecureConversation  
 L'elemento di associazione di sicurezza è un elemento `SymmetricSecurityBindingElement` restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A>. Questo metodo considera un elemento <xref:System.ServiceModel.Channels.SecurityBindingElement> come parametro, che viene utilizzato durante l'inizializzazione per stabilire la sessione protetta. In alternativa, impostare l'attributo `authenticationMode` su `SecureConversation`.  
  
 Se non è specificata nessuna associazione del bootstrap, per il bootstratp viene utilizzata la modalità di autenticazione `SspiNegotiated`.  
  
### <a name="sspinegotiation"></a>SspiNegotiation  
 Questa modalità di autenticazione prevede l'utilizzo di un protocollo di negoziazione per eseguire l'autenticazione di client e server. Se possibile, viene utilizzato il protocollo Kerberos. In caso contrario viene utilizzato il protocollo NT LanMan (NTLM). L'elemento di associazione di sicurezza è un elemento `SymmetricSecurityBindingElement` restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `SspiNegotiated`.  
  
### <a name="sspinegotiatedovertransport"></a>SspiNegotiatedOverTransport  
 Questa modalità di autenticazione prevede l'utilizzo di un protocollo di negoziazione per eseguire l'autenticazione di client e server. Se possibile, viene utilizzato il protocollo Kerberos. In caso contrario, viene utilizzato il protocollo NTLM. Il token risultante viene considerato a livello SOAP come un token di supporto di verifica dell'autenticità, ovvero un token che firma la firma del messaggio. Il servizio viene autenticato ulteriormente a livello di trasporto tramite un certificato X.509. L'elemento di associazione di sicurezza è un elemento `TransportSecurityBindingElement` restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationOverTransportBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `SspiNegotiatedOverTransport`.  
  
### <a name="usernameforcertificate"></a>UserNameForCertificate  
 In questa modalità di autenticazione il client viene autenticato presso il servizio mediante un token nome utente che a livello SOAP viene considerato come un token di supporto firmato, ovvero un token firmato dalla firma del messaggio. Il client autentica il servizio tramite un certificato X.509. L'elemento di associazione di sicurezza è un elemento `SymmetricSecurityBindingElement` restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `UserNameForCertificate`.  
  
 Per la modalità di autenticazione `UserNameForCertificate`, il client e il servizio devono entrambi utilizzare WS-Security 1.1.  
  
### <a name="usernameforsslnegotiated"></a>UserNameForSslNegotiated  
 In questa modalità di autenticazione il client viene autenticato mediante un token nome utente che a livello SOAP viene considerato come un token di supporto firmato, ovvero un token firmato dalla firma del messaggio. Il servizio viene autenticato tramite l'uso di un certificato X.509. L'elemento di associazione di sicurezza è un elemento `SymmetricSecurityBindingElement` restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForSslBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `UserNameForSslNegotiated`.  
  
### <a name="usernameovertransport"></a>UserNameOverTransport  
 In questa modalità di autenticazione il client viene autenticato mediante un token nome utente che a livello SOAP viene considerato come un token di supporto firmato, ovvero un token firmato dalla firma del messaggio. Il servizio viene autenticato tramite un certificato X.509 a livello di trasporto. L'elemento di associazione di sicurezza è un elemento `TransportSecurityBindingElement` restituito dal metodo <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameOverTransportBindingElement%2A>. In alternativa, impostare l'attributo `authenticationMode` su `UserNameOverTransport`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
 [Procedura: Creare un elemento SecurityBindingElement per una modalità di autenticazione specificata](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
