---
title: Associazioni e protezione
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], security
- WCF security
- Windows Communication Foundation, security
- bindings [WCF]
ms.assetid: 4de03dd3-968a-4e65-af43-516e903d7f95
ms.openlocfilehash: 63d3888df364d033b17972a5fd3ba3b851e00c42
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964431"
---
# <a name="bindings-and-security"></a>Associazioni e protezione

Le associazioni fornite dal sistema incluse in Windows Communication Foundation (WCF) offrono un modo rapido per programmare le applicazioni WCF. Tutte le associazioni, tranne una, dispongono di uno schema di sicurezza predefinito attivo. In questo argomento viene illustrato come selezionare l'associazione corretta per la sicurezza desiderata.

Per una panoramica della sicurezza di WCF, vedere [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md). Per ulteriori informazioni sulla programmazione di WCF mediante binding, vedere [Programming WCF Security](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md).

Se è già stata selezionata un'associazione, è possibile ottenere ulteriori informazioni sui comportamenti di runtime associati alla sicurezza nei [comportamenti di sicurezza](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md).

Alcune funzionalità di sicurezza non sono programmabili tramite le associazioni fornite dal sistema. Per un maggiore controllo sull'utilizzo di un'associazione personalizzata, vedere [funzionalità di sicurezza con associazioni personalizzate](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md).

## <a name="security-functions-of-bindings"></a>Funzionalità di sicurezza delle associazioni

WCF include diverse associazioni fornite dal sistema che soddisfano la maggior parte delle esigenze. È inoltre possibile creare un'associazione personalizzata se una determinata associazione non è sufficiente. Per un elenco delle associazioni fornite dal sistema, vedere [associazioni fornite dal sistema](../../../../docs/framework/wcf/system-provided-bindings.md). Per ulteriori informazioni sulle associazioni personalizzate, vedere [associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md).

Ogni binding in WCF è costituito da due formati: come API e come elemento XML usato in un file di configurazione. Ad esempio, il `WSHttpBinding` (API) ha una controparte nella [> di\<WSHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).

Nella sezione seguente vengono elencate entrambe le forme per ogni associazione e vengono riepilogate le funzionalità di sicurezza.

### <a name="basichttp"></a>BasicHttp

Nel codice usare la classe <xref:System.ServiceModel.BasicHttpBinding>; in configurazione usare il [> basichttpbinding\<](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).

Questa associazione è progettata per l'utilizzo con una gamma di tecnologie esistenti, incluse le seguenti:

- Servizi Web ASP.NET (ASMX), versione 1.

- Applicazioni Web Service Enhancements (WSE).

