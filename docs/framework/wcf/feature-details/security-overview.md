---
title: Panoramica della sicurezza
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, security
- WCF, security
ms.assetid: f478c80d-792d-4e7a-96bd-a2ff0b6f65f9
ms.openlocfilehash: 517d80395e09598fcbd067034223dc6ba58cbe2e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600438"
---
# <a name="windows-communication-foundation-security-overview"></a>Panoramica della sicurezza Windows Communication Foundation
Windows Communication Foundation (WCF) è una piattaforma di programmazione distribuita basata su messaggi SOAP e la protezione dei messaggi tra client e servizi è essenziale per la protezione dei dati. WCF offre una piattaforma versatile e interoperativa per lo scambio di messaggi protetti basati sull'infrastruttura di sicurezza esistente e sugli standard di sicurezza riconosciuti per i messaggi SOAP.  
  
> [!NOTE]
> Per una guida completa alla sicurezza di WCF, vedere [Guida alla sicurezza di WCF](https://archive.codeplex.com/?p=WCFSecurity).  
  
 WCF utilizza concetti familiari se sono state create applicazioni distribuite sicure con tecnologie esistenti quali HTTPS, la sicurezza integrata di Windows o nomi utente e password per autenticare gli utenti. WCF non si integra solo con le infrastrutture di sicurezza esistenti, ma estende la sicurezza distribuita anche oltre i domini solo Windows utilizzando messaggi SOAP protetti. Prendere in considerazione WCF un'implementazione dei meccanismi di sicurezza esistenti con il vantaggio principale dell'utilizzo di SOAP come protocollo, oltre ai protocolli esistenti. Ad esempio, le credenziali che identificano un client o un servizio, quali nome utente e password o certificati X.509, hanno profili SOAP interoperativi basati su XML. Se si usano questi profili, i messaggi vengono scambiati in modo protetto usufruendo dei vantaggi delle specifiche aperte quali le firme digitali e la crittografia XML. Per un elenco delle specifiche, vedere [protocolli di servizi Web supportati da associazioni di interoperabilità fornite dal sistema](web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
 Un altro servizio parallelo è COM (Component Object Model) sulla piattaforma Windows, che consente applicazioni distribuite protette. COM dispone di un meccanismo di sicurezza completo mediante il quale il contesto di sicurezza può essere propagato tra i componenti. Questo meccanismo applica l'integrità, la riservatezza e l'autenticazione. COM, tuttavia, non consente la messaggistica protetta multipiattaforma come WCF. Con WCF è possibile creare servizi e client che si estendono da domini Windows su Internet. I messaggi interoperativi di WCF sono essenziali per la creazione di servizi dinamici e basati sull'azienda che consentono di ottenere la sicurezza delle informazioni.  
  
## <a name="windows-communication-foundation-security-benefits"></a>Vantaggi della sicurezza di Windows Communication Foundation  
 WCF è una piattaforma di programmazione distribuita basata su messaggi SOAP. Con WCF è possibile creare applicazioni che funzionano sia come servizi che come client di servizio, creando ed elaborando messaggi da un numero illimitato di altri servizi e client. In un'applicazione distribuita di questo tipo i messaggi possono fluire da nodo a nodo, attraverso firewall, su Internet e attraverso numerosi intermediari SOAP. Ciò introduce tutta una serie di rischi per la sicurezza dei messaggi. Negli esempi seguenti vengono illustrate alcune minacce comuni che la sicurezza di WCF può contribuire a mitigare durante lo scambio di messaggi tra entità:  
  
- Osservazione del traffico di rete per ottenere informazioni riservate. In uno scenario di online banking, ad esempio, un cliente richiede il trasferimento di fondi da un conto a un altro. Un utente malintenzionato intercetta il messaggio e, disponendo del numero di conto e della password, esegue successivamente un trasferimento di fondi dal conto compromesso.  
  
- Entità non autorizzate che agiscono come servizi all'insaputa del cliente. In questo scenario un utente malintenzionato (l'entità non autorizzata) agisce come un servizio online e intercetta messaggi inviati dal cliente per ottenere informazioni riservate. L'entità non autorizzata usa quindi i dati rubati per trasferire fondi dal conto compromesso. Questo attacco è noto anche come *attacco di phishing*.  
  
- Modifica di messaggi per ottenere un risultato diverso da quello voluto dal chiamante. Ad esempio, la modifica del numero di conto nel quale viene effettuato un deposito consente il trasferimento di fondi in un conto non autorizzato.  
  
- Riproduzioni hacker in cui un hacker "nuisance" riproduce lo stesso ordine di acquisto. Ad esempio, una libreria online riceve centinaia di ordini e invia i libri a un cliente che non li ha ordinati.  
  
- Incapacità di un servizio di autenticare un client. In questo caso, il servizio non può assicurare che la transazione sia stata eseguita dalla persona appropriata.  
  
 In sintesi, la sicurezza del trasferimento fornisce le garanzie seguenti:  
  
- Autenticazione dell'endpoint servizio (rispondente).  
  
- Autenticazione dell'entità client (iniziatore).  
  
- Integrità del messaggio.  
  
- Riservatezza del messaggio.  
  
- Rilevamento riproduzione.  
  
### <a name="integration-with-existing-security-infrastructures"></a>Integrazione con infrastrutture di sicurezza esistenti  
 Nelle distribuzioni di servizi Web sono spesso già presenti soluzioni di sicurezza quali Secure Sockets Layer (SSL) o il protocollo Kerberos. Alcune distribuzioni sfruttano un'infrastruttura di sicurezza che è già stata distribuita, come i domini Windows che usano Active Directory. Spesso è necessario integrare le distribuzioni con queste tecnologie esistenti, nonché valutare e adottare nuove tecnologie.  
  
 La sicurezza WCF si integra con i modelli di sicurezza del trasporto esistenti e può sfruttare l'infrastruttura esistente per i modelli di sicurezza del trasferimento più recenti basati sulla sicurezza dei messaggi SOAP.  
  
### <a name="integration-with-existing-authentication-models"></a>Integrazione con modelli di autenticazione esistenti  
 Un aspetto importante di qualsiasi modello di sicurezza della comunicazione è la possibilità di identificare e autenticare entità in comunicazione. Queste entità in comunicazione usano "identità digitali", o credenziali, per l'autenticazione con i peer in comunicazione. Con l'evolversi delle piattaforme di comunicazione distribuite sono state implementate varie funzionalità di autenticazione delle credenziali e modelli di sicurezza correlati. Su Internet, ad esempio, l'uso di un nome utente e di una password per identificare gli utenti è prassi comune. Sulla rete Intranet l'uso di un controller di dominio Kerberos per eseguire il backup dell'autenticazione degli utenti e dei servizi sta diventando una prassi comune. In certi scenari, ad esempio tra due partner aziendali, i certificati possono essere usati per l'autenticazione reciproca dei partner.  
  
 Così, nel mondo dei servizi Web, dove lo stesso servizio può essere esposto ai clienti interni dell'azienda così come a partner esterni o a clienti Internet, è importante che l'infrastruttura consenta l'integrazione con questi modelli di autenticazione della sicurezza esistenti. La sicurezza WCF supporta un'ampia varietà di tipi di credenziali (modelli di autenticazione), tra cui:  
  
- Chiamante anonimo.  
  
- Credenziale client nome utente.  
  
- Credenziale client certificato.  
  
- Windows (sia protocollo Kerberos che NT LanMan [NTLM]).  
  
### <a name="standards-and-interoperability"></a>Standard e interoperabilità  
 In un panorama caratterizzato da grandi distribuzioni esistenti, l'omogeneità è rara. Le piattaforme di calcolo/comunicazione distribuite devono poter interagire con le tecnologie offerte dai diversi fornitori. Anche la sicurezza deve essere quindi interoperativa.  
  
 Per consentire sistemi di sicurezza interoperativi, le aziende che operano nell'industria dei servizi Web hanno creato una serie di standard. Specificamente riguardo alla sicurezza sono stati proposti alcuni standard noti: WS-Security: SOAP Message Security (accettato tra gli standard OASIS e già noto come WS-Security), WS-Trust, WS-SecureConversation e WS-SecurityPolicy.  
  
 WCF supporta un'ampia gamma di scenari di interoperabilità. La classe <xref:System.ServiceModel.BasicHttpBinding> è associata allo standard Basic Security Profile (BSP) e la classe <xref:System.ServiceModel.WSHttpBinding> è associata agli standard di sicurezza più recenti quali WS-Security 1.1 e WS-SecureConversation. Aderendo a questi standard, la sicurezza WCF può interagire e integrarsi con i servizi Web ospitati in sistemi operativi e piattaforme diverse da Microsoft Windows.  
  
## <a name="wcf-security-functional-areas"></a>Aree funzionali della sicurezza di WCF  
 La sicurezza di WCF è divisa in tre aree funzionali: sicurezza del trasferimento, controllo di accesso e controllo. Nelle sezioni seguenti vengono descritte brevemente queste aree funzionali e vengono forniti collegamenti per altre informazioni.  
  
### <a name="transfer-security"></a>Sicurezza del trasferimento  
 La sicurezza del trasferimento comprende tre funzioni di sicurezza principali: integrità, riservatezza e autenticazione. L' *integrità* è la capacità di rilevare se un messaggio è stato alterato. La *riservatezza* è la possibilità di rendere illeggibile un messaggio da parte di altri utenti del destinatario. Questa operazione viene eseguita tramite la crittografia. L' *autenticazione* è la possibilità di verificare un'identità richiesta. Nel complesso queste tre funzioni consentono di garantire che i messaggi vengano inviati in modo protetto da un punto a un altro.  
  
#### <a name="transport-and-message-security-modes"></a>Modalità di sicurezza del trasporto e dei messaggi  
 Per implementare la sicurezza del trasferimento in WCF vengono usati due meccanismi principali: modalità di sicurezza del *trasporto* e modalità di sicurezza dei *messaggi* .  
  
- La *modalità di sicurezza del trasporto* utilizza un protocollo a livello di trasporto, ad esempio HTTPS, per ottenere la sicurezza del trasferimento. La modalità di sicurezza del trasporto ha il vantaggio di essere ampiamente diffusa, disponibile su più piattaforme e meno complessa dal punto di vista computazionale. Ha tuttavia lo svantaggio di proteggere i messaggi solo da punto a punto.  
  
- La *modalità di sicurezza del messaggio*, d'altra parte, USA WS-Security (e altre specifiche) per implementare la sicurezza del trasferimento. Poiché la sicurezza del messaggio viene applicata direttamente ai messaggi SOAP ed è contenuta negli elementi SOAP Envelope unitamente ai dati dell'applicazione, ha il vantaggio di essere indipendente dal protocollo di trasporto, di essere maggiormente estensibile e di garantire la sicurezza end-to-end (anziché point-to-point). Ha lo svantaggio di essere notevolmente più lenta rispetto alla modalità di sicurezza del trasporto perché deve trattare con la natura XML dei messaggi SOAP.  
  
 Per ulteriori informazioni su queste differenze, vedere [protezione di servizi e client](securing-services-and-clients.md).  
  
 Una terza modalità di sicurezza usa entrambe le modalità precedenti e sfrutta i vantaggi di entrambe. Questa modalità è detta `TransportWithMessageCredential`. In questa modalità la sicurezza del messaggio viene usata per autenticare il client e la sicurezza del trasporto viene usata per autenticare il server e fornire riservatezza e integrità dei messaggi. La modalità di sicurezza `TransportWithMessageCredential` è infatti veloce quasi quanto la modalità di sicurezza del trasporto e fornisce estensibilità per l'autenticazione client ugualmente alla modalità di sicurezza del messaggio. A differenza della modalità di sicurezza del messaggio, tuttavia, non fornisce la sicurezza end-to-end completa.  
  
### <a name="access-control"></a>Controllo di accesso  
 Il *controllo di accesso* è noto anche come autorizzazione. L' *autorizzazione* consente a utenti diversi di disporre di privilegi diversi per la visualizzazione dei dati. Ad esempio, poiché i file relativi alle risorse umane di un'azienda contengono dati riservati sui dipendenti, la visualizzazione di questi dati è consentita soltanto ai dirigenti, che possono tuttavia visualizzare soltanto i dati relativi ai propri subalterni. In questo caso, il controllo di accesso è basato sia sul ruolo ("dirigente") che sull'identità specifica del dirigente (per impedire a un dirigente di accedere ai record relativi ai subalterni di un altro dirigente).  
  
 In WCF, le funzionalità di controllo di accesso vengono fornite tramite l'integrazione con il Common Language Runtime (CLR) <xref:System.Security.Permissions.PrincipalPermissionAttribute> e tramite un set di API noto come *modello di identità*. Per informazioni dettagliate sul controllo di accesso e sull'autorizzazione basata sulle attestazioni, vedere [estensione della protezione](../extending/extending-security.md).  
  
### <a name="auditing"></a>Controllo  
 Il *controllo* è la registrazione degli eventi di sicurezza nel registro eventi di Windows. È possibile registrare eventi relativi alla sicurezza, ad esempio le operazioni di autenticazione riuscite o non riuscite. Per ulteriori informazioni, vedere [controllo](auditing-security-events.md). Per informazioni dettagliate sulla programmazione, vedere [procedura: controllare gli eventi di sicurezza](how-to-audit-wcf-security-events.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [Protezione dei servizi](../securing-services.md)
- [Scenari di sicurezza comuni](common-security-scenarios.md)
- [Associazioni e protezione](bindings-and-security.md)
- [Securing Services and Clients](securing-services-and-clients.md)
- [autenticazione](authentication-in-wcf.md)
- [Autorizzazione](authorization-in-wcf.md)
- [Federazione e token emessi](federation-and-issued-tokens.md)
- [Controllo](auditing-security-events.md)
- [Indicazioni di sicurezza e procedure consigliate](security-guidance-and-best-practices.md)
- [Configurazione dei servizi tramite file di configurazione](../configuring-services-using-configuration-files.md)
- [Associazioni fornite dal sistema](../system-provided-bindings.md)
- [Cenni preliminari sulla creazione di endpoint](../endpoint-creation-overview.md)
- [Estensione della protezione](../extending/extending-security.md)
- [Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
