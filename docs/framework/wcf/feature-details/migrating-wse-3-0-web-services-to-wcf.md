---
title: Migrazione dei servizi Web WSE 3.0 a WCF
ms.date: 03/30/2017
ms.assetid: 7bc5fff7-a2b2-4dbc-86cc-ecf73653dcdc
ms.openlocfilehash: ecf27c227b3e39d0c449a1d2ff32dc5bd59c750b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598788"
---
# <a name="migrating-wse-30-web-services-to-wcf"></a>Migrazione dei servizi Web WSE 3.0 a WCF
I vantaggi della migrazione dei servizi Web WSE 3,0 al Windows Communication Foundation (WCF) includono prestazioni migliorate e supporto per trasporti aggiuntivi, scenari di sicurezza aggiuntivi e specifiche WS-*. Un servizio Web di cui è stata eseguita la migrazione da WSE 3,0 a WCF può avere un miglioramento delle prestazioni compreso tra 200 e 400%. Per ulteriori informazioni sui trasporti supportati da WCF, vedere [scelta di un trasporto](choosing-a-transport.md). Per un elenco degli scenari supportati da WCF, vedere [scenari di sicurezza comuni](common-security-scenarios.md). Per un elenco delle specifiche supportate da WCF, vedere la Guida all' [interoperabilità dei protocolli dei servizi Web](web-services-protocols-interoperability-guide.md).  
  
 Nelle sezioni seguenti vengono fornite indicazioni su come eseguire la migrazione di una funzionalità specifica di un servizio Web WSE 3,0 in WCF.  
  
## <a name="general"></a>Generale  
 Le applicazioni WSE 3,0 e WCF includono l'interoperabilità a livello di rete e un set comune di terminologia. Le applicazioni WSE 3,0 e WCF sono interoperabili a livello di rete in base al set di specifiche WS-* supportate. Quando si sviluppa un'applicazione WSE 3,0 o WCF, è disponibile un set comune di terminologia, ad esempio i nomi delle asserzioni di sicurezza chiavi in mano in WSE e le modalità di autenticazione.  
  
 Sebbene esistano molti aspetti simili tra i modelli di programmazione WCF e ASP.NET o WSE 3,0, sono diversi. Per informazioni dettagliate sul modello di programmazione WCF, vedere [Basic Programming Lifecycle](../basic-programming-lifecycle.md).  
  
> [!NOTE]
> Per eseguire la migrazione di un servizio Web WSE a WCF, è possibile utilizzare lo strumento [ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) per generare un client. Tuttavia, le interfacce e le classi contenute in questo client sono utilizzabili anche come base per un servizio WCF. L'attributo <xref:System.ServiceModel.OperationContractAttribute> delle interfacce che vengono generate viene applicato ai membri del contratto con la proprietà <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> impostata su `*`. Quando un client WSE chiama un servizio Web con questa impostazione, viene generata l'eccezione seguente: **Web. services3. ResponseProcessingException: WSE910: si è verificato un errore durante l'elaborazione di un messaggio di risposta ed è possibile trovare l'errore nell'eccezione interna**. Per risolvere questo problema, impostare la proprietà <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> dell'attributo <xref:System.ServiceModel.OperationContractAttribute> su un valore diverso da `null`, ad esempio `http://Microsoft.WCF.Documentation/ResponseToOCAMethod`.  
  
## <a name="security"></a>Sicurezza  
  
### <a name="wse-30-web-services-that-are-secured-using-a-policy-file"></a>Servizi Web WSE 3.0 protetti mediante un file dei criteri  
 I servizi WCF possono usare un file di configurazione per proteggere un servizio e questo meccanismo è simile a un file di criteri WSE 3,0. Quando in WSE 3.0 si protegge un servizio Web tramite un file dei criteri, si utilizza un'asserzione di sicurezza turnkey oppure un'asserzione di criteri personalizzata. Le asserzioni di sicurezza chiavi in mano vengono mappate strettamente alla modalità di autenticazione di un elemento di associazione di sicurezza WCF. Non solo le modalità di autenticazione WCF e le asserzioni di sicurezza di WSE 3,0, denominate allo stesso modo o allo stesso modo, proteggono i messaggi usando gli stessi tipi di credenziale. Ad esempio, l' `usernameForCertificate` asserzione di sicurezza chiavi in mano in WSE 3,0 esegue il mapping alla `UsernameForCertificate` modalità di autenticazione in WCF. Gli esempi di codice seguenti illustrano in che modo un criterio minimo che usa l' `usernameForCertificate` asserzione di sicurezza chiavi in mano in WSE 3,0 esegue il mapping a una `UsernameForCertificate` modalità di autenticazione in WCF in un'associazione personalizzata.  
  
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
  
 Per eseguire la migrazione delle impostazioni di sicurezza di un servizio Web WSE 3,0 specificato in un file di criteri in WCF, è necessario creare un'associazione personalizzata in un file di configurazione e l'asserzione di sicurezza chiavi in mano deve essere impostata sulla modalità di autenticazione equivalente. Quando i client WSE 3.0 comunicano con il servizio occorre inoltre configurare l'associazione personalizzata in modo che utilizzi la specifica WS-Addressing dell'agosto 2004. Quando il servizio WCF migrato non richiede la comunicazione con i client WSE 3,0 e deve mantenere solo la parità di sicurezza, è consigliabile utilizzare le associazioni definite dal sistema WCF con le impostazioni di sicurezza appropriate anziché creare un'associazione personalizzata.  
  
 Nella tabella seguente viene elencato il mapping tra un file di criteri WSE 3,0 e l'associazione personalizzata equivalente in WCF.  
  
