---
title: Migrazione dei servizi Web WSE 3.0 a WCF
ms.date: 03/30/2017
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
ms.openlocfilehash: fea56d5737b47dabd5632477b7daed23fcfaf249
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>Migrazione dei servizi Web WSE 3.0 a WCF
I vantaggi della migrazione dei servizi Web WSE 3.0 per Windows Communication Foundation (WCF) includono prestazioni migliorate e il supporto degli altri trasporti, scenari di sicurezza aggiuntive e WS-* specifiche. Un servizio Web che viene eseguita la migrazione da WSE 3.0 a WCF può subire fino a un miglioramento delle prestazioni di 200% e 400%. Per ulteriori informazioni sui trasporti supportati da WCF, vedere [scelta di un trasporto](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md). Per un elenco degli scenari supportati da WCF, vedere [comuni scenari di sicurezza](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md). Per un elenco delle specifiche che sono supportati da WCF, vedere [Guida di interoperabilità dei protocolli di servizi Web](../../../../docs/framework/wcf/feature-details/web-services-protocols-interoperability-guide.md).  
  
 Nelle sezioni seguenti forniscono istruzioni su come eseguire la migrazione di una funzionalità specifica di un servizio Web WSE 3.0 a WCF.  
  
## <a name="general"></a>Generale  
 Le applicazioni WSE 3.0 e WCF includono interoperabilità a livello di rete e un set comune di terminologia. Le applicazioni WSE 3.0 e WCF sono in transito a livello di interoperabilità in base al set di WS-* specifiche supportato da entrambe. Quando viene sviluppata un'applicazione WSE 3.0 o WCF è un set comune di terminologia, ad esempio i nomi delle asserzioni di sicurezza turnkey in WSE e le modalità di autenticazione.  
  
 Sebbene vi siano molte analogie tra WCF e ASP.NET o WSE 3.0 modelli di programmazione, sono diversi. Per informazioni dettagliate sul modello di programmazione WCF, vedere [ciclo di programmazione di base](../../../../docs/framework/wcf/basic-programming-lifecycle.md).  
  
> [!NOTE]
>  Eseguire la migrazione di un servizio Web WSE a WCF i [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) strumento può essere utilizzato per generare un client. Tuttavia, le interfacce e le classi contenute in questo client sono utilizzabili anche come base per un servizio WCF. L'attributo <xref:System.ServiceModel.OperationContractAttribute> delle interfacce che vengono generate viene applicato ai membri del contratto con la proprietà <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> impostata su `*`. Quando un client WSE chiama un servizio Web con questa impostazione, viene generata l'eccezione seguente: **Web.Services3.ResponseProcessingException: WSE910: si è verificato un errore durante l'elaborazione di un messaggio di risposta ed è possibile trovare l'errore in interna eccezione**. Per risolvere questo problema, impostare la proprietà <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> dell'attributo <xref:System.ServiceModel.OperationContractAttribute> su un valore diverso da `null`, ad esempio `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>Sicurezza  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>Servizi Web WSE 3.0 protetti mediante un file dei criteri  
 Servizi WCF possono usare un file di configurazione per proteggere un servizio e tale meccanismo è simile a un file dei criteri di WSE 3.0. Quando in WSE 3.0 si protegge un servizio Web tramite un file dei criteri, si utilizza un'asserzione di sicurezza turnkey oppure un'asserzione di criteri personalizzata. Le asserzioni di sicurezza turnkey eseguono mapping ravvicinato alla modalità di autenticazione di un elemento di associazione di sicurezza WCF. Non solo la modalità di autenticazione WCF e le asserzioni di sicurezza turnkey WSE 3.0 lo stesso nome o in modo analogo, proteggono i messaggi utilizzando gli stessi tipi di credenziale. Ad esempio, il `usernameForCertificate` asserzione di sicurezza turnkey in WSE 3.0 viene eseguito il mapping per il `UsernameForCertificate` modalità di autenticazione in WCF. Esempi di codice seguenti illustrano un criterio minimo che utilizza il `usernameForCertificate` asserzione di sicurezza turnkey in WSE 3.0 esegue il mapping a un `UsernameForCertificate` modalità di autenticazione in WCF in un'associazione personalizzata.  
  
 **WSE 3.0**  
  
