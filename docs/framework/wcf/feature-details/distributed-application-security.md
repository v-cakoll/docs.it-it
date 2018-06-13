---
title: Protezione delle applicazioni distribuite
ms.date: 03/30/2017
helpviewer_keywords:
- distributed application security [WCF]
- security [WCF], transfer
ms.assetid: 53928a10-e474-46d0-ab90-5f98f8d7b668
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: d8f34d0c6b0269cc4837313d6613e3cee0eb26c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496165"
---
# <a name="distributed-application-security"></a>Protezione delle applicazioni distribuite
Sicurezza di Windows Communication Foundation (WCF) viene suddiviso in tre aree funzionali principali: protezione del trasferimento, controllo di accesso e il controllo. La protezione di trasferimento, oltre a offrire funzionalità di autenticazione, garantisce integrità e riservatezza. Questa area funzionale utilizza uno dei meccanismi seguenti: protezione a livello di trasporto, protezione a livello di messaggio e `TransportWithMessageCredential`.  
  
 Per una panoramica della sicurezza dei messaggi WCF, vedere [Cenni preliminari sulla sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md). Per ulteriori informazioni su altri due tipi di sicurezza WCF, vedere [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md) e [controllo](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
## <a name="transfer-security-scenarios"></a>Scenari di utilizzo della protezione di trasferimento  
 Scenari comuni che si avvalgono di sicurezza di trasferimento WCF includono quanto segue:  
  
-   Protezione di trasferimento basata su Windows: Un client e servizio WCF vengono distribuiti in un dominio di Windows (o una foresta di Windows). Poiché i messaggi contengono dati personali, i requisiti prevedono l'autenticazione reciproca del client e del servizio nonché l'integrità e la riservatezza dei messaggi. Occorre inoltre implementare una funzione che provi l'avvenuta esecuzione di una determinata transazione. Ad esempio, è necessario che il destinatario del messaggio registri le informazioni sulla firma.  
  
-   Protezione di trasferimento basata sull'elemento `UserName` e su HTTPS: Un client WCF e un servizio necessario sviluppare modo che funzionino su Internet. L'autenticazione delle credenziali client si basa su un database di coppie nome utente/password. Il servizio è distribuito presso un indirizzo HTTPS che utilizza un certificato SSL (Secure Sockets Layer) attendibile. Poiché i messaggi sono trasmessi su Internet, occorre implementare l'autenticazione reciproca fra client e servizio nonché garantire la riservatezza e l'integrità dei messaggi durante il trasferimento.  
  
-   Protezione di trasferimento basata su certificati: Un client WCF e un servizio necessario sviluppare modo che funzionino sulla rete internet pubblica. Sia il client sia il servizio presentano certificati utilizzabili per proteggere i messaggi. Il client e il servizio comunicano fra loro via Internet allo scopo di eseguire transazioni di elevata importanza per cui occorre implementare funzionalità che, oltre a garantire l'integrità e la riservatezza delle comunicazioni, eseguano l'autenticazione reciproca.  
  
## <a name="integrity-confidentiality-and-authentication"></a>Integrità, riservatezza e autenticazione  
 La protezione di trasferimento è costituita da tre funzioni: integrità, riservatezza e autenticazione. La sicurezza di trasferimento offre funzioni che consentono di ridurre i rischi per un'applicazione distribuita. Nella tabella seguente sono descritte brevemente le tre funzioni che costituiscono la protezione di trasferimento.  
  
|Funzione|Descrizione|  
|--------------|-----------------|  
|Integrità|*Integrità* rappresenta la garanzia che i dati siano completa e accurato, in particolare dopo che è attraversata da un punto a altro e possibile lettura da parte di molti attori. L'integrità garantisce che i dati non subiscano manomissioni e in genere si basa sull'utilizzo di firme digitali nei messaggi.|  
|Riservatezza|*Riservatezza* rappresenta la garanzia che un messaggio non è stato letto esclusivamente dall'utente previsto. È ad esempio fondamentale garantire la riservatezza dei numeri di carta di credito trasmessi via Internet. La riservatezza spesso si basa sulla crittografia dei dati mediante uno schema chiave pubblica/chiave privata.|  
|Autenticazione|*Autenticazione* è la verifica di un'attestazione di identità. Ad esempio, quando si utilizza un conto bancario, è fondamentale garantire che solo il titolare effettivo del conto sia in grado di prelevare fondi. L'autenticazione può essere eseguita in vari modi. Un metodo comune è il sistema utente/password. Un altro metodo è l'utilizzo di un certificato X.509 fornito da terzi.|  
  
## <a name="security-modes"></a>Modalità di sicurezza  
 WCF dispone di diverse modalità di sicurezza del trasferimento, che sono descritte nella tabella seguente.  
  
|Modalità|Descrizione|  
|----------|-----------------|  
|Nessuno|Non viene fornita alcuna protezione né a livello di trasporto né a livello di messaggio. Nessuna delle associazioni predefinite utilizzare questa modalità per impostazione predefinita, ad eccezione di [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) elemento o, quando si utilizza codice, la <xref:System.ServiceModel.BasicHttpBinding> classe.|  
|Trasporto|Per implementare la funzionalità di autenticazione reciproca e per garantire l'integrità e la riservatezza dei messaggi viene utilizzato un trasporto protetto, ad esempio HTTPS.|  
|Messaggio|Per implementare la funzionalità di autenticazione reciproca e per garantire l'integrità e la riservatezza dei messaggi viene utilizzato un sistema di sicurezza basato sui messaggi SOAP. I messaggi SOAP sono protetti in conformità agli standard WS-Security.|  
|Modalità mista|Per implementare la funzionalità di autenticazione del server e per garantire l'integrità e la riservatezza dei messaggi viene utilizzato un trasporto protetto. Per implementare la funzionalità di autenticazione del client viene invece utilizzato un sistema di sicurezza a livello di messaggio conforme a uno standard di sicurezza, ad esempio WS-Security.<br /><br /> L'enumerazione di questa modalità è `TransportWithMessageCredential`.|  
|Entrambi|Le funzionalità di protezione e autenticazione vengono implementate sia a livello di trasporto sia a livello di messaggio. È disponibile solo in questa modalità il [ \<netMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md) elemento.|  
  
## <a name="credentials-and-transfer-security"></a>Protezione di trasferimento basata sull'utilizzo di credenziali  
 Oggetto *credenziali* dati presentati per stabilire un'attestazione di identità o funzionalità. Quando si presenta una credenziale, è necessario presentare sia i dati sia la prova di possesso dei dati. WCF supporta diversi tipi di credenziali a livello di trasporto e messaggio di sicurezza. È possibile specificare un tipo di credenziale per un binding WCF.  
  
 In molti paesi o aree geografiche la patente di guida costituisce un esempio di credenziale. Oltre a contenere dati che descrivono l'identità e le capacità di un individuo, una patente contiene una prova di possesso, ovvero la foto del titolare. La patente viene inoltre rilasciata da un'autorità attendibile, in genere un apposito ente governativo e, allo scopo di impedire manomissioni e falsificazioni, viene sigillata ed eventualmente corredata di ologramma.  
  
 Ad esempio, prendere in considerazione due tipi di credenziali supportati in WCF: nome utente e certificati (X.509) le credenziali.  
  
 Nel primo tipo di credenziale, il nome utente rappresenta l'attestazione di identità e la password rappresenta la prova di possesso. In questo caso l'autorità attendibile è il sistema che convalida nome utente e password.  
  
 Nel secondo tipo di credenziale, il nome del soggetto, il nome alternativo del soggetto o i campi specifici del certificato possono essere utilizzati per rappresentare l'attestazione di identità e/o di funzionalità. La prova di possesso dei dati in questo caso viene fornita tramite una firma creata mediante la chiave privata associata alla credenziale.  
  
 Per ulteriori informazioni sulla programmazione della sicurezza del trasferimento e specificare le credenziali, vedere [associazioni e protezione](../../../../docs/framework/wcf/feature-details/bindings-and-security.md) e [comportamenti di sicurezza](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md).  
  
### <a name="transport-client-credential-types"></a>Tipi di credenziale utilizzati nella protezione client a livello di trasporto  
 La tabella seguente mostra i valori utilizzabili quando si crea un'applicazione che utilizza la protezione a livello di trasporto. I valori riportati possono essere utilizzati nelle impostazioni del codice o delle associazioni.  
  
|Impostazione|Descrizione|  
|-------------|-----------------|  
|None|Specifica che il client non deve presentare alcuna credenziale. Il client viene pertanto autenticato come anonimo.|  
|Basic|Specifica l'autenticazione di base.  Per ulteriori informazioni, vedere il documento RFC2617, "[HTTP Authentication: Basic and Digest Authentication](http://go.microsoft.com/fwlink/?LinkId=88313)."|  
|Digest|Specifica l'autenticazione digest.  Per ulteriori informazioni, vedere il documento RFC2617, "[HTTP Authentication: Basic and Digest Authentication](http://go.microsoft.com/fwlink/?LinkId=88313)."|  
|Ntlm|Specifica l'autenticazione di Windows basata sulla negoziazione SSPI in un dominio di Windows.<br /><br /> La negoziazione SSPI comporta l'utilizzo del protocollo Kerberos o del protocollo NTLM (NT LanMan).|  
|WINDOWS|Specifica l'autenticazione di Windows basata su SSPI in un dominio di Windows. L'interfaccia SSPI sceglie come servizio di autenticazione il protocollo Kerberos oppure il protocollo NTLM.<br /><br /> In particolare, tenta prima di scegliere il protocollo Kerberos e, se il tentativo non riesce, utilizza il protocollo NTLM.|  
|Certificato|L'autenticazione del client viene eseguita tramite un certificato, in genere X.509.|  
  
### <a name="message-client-credential-types"></a>Tipi di credenziale usati nella sicurezza client a livello di messaggio  
 La tabella seguente mostra i valori utilizzabili quando si crea un'applicazione che utilizza la protezione a livello di messaggio. I valori riportati possono essere utilizzati nelle impostazioni del codice o delle associazioni.  
  
|Impostazione|Descrizione|  
|-------------|-----------------|  
|Nessuno|Consente al servizio di interagire con client anonimi.|  
|WINDOWS|Consente lo scambio di messaggi SOAP all'interno di un contesto autenticato di una credenziale Windows. Viene utilizzato il meccanismo di negoziazione SSPI per scegliere il protocollo Kerberos o il protocollo NTLM come servizio di autenticazione.|  
|Nome utente|Consente al servizio di richiedere che l'autenticazione del client si basi su una credenziale di tipo nome utente. Si noti che WCF non consente le operazioni di crittografia con il nome utente, ad esempio la generazione di una firma o la crittografia dei dati. Di conseguenza, WCF richiede che il trasporto sia protetto quando si usano credenziali nome utente.|  
|Certificato|Consente al servizio di richiedere che l'autenticazione del client si basi su un certificato.|  
|[!INCLUDE[infocard](../../../../includes/infocard-md.md)]|Consente al servizio di richiedere che l'autenticazione del client si basi su [!INCLUDE[infocard](../../../../includes/infocard-md.md)].|  
  
### <a name="programming-credentials"></a>Programmazione delle credenziali  
 Per ognuno dei tipi di credenziali client, il modello di programmazione WCF consente di specificare i valori delle credenziali e una credenziale validator utilizzando i comportamenti del servizio e comportamenti di canale.  
  
 Sicurezza WCF è disponibili due tipi di credenziali: comportamenti di credenziale di canale e i comportamenti di credenziale del servizio. Comportamenti di credenziale di WCF specificano i dati effettivi, vale a dire, le credenziali utilizzate per soddisfare i requisiti di sicurezza espliciti tramite associazioni. In WCF, una classe client è il componente di runtime che esegue la conversione tra i messaggi e la chiamata di operazione. Tutti i client sono ereditati dalla classe <xref:System.ServiceModel.ClientBase%601>. La proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> della classe di base consente di specificare vari valori di credenziali client.  
  
 In WCF, i comportamenti del servizio sono attributi applicati alla classe che implementa un contratto di servizio (interfaccia) a livello di programmazione il servizio. La classe <xref:System.ServiceModel.Description.ServiceCredentials> consente l'utilizzo di certificati come credenziale di un servizio nonché la configurazione delle impostazioni di convalida relative a vari tipi di credenziale client.  
  
### <a name="negotiation-model-for-message-security"></a>Modello di negoziazione della protezione a livello di messaggio  
 La modalità di sicurezza a livello di messaggio consente di eseguire la funzionalità di sicurezza di trasferimento in modo che la credenziale del servizio venga configurata presso il client fuori banda. Se ad esempio si utilizza un certificato memorizzato nell'archivio certificati di Windows, è necessario ricorrere a uno strumento specifico, ad esempio lo snap-in MMC (Microsoft Management Console).  
  
 La modalità di sicurezza a livello di messaggio consente inoltre di eseguire la funzionalità di sicurezza di trasferimento in modo che la credenziale del servizio venga scambiata con il client nel contesto di una negoziazione iniziale. Per attivare la negoziazione, impostare la proprietà <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> su `true`.  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica della creazione di endpoint](../../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Associazioni fornite dal sistema](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Modello di sicurezza per Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