- Profilo di base come definito nella specifica WS-I (Web Services Interoperability) (<https://go.microsoft.com/fwlink/?LinkId=38955>).

- Basic Security Profile come definito in WS-I.

Per impostazione predefinita, questa associazione non è protetta. È progettata per interagire con i servizi ASMX. Quando la sicurezza è attivata, l'associazione è progettata per l'interazione con meccanismi di sicurezza di Internet Information Services (IIS), ad esempio l'autenticazione di base, digest e la sicurezza di Windows integrata. Per altre informazioni, vedere [Panoramica della sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/transport-security-overview.md). Questa associazione supporta:

- Sicurezza del trasporto HTTPS.

- Autenticazione di base HTTP.

- WS-Security.

Per ulteriori informazioni, vedere <xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType> e <xref:System.ServiceModel.BasicHttpSecurityMode>.

### <a name="wshttpbinding"></a>WSHttpBinding

Nel codice usare la classe <xref:System.ServiceModel.WSHttpBinding>; in configurazione usare il [> WSHttpBinding di\<](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).

Per impostazione predefinita, questa associazione implementa la specifica WS-Security e fornisce interoperabilità con servizi che implementano le specifiche WS-*. Sono supportati:

- Sicurezza del trasporto HTTPS.

- WS-Security.

- Protezione del trasporto HTTPS con sicurezza della credenziale messaggi SOAP per l'autenticazione del chiamante.

Per ulteriori informazioni, vedere <xref:System.ServiceModel.WSHttpSecurity>, <xref:System.ServiceModel.MessageSecurityOverHttp>, <xref:System.ServiceModel.MessageCredentialType>, <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.HttpTransportSecurity>, <xref:System.ServiceModel.HttpClientCredentialType>e <xref:System.ServiceModel.HttpProxyCredentialType>.

### <a name="wsdualhttpbinding"></a>WSDualHttpBinding

Nel codice usare la classe <xref:System.ServiceModel.WSDualHttpBinding>; in configurazione usare il [\<WSDualHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).

Questa associazione è progettata per consentire applicazioni di servizio duplex. Implementa la specifica WS-Security per la protezione del trasferimento basata sul messaggio. La protezione del trasporto non è disponibile. Per impostazione predefinita, fornisce le funzionalità seguenti:

- Implementa WS-Reliable Messaging per l'affidabilità.

- Implementa WS-Security per la protezione e l'autenticazione del trasferimento.

- Utilizza HTTP per il recapito dei messaggi.

- Utilizza la codifica dei messaggi testo/XML.

 Tramite WS-Security (protezione a livello di messaggio), l'associazione consente di configurare i parametri seguenti:

- Gruppo di algoritmi di sicurezza per determinare l'algoritmo di crittografia.

- Opzioni dell'associazione per:

  - Fornitura di credenziali del servizio disponibili fuori banda nel client.

  - Fornitura di credenziali del servizio negoziate dal servizio come parte della configurazione del canale.

Per altre informazioni, vedere <xref:System.ServiceModel.WSDualHttpSecurity> e <xref:System.ServiceModel.WSDualHttpSecurityMode>.

### <a name="nettcpbinding"></a>NetTcpBinding

Nel codice usare la classe <xref:System.ServiceModel.NetTcpBinding>; in configurazione usare il [> NetTcpBinding di\<](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).

Questa associazione è ottimizzata per le comunicazioni tra computer. Per impostazione predefinita, dispone delle caratteristiche seguenti:

- Implementa la protezione a livello di trasporto.

- Utilizza la protezione di Windows per la protezione e l'autenticazione del trasferimento.

- Utilizza TCP per il trasporto.

- Implementa la codifica messaggi binaria.

- Implementa WS-Reliable Messaging.

Le opzioni includono:

- Sicurezza a livello di messaggio (tramite WS-Security).

- Sicurezza del trasporto con credenziali messaggio: riservatezza e integrità fornite da Transport Layer Security (TLS) su TCP e credenziali per l'autorizzazione fornite da WS-Security.

Per ulteriori informazioni, vedere <xref:System.ServiceModel.NetTcpSecurity>, <xref:System.ServiceModel.TcpTransportSecurity>, <xref:System.ServiceModel.TcpClientCredentialType>, <xref:System.ServiceModel.MessageSecurityOverTcp>e <xref:System.ServiceModel.MessageCredentialType>.

### <a name="netnamedpipebinding"></a>NetNamedPipeBinding

Nel codice usare la classe <xref:System.ServiceModel.NetNamedPipeBinding>; in configurazione usare il [> netNamedPipeBinding\<](../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).

Questa associazione è ottimizzata per le comunicazioni tra processi (in genere nello stesso computer). Per impostazione predefinita, questa associazione dispone delle caratteristiche seguenti:

- Utilizza la sicurezza del trasporto per il trasferimento e l'autenticazione dei messaggi.

- Utilizza le named pipe per il recapito dei messaggi.

- Implementa la codifica messaggi binaria.

- Crittografia e firma dei messaggi.

Le opzioni includono:

- Autenticazione tramite la sicurezza di Windows.

Per altre informazioni, vedere <xref:System.ServiceModel.NetNamedPipeSecurity>, <xref:System.ServiceModel.NetNamedPipeSecurityMode> e <xref:System.ServiceModel.NamedPipeTransportSecurity>.

### <a name="msmqintegrationbinding"></a>MsmqIntegrationBinding

Nel codice usare la classe <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>; in configurazione usare il [\<> MsmqIntegrationBinding](../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).

Questa associazione è ottimizzata per la creazione di client e servizi WCF che interagiscono con gli endpoint non WCF Microsoft Message Queuing (MSMQ).

Per impostazione predefinita, questa associazione utilizza la sicurezza del trasporto e fornisce le caratteristiche di sicurezza seguenti:

- Possibilità di disattivare la sicurezza (None).

- Sicurezza del trasporto MSMQ (Transport).

Per altre informazioni, vedere <xref:System.ServiceModel.NetMsmqSecurity> e <xref:System.ServiceModel.NetMsmqSecurityMode>.

### <a name="netmsmqbinding"></a>NetMsmqBinding

Nel codice usare la classe <xref:System.ServiceModel.NetMsmqBinding>; in configurazione usare la [> NetMsmqBinding di\<](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md).

Questa associazione è destinata all'utilizzo quando si creano servizi WCF che richiedono il supporto dei messaggi accodati MSMQ.

Per impostazione predefinita, questa associazione utilizza la sicurezza del trasporto e fornisce le caratteristiche di sicurezza seguenti:

- Possibilità di disattivare la sicurezza (None).

- Sicurezza del trasporto MSMQ (Transport).

- Sicurezza dei messaggi basati su SOAP (Message).

- Trasporto simultaneo e sicurezza dei messaggi (Both).

- Tipi di credenziale client supportati: None, Windows, UserName, Certificate, IssuedToken.

La credenziale <xref:System.ServiceModel.MessageCredentialType.Certificate> è supportata solo quando la modalità di sicurezza è impostata su <xref:System.ServiceModel.NetMsmqSecurityMode.Both> o su <xref:System.ServiceModel.NetMsmqSecurityMode.Message>.

Per altre informazioni, vedere <xref:System.ServiceModel.MessageSecurityOverMsmq> e <xref:System.ServiceModel.MsmqTransportSecurity>.

### <a name="wsfederationhttpbinding"></a>WSFederationHttpBinding

Nel codice usare la classe <xref:System.ServiceModel.WSFederationHttpBinding>; in configurazione usare il [> wsFederationHttpBinding\<](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).

Per impostazione predefinita, questa associazione utilizza WS-Security (sicurezza a livello di messaggio).

Per ulteriori informazioni, vedere [Federazione](../../../../docs/framework/wcf/feature-details/federation.md), <xref:System.ServiceModel.WSFederationHttpSecurity>e <xref:System.ServiceModel.WSFederationHttpSecurityMode>.

## <a name="custom-bindings"></a>Binding personalizzati

Se i requisiti non vengono soddisfatti da alcuna associazione fornita dal sistema, è possibile creare un'associazione personalizzata con un elemento di associazione di sicurezza personalizzato. Per altre informazioni, vedere [funzionalità di sicurezza con associazioni personalizzate](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md).

## <a name="binding-choices"></a>Scelte di associazioni

Nella tabella seguente vengono riepilogate le funzionalità offerte nell'impostazione della modalità di sicurezza, ovvero vengono elencate le funzionalità disponibili quando la modalità di sicurezza è impostata su `Transport`, `Message` o `TransportWithMessageCredential`. L'utilizzo di questa tabella consente di trovare le funzionalità di sicurezza più appropriate per l'applicazione.

|Impostazione di|Funzionalità|
|-------------|--------------|
|Transport|Autenticazione server<br /><br /> Autenticazione client<br /><br /> Sicurezza point-to-point<br /><br /> Interoperabilità<br /><br /> Accelerazione hardware<br /><br /> Velocità effettiva elevata<br /><br /> Firewall di sicurezza<br /><br /> Applicazioni con latenza elevata<br /><br /> Ripetizione della crittografia attraverso più hop|
|Messaggio|Autenticazione server<br /><br /> Autenticazione client<br /><br /> Sicurezza end-to-end<br /><br /> Interoperabilità<br /><br /> Attestazioni complesse<br /><br /> Federazione<br /><br /> Autenticazione a più fattori<br /><br /> Token personalizzati<br /><br /> Servizio notary/timestamp<br /><br /> Applicazioni con latenza elevata<br /><br /> Persistenza di firme del messaggio|
|TransportWithMessageCredential|Autenticazione server<br /><br /> Autenticazione client<br /><br /> Sicurezza point-to-point<br /><br /> Interoperabilità<br /><br /> Accelerazione hardware<br /><br /> Velocità effettiva elevata<br /><br /> Richieste del client Dettagliate<br /><br /> Federazione<br /><br /> Autenticazione a più fattori<br /><br /> Token personalizzati<br /><br /> Firewall di sicurezza<br /><br /> Applicazioni con latenza elevata<br /><br /> Ripetizione della crittografia attraverso più hop|

Nella tabella seguente vengono elencate le associazioni che supportano le impostazioni delle varie modalità. Selezionare un'associazione dalla tabella per creare l'endpoint del servizio.

|Associazione|Supporto modalità trasporto|Supporto modalità messaggio|Supporto TransportWithMessageCredential|
|-------------|----------------------------|--------------------------|--------------------------------------------|
|`BasicHttpBinding`|Sì|Sì|Sì|
|`WSHttpBinding`|Sì|Sì|Sì|
|`WSDualHttpBinding`|No|Sì|No|
|`NetTcpBinding`|Sì|Sì|Sì|
|`NetNamedPipeBinding`|Sì|No|No|
|`NetMsmqBinding`|Sì|Sì|No|
|`MsmqIntegrationBinding`|Sì|No|No|
|`wsFederationHttpBinding`|No|Sì|Sì|

## <a name="transport-credentials-in-bindings"></a>Credenziali di trasporto nelle associazioni

Nella tabella seguente vengono elencati i tipi di credenziali client disponibili quando si utilizza `BasicHttpBinding` o `WSHttpBinding` nella modalità di sicurezza del trasporto.

|Tipo di|Descrizione|
|----------|-----------------|
|nessuna|Specifica che il client non deve presentare alcuna credenziale. Il client viene pertanto autenticato come anonimo.|
|Basic|Autenticazione di base. Per ulteriori informazioni, vedere RFC 2617-HTTP Authentication: Basic and Digest Authentication, disponibile all'<https://go.microsoft.com/fwlink/?LinkId=84023>.|
|Digest|Autenticazione del digest. Per ulteriori informazioni, vedere RFC 2617-HTTP Authentication: Basic and Digest Authentication, disponibile all'<https://go.microsoft.com/fwlink/?LinkId=84023>.|
|NTLM|Autenticazione NT LAN Manager (NTLM).|
|Portale di|Autenticazione Windows.|
|Certificato|Autenticazione eseguita mediante un certificato.|
|IssuedToken|Consente al servizio di richiedere che il client venga autenticato utilizzando un token emesso da un servizio token di sicurezza o da CardSpace. Per altre informazioni, vedere [Federazione e token emessi](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).|

### <a name="message-client-credentials-in-bindings"></a>Credenziali client dei messaggi nelle associazioni

Nella tabella seguente vengono elencati i tipi di credenziali client disponibili quando si utilizza un'associazione nella modalità di sicurezza dei messaggi.

|Tipo di|Descrizione|
|----------|-----------------|
|nessuna|Consente al servizio di interagire con client anonimi.|
|Portale di|Consente gli scambi di messaggi SOAP nel contesto autenticato di una credenziale di Windows.|
|Nome utente|Consente al servizio di richiedere che l'autenticazione del client sia eseguita tramite una credenziale UserName. Si noti che quando la modalità di sicurezza è impostata su `TransportWithMessageCredential`, WCF non supporta l'invio di un digest della password o la derivazione di chiavi tramite password e l'utilizzo di tali chiavi per la sicurezza in modalità messaggio. Di conseguenza, WCF impone che il trasporto sia protetto quando si utilizzano le credenziali del nome utente.|
|Certificato|Consente al servizio di richiedere che l'autenticazione del client si basi su un certificato.|
|IssuedToken|Consente al servizio di utilizzare un servizio token di sicurezza per fornire un token personalizzato.|

## <a name="see-also"></a>Vedere anche

- [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Selezione di un tipo di credenziale](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [Funzionalità di sicurezza con associazioni personalizzate](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [Comportamenti di sicurezza](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Modello di sicurezza per Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