```xml  
<policies>  
  <policy name="MyPolicy">  
    <usernameForCertificate messageProtectionOrder="SignBeforeEncrypt"  
                            requireDeriveKeys="true"/>  
  </policy>  
</policies>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <security authenticationMode="UserNameForCertificate"   
              messageProtectionOrder="SignBeforeEncrypt"  
              requireDerivedKeys="true"/>  
  </binding>  
</customBinding>  
```  
  
 Per migrare le impostazioni di sicurezza di un servizio Web WSE 3.0 che vengono specificate in un file di criteri a WCF, è necessario creare un'associazione personalizzata in un file di configurazione e deve essere impostato l'asserzione di sicurezza turnkey sulla relativa modalità di autenticazione equivalente. Quando i client WSE 3.0 comunicano con il servizio occorre inoltre configurare l'associazione personalizzata in modo che utilizzi la specifica WS-Addressing dell'agosto 2004. Quando il servizio WCF sottoposto a migrazione non richiede la comunicazione con i client WSE 3.0 e deve mantenere solo la parità di sicurezza, è consigliabile usare le associazioni WCF definiti dal sistema con impostazioni di sicurezza appropriate invece di creare un'associazione personalizzata.  
  
 Nella tabella seguente sono elencati i mapping tra un file dei criteri di WSE 3.0 e l'associazione personalizzata equivalente in WCF.  
  