|Asserzione di sicurezza turnkey di WSE 3.0|Configurazione dell'associazione personalizzata di WCF|  
|----------------------------------------|--------------------------------------|  
|\<usernameOverTransportSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UserNameOverTransport" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate10Security />|`<customBinding>   <binding name="MyBinding">     <security messageSecurityVersion="WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10" authenticationMode="MutualCertificate" />     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<usernameForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="UsernameForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<anonymousForCertificateSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="AnonymousForCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<kerberosSecurity />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="Kerberos"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
|\<mutualCertificate11Security />|`<customBinding>   <binding name="MyBinding">     <security authenticationMode="MutualCertificate"/>     <textMessageEncoding messageVersion="Soap12WSAddressingAugust2004" />   </binding> </customBinding>`|  
  
 Per ulteriori informazioni sulla creazione di associazioni personalizzate in WCF, vedere [associazioni personalizzate](../extending/custom-bindings.md).  
  
### <a name="wse-30-web-services-that-are-secured-using-application-code"></a>Servizi Web WSE 3.0 protetti mediante il codice dell'applicazione  
 Se si usa WSE 3,0 o WCF, i requisiti di sicurezza possono essere specificati nel codice dell'applicazione anziché nella configurazione. Per eseguire questa operazione in WSE 3.0 occorre creare una classe che deriva dalla classe `Policy` e quindi aggiungere i requisiti chiamando il metodo `Add`. Per altri dettagli su come specificare i requisiti di sicurezza nel codice, vedere [procedura: proteggere un servizio Web senza usare un file di criteri](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa528763(v=msdn.10)). In WCF, per specificare i requisiti di sicurezza nel codice, creare un'istanza della <xref:System.ServiceModel.Channels.BindingElementCollection> classe e aggiungere un'istanza di <xref:System.ServiceModel.Channels.SecurityBindingElement> a <xref:System.ServiceModel.Channels.BindingElementCollection> . Per impostare i requisiti delle asserzioni di sicurezza occorre utilizzare i metodi di supporto statici della modalità di autenticazione della classe <xref:System.ServiceModel.Channels.SecurityBindingElement>. Per altre informazioni su come specificare i requisiti di sicurezza nel codice con WCF, vedere [procedura: creare un'associazione personalizzata usando SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md) e [procedura: creare un oggetto SecurityBindingElement per una modalità di autenticazione specificata](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
### <a name="wse-30-custom-policy-assertion"></a>Asserzione di criteri personalizzata di WSE 3.0  
 In WSE 3.0 sono disponibili due tipi di asserzioni di criteri personalizzate: le asserzioni che proteggono i messaggi SOAP e quelle che non li proteggono. Le asserzioni di criteri che proteggono i messaggi SOAP derivano dalla classe WSE 3,0 `SecurityPolicyAssertion` e l'equivalente concettuale in WCF è la <xref:System.ServiceModel.Channels.SecurityBindingElement> classe.  
  
 Un punto importante da tenere presente è che le asserzioni di sicurezza chiavi in mano di WSE 3,0 sono un subset delle modalità di autenticazione WCF. Se è stata creata un'asserzione di criteri personalizzata in WSE 3,0, potrebbe essere presente una modalità di autenticazione WCF equivalente. Ad esempio, anziché fornire un'asserzione di sicurezza CertificateOverTransport equivalente all'asserzione di sicurezza turnkey `UsernameOverTransport`, WSE 3.0 utilizza un certificato X.509 per eseguire l'autenticazione client. Se per questo scenario è stata definita un'asserzione di criteri personalizzata, WCF semplifica la migrazione. WCF definisce una modalità di autenticazione per questo scenario, quindi è possibile sfruttare i metodi helper della modalità di autenticazione statica per configurare un WCF <xref:System.ServiceModel.Channels.SecurityBindingElement> .  
  
 Quando non è disponibile una modalità di autenticazione WCF equivalente a un'asserzione di criteri personalizzata che protegge i messaggi SOAP, derivare una classe dalle <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> classi di o <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> WCF e specificare l'elemento di associazione equivalente. Per altri dettagli, vedere [procedura: creare un'associazione personalizzata usando SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
 Per convertire un'asserzione di criteri personalizzata che non protegge un messaggio SOAP, vedere [filtro](filtering.md) e l' [intercettore di messaggi personalizzato](../samples/custom-message-interceptor.md)di esempio.  
  
### <a name="wse-30-custom-security-token"></a>Token di sicurezza personalizzato di WSE 3.0  
 Il modello di programmazione WCF per la creazione di un token personalizzato è diverso da WSE 3,0. Per informazioni dettagliate sulla creazione di un token personalizzato in WSE, vedere [creazione di token di sicurezza personalizzati](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa529304(v=msdn.10)). Per informazioni dettagliate sulla creazione di un token personalizzato in WCF, vedere [procedura: creare un token personalizzato](../extending/how-to-create-a-custom-token.md).  
  
### <a name="wse-30-custom-token-manager"></a>Gestore del token personalizzato di WSE 3.0  
 Il modello di programmazione per la creazione di un gestore di token personalizzato è diverso in WCF rispetto a WSE 3,0. Per informazioni dettagliate su come creare un gestore di token personalizzato e gli altri componenti necessari per un token di sicurezza personalizzato, vedere [procedura: creare un token personalizzato](../extending/how-to-create-a-custom-token.md).  
  
> [!NOTE]
> Se è stato creato un `UsernameToken` gestore del token di sicurezza personalizzato, WCF fornisce un meccanismo più semplice per specificare la logica di autenticazione rispetto alla creazione di un gestore del token di sicurezza personalizzato. Per altri dettagli, vedere [procedura: usare un validator personalizzato di nome utente e password](how-to-use-a-custom-user-name-and-password-validator.md).  
  
### <a name="wse-30-web-services-that-use-mtom-encoded-soap-messages"></a>Servizi Web WSE 3.0 che utilizzano messaggi SOAP con codifica MTOM  
 Analogamente a un'applicazione WSE 3, un'applicazione WCF può specificare la codifica dei messaggi MTOM nella configurazione. Per eseguire la migrazione di questa impostazione, aggiungere al [\<mtomMessageEncoding>](../../configure-apps/file-schema/wcf/mtommessageencoding.md) binding per il servizio. Nell'esempio di codice riportato di seguito viene illustrato come specificare la codifica MTOM in WSE 3,0 per un servizio equivalente in WCF.  
  
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

 Quando si utilizza l'API del sistema di messaggistica di WSE per accedere in modo diretto ai dati XML scambiati fra il client e il servizio Web, l'applicazione può essere convertita in modo da utilizzare il formato POX (Plain Old XML). Per ulteriori informazioni su POX, vedere [interoperabilità con applicazioni POX](interoperability-with-pox-applications.md). Per ulteriori informazioni sull'API di messaggistica WSE, vedere [invio e ricezione di messaggi SOAP tramite l'API di messaggistica WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-2.0/aa529293(v=msdn.10)).  
  
## <a name="transports"></a>Trasporti  
  
### <a name="tcp"></a>TCP  
 Per impostazione predefinita, i client WSE 3,0 e i servizi Web che inviano messaggi SOAP utilizzando il trasporto TCP non interagiscono con i client e i servizi Web WCF. Questa incompatibilità è dovuta a differenze nella modalità di frame del protocollo TCP e si basa inoltre su motivi legati alle prestazioni. Tuttavia, in un esempio WCF viene illustrato in dettaglio come implementare una sessione TCP personalizzata che interagisce con WSE 3,0. Per informazioni dettagliate su questo esempio, vedere [trasporto: interoperabilità TCP di WSE 3,0](../samples/transport-wse-3-0-tcp-interoperability.md).  
  
 Per specificare che un'applicazione WCF utilizza il trasporto TCP, utilizzare [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) .  
  
### <a name="custom-transport"></a>Trasporto personalizzato  
 L'equivalente di un trasporto personalizzato WSE 3,0 in WCF è un'estensione del canale. Per informazioni dettagliate sulla creazione di un'estensione del canale, vedere [estensione del livello del canale](../extending/extending-the-channel-layer.md).  
  
## <a name="see-also"></a>Vedere anche

- [Ciclo di vita della programmazione di base](../basic-programming-lifecycle.md)
- [Associazioni personalizzate](../extending/custom-bindings.md)
- [Procedura: creare un'associazione personalizzata usando SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Procedura: creare un elemento SecurityBindingElement per una modalità di autenticazione specificata](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