|Asserzione di sicurezza turnkey di WSE 3.0|Configurazione dell'associazione personalizzata di WCF|  
|----------------------------------------|--------------------------------------|  
|\<usernameOverTransportSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate10Security / >|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<usernameForCertificateSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<anonymousForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<kerberosSecurity / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate11Security / >|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 Per ulteriori informazioni sulla creazione di associazioni personalizzate in WCF, vedere [associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>Servizi Web WSE 3.0 protetti mediante il codice dell'applicazione  
 Se si utilizza WSE 3.0 o WCF, è possono specificare i requisiti di sicurezza nel codice dell'applicazione anziché nella configurazione. Per eseguire questa operazione in WSE 3.0 occorre creare una classe che deriva dalla classe `Policy` e quindi aggiungere i requisiti chiamando il metodo `Add`. Per ulteriori informazioni su come specificare i requisiti di sicurezza nel codice, vedere [procedura: proteggere un servizio Web senza utilizzando un File di criteri](http://go.microsoft.com/fwlink/?LinkId=73747). In WCF, per specificare i requisiti di sicurezza nel codice, creare un'istanza del <xref:System.ServiceModel.Channels.BindingElementCollection> classe e aggiungere un'istanza di un <xref:System.ServiceModel.Channels.SecurityBindingElement> per il <xref:System.ServiceModel.Channels.BindingElementCollection>. Per impostare i requisiti delle asserzioni di sicurezza occorre utilizzare i metodi di supporto statici della modalità di autenticazione della classe <xref:System.ServiceModel.Channels.SecurityBindingElement>. Per ulteriori informazioni su come specificare i requisiti di sicurezza nel codice utilizzando WCF, vedere [procedura: creare un personalizzato associazione usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md) e [procedura: creare un elemento SecurityBindingElement per una specificata Modalità di autenticazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
### <a name="wse-30-custom-policy-assertion"></a>Asserzione di criteri personalizzata di WSE 3.0  
 In WSE 3.0 sono disponibili due tipi di asserzioni di criteri personalizzate: le asserzioni che proteggono i messaggi SOAP e quelle che non li proteggono. Le asserzioni di criteri che proteggono i messaggi SOAP derivano da WSE 3.0 `SecurityPolicyAssertion` classe e l'equivalente concettuale in WCF è il <xref:System.ServiceModel.Channels.SecurityBindingElement> classe.  
  
 Un punto importante da notare è che le asserzioni di sicurezza turnkey WSE 3.0 sono un subset delle modalità di autenticazione WCF. Se è stato creato un'asserzione di criteri personalizzato di WSE 3.0, potrebbe esserci una modalità di autenticazione WCF equivalente. Ad esempio, anziché fornire un'asserzione di sicurezza CertificateOverTransport equivalente all'asserzione di sicurezza turnkey `UsernameOverTransport`, WSE 3.0 utilizza un certificato X.509 per eseguire l'autenticazione client. Se è stata definita la propria asserzione di criteri personalizzata per questo scenario, WCF semplifica la migrazione. WCF definisce una modalità di autenticazione per questo scenario, in modo da poter sfruttare l'autenticazione statico metodi di supporto di modalità per configurare un WCF<xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
 Quando non è una modalità di autenticazione WCF che equivale a un'asserzione di criteri personalizzata che protegge i messaggi SOAP, derivare una classe da <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>WCF classi e specificare l'elemento di associazione equivalente. Per ulteriori informazioni, vedere [procedura: creare un personalizzato associazione usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Per convertire un'asserzione di criteri personalizzati che non è possibile protetta un messaggio SOAP, vedere [filtro](../../../../docs/framework/wcf/feature-details/filtering.md) e l'esempio [intercettatore di messaggi personalizzato](../../../../docs/framework/wcf/samples/custom-message-interceptor.md).  
  
### <a name="wse-30-custom-security-token"></a>Token di sicurezza personalizzato di WSE 3.0  
 Il modello di programmazione WCF per la creazione di un token personalizzato è diverso rispetto a WSE 3.0. Per informazioni dettagliate sulla creazione di un token personalizzato in WSE, vedere [la creazione di token di sicurezza personalizzato](http://go.microsoft.com/fwlink/?LinkID=73750). Per informazioni dettagliate sulla creazione di un token personalizzato in WCF, vedere [procedura: creare un Token personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
### <a name="wse-30-custom-token-manager"></a>Gestore del token personalizzato di WSE 3.0  
 Il modello di programmazione per la creazione di un gestore del token personalizzato è diverso in WCF WSE 3.0. Per informazioni dettagliate su come creare un gestore del token personalizzato e gli altri componenti necessari per un token di sicurezza personalizzato, vedere [procedura: creare un Token personalizzato](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
> [!NOTE]
>  Se è stato creato un oggetto personalizzato `UsernameToken` gestore del token di sicurezza, WCF fornisce un meccanismo più semplice per specificare la logica di autenticazione rispetto alla creazione di una protezione personalizzata gestore del token. Per ulteriori informazioni, vedere [procedura: utilizzare un nome utente personalizzata e convalida della Password](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md).  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>Servizi Web WSE 3.0 che utilizzano messaggi SOAP con codifica MTOM  
 Ad esempio un'applicazione WSE 3, un'applicazione WCF può specificare la codifica nella configurazione dei messaggi MTOM. Per eseguire la migrazione questa impostazione, aggiungere il [ \<mtomMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/mtommessageencoding.md) all'associazione per il servizio. Esempio di codice seguente viene illustrato come specificare la codifica MTOM in WSE 3.0 per un servizio equivalente in WCF.  
  
 **WSE 3.0**  
  
```xml  
<messaging>  
    <mtom clientMode="On"/>  
</messaging>  
```  
  
 **WCF**  
  
```xml  
<customBinding>  
  <binding name="MyBinding">  
    <mtomMessageEncoding/>  
  </binding>  
</customBinding>  
```  
  
## <a name="messaging"></a>Messaggistica  
  
### <a name="wse-30-applications-that-use-the-wse-messaging-api"></a>Applicazioni WSE 3.0 che utilizzano l'API del sistema di messaggistica di WSE  
 Quando si utilizza l'API del sistema di messaggistica di WSE per accedere in modo diretto ai dati XML scambiati fra il client e il servizio Web, l'applicazione può essere convertita in modo da utilizzare il formato POX (Plain Old XML). Per ulteriori dettagli su POX, vedere [l'interoperabilità con applicazioni POX](../../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md). Per ulteriori informazioni sull'API di messaggistica di WSE, vedere [invio e ricezione di messaggi con WSE messaggistica API SOAP](http://go.microsoft.com/fwlink/?LinkID=73755).  
  
## <a name="transports"></a>Trasporti  
  
### <a name="tcp"></a>TCP  
 Per impostazione predefinita, i client WSE 3.0 e i servizi Web che inviano messaggi SOAP utilizzando il trasporto TCP non di interoperabilità con client e servizi Web WCF. Questa incompatibilità è dovuta a differenze nella modalità di frame del protocollo TCP e si basa inoltre su motivi legati alle prestazioni. Tuttavia, un esempio WCF viene illustrato come implementare una sessione TCP personalizzata che interopera con WSE 3.0. Per informazioni dettagliate su questo esempio, vedere [trasporto: interoperabilità di WSE 3.0 TCP](../../../../docs/framework/wcf/samples/transport-wse-3-0-tcp-interoperability.md).  
  
 Per specificare che un'applicazione WCF utilizza il trasporto TCP, usare il [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
### <a name="custom-transport"></a>Trasporto personalizzato  
 L'equivalente di un trasporto personalizzato di WSE 3.0 in WCF è un'estensione di canale. Per informazioni dettagliate sulla creazione di un'estensione di canale, vedere [estendendo il livello del canale](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Ciclo di vita della programmazione di base](../../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 [Associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [Procedura: Creare un'associazione personalizzata usando SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Procedura: Creare un elemento SecurityBindingElement per una modalità di autenticazione specificata](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
