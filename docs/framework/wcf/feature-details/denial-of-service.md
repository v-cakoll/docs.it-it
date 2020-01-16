---
title: Denial of Service (Negazione del servizio)
ms.date: 03/30/2017
helpviewer_keywords:
- denial of service [WCF]
ms.assetid: dfb150f3-d598-4697-a5e6-6779e4f9b600
ms.openlocfilehash: 55120430a9aaafe7d8bbf2b26f07806e4f1aa44a
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964428"
---
# <a name="denial-of-service"></a>Denial of Service (Negazione del servizio)
Si verifica un attacco Denial of Service quando un sistema viene sommerso da una quantità di messaggi tale da non poter essere elaborata o da poter essere elaborata solo molto lentamente.  
  
## <a name="excess-memory-consumption"></a>Eccessivo consumo di memoria  
 Quando viene letto un documento XML con un numero elevato di nomi locali, spazi dei nomi o prefissi univoci, può verificarsi un problema. Se si usa una classe che deriva da <xref:System.Xml.XmlReader> e si chiama la proprietà <xref:System.Xml.XmlReader.LocalName%2A>, <xref:System.Xml.XmlReader.Prefix%2A> o <xref:System.Xml.XmlReader.NamespaceURI%2A> per ogni elemento, la stringa restituita viene aggiunta a una classe <xref:System.Xml.NameTable>. Le dimensioni della raccolta contenuta nella classe <xref:System.Xml.NameTable> non diminuiscono mai, creando una "perdita di memoria" virtuale degli handle di stringa.  
  
 Le strategie risolutive includono:  
  
- Derivare dalla classe <xref:System.Xml.NameTable> e imporre una quota della dimensione massima. Non è possibile impedire l'uso di una classe <xref:System.Xml.NameTable> o cambiare la classe <xref:System.Xml.NameTable> quando è completa.  
  
- Evitare di usare le proprietà citate e impiegare invece il metodo <xref:System.Xml.XmlReader.MoveToAttribute%2A> con il metodo <xref:System.Xml.XmlReader.IsStartElement%2A> quando possibile; questi metodi non restituiscono stringhe e non provocano quindi problemi di superamento della capacità della raccolta <xref:System.Xml.NameTable>.  
  
## <a name="malicious-client-sends-excessive-license-requests-to-service"></a>Il client dannoso invia un numero eccessivo di richieste di licenza al servizio  
 Se un client dannoso bombarda un servizio con un numero eccessivo di richieste di licenza, può costringere il server a usare troppa memoria.  
  
 Mitigazione: usare le proprietà seguenti della classe <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>:  
  
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxCachedCookies%2A>: controlla il numero massimo di classi `SecurityContextToken` temporali memorizzate nella cache dal server dopo la negoziazione `SPNego` o `SSL`.  
  
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.IssuedCookieLifetime%2A>: controlla la durata della classe `SecurityContextTokens` rilasciata dal server in seguito alla negoziazione `SPNego` o `SSL`. Il server memorizza nella cache la classe `SecurityContextToken` per questo periodo di tempo.  
  
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxPendingSessions%2A>: controlla il numero massimo di conversazioni protette stabilite nel server, per cui però non sono stati elaborati messaggi dell'applicazione. Questa quota impedisce ai client di stabilire conversazioni protette nel servizio, facendo così in modo che il servizio mantenga lo stato per client, senza mai usare i client.  
  
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.InactivityTimeout%2A>: controlla il tempo massimo in cui il servizio mantiene attiva una conversazione protetta senza ricevere un messaggio dell'applicazione dal client per la conversazione. Questa quota impedisce ai client di stabilire conversazioni protette nel servizio, facendo così in modo che il servizio mantenga lo stato per client, senza mai usare i client.  
  
## <a name="wsdualhttpbinding-or-dual-custom-bindings-require-client-authentication"></a>Necessità dell'autenticazione client per WSDualHttpBinding o per le doppie associazioni personalizzate  
 Per impostazione predefinita, <xref:System.ServiceModel.WSDualHttpBinding> ha la sicurezza abilitata. È tuttavia possibile che, se l'autenticazione client viene disattivata impostando la proprietà <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> su <xref:System.ServiceModel.MessageCredentialType.None>, un utente malintenzionato provochi un attacco Denial of Service in un terzo servizio. Ciò può verificarsi perché un client dannoso può indicare al servizio di inviare un flusso di messaggi a un terzo servizio.  
  
 Per prevenire il problema, non impostare la proprietà su `None`. Occorre essere consapevoli di questa possibilità quando si crea un'associazione personalizzata con un modello di messaggio doppio.  
  
## <a name="auditing-event-log-can-be-filled"></a>Possibilità di riempimento del registro eventi di controllo  
 Se un utente malintenzionato comprende che è attivato il controllo, può inviare messaggi non validi che causano la scrittura di voci di controllo. Ciò comporta a sua volta la generazione di errori nel sistema di controllo.  
  
 Per ridurre questo problema, impostare la proprietà <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> su `true` e usare le proprietà del Visualizzatore eventi per controllare il comportamento di controllo. Per ulteriori informazioni sull'utilizzo del Visualizzatore eventi per visualizzare e gestire i registri eventi, vedere [Visualizzatore eventi](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc766042(v=ws.11)). Per ulteriori informazioni, vedere [controllo](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
## <a name="invalid-implementations-of-iauthorizationpolicy-can-cause-service-to-become-unresponsive"></a>Le implementazioni di IAuthorizationPolicy non valide possono causare la mancata risposta del servizio  
 La chiamata del metodo <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> su un'implementazione non corretta dell'interfaccia <xref:System.IdentityModel.Policy.IAuthorizationPolicy> può causare la mancata risposta da parte del servizio.  
  
 Mitigazione: usare solo codice attendibile. In altre parole, usare solo codice scritto e verificato o proveniente da un provider attendibile. Non consentire l'aggiunta nel codice di estensioni non attendibili di <xref:System.IdentityModel.Policy.IAuthorizationPolicy> senza la dovuta considerazione. Questo vale per tutte le estensioni usate in un'implementazione del servizio. In WCF non viene fatta alcuna distinzione tra il codice dell'applicazione e il codice esterno collegato utilizzando i punti di estendibilità.  
  
## <a name="kerberos-maximum-token-size-may-need-resizing"></a>Possibile necessità di ridimensionamento per la dimensione massima dei token Kerberos  
 Se un client appartiene a un gran numero di gruppi (circa 900, anche se il numero effettivo varia a seconda dei gruppi), può verificarsi un problema quando il blocco dell'intestazione di un messaggio supera i 64 kilobyte. In tal caso, è possibile aumentare le dimensioni massime del token Kerberos. Potrebbe inoltre essere necessario aumentare la dimensione massima dei messaggi WCF per contenere il token Kerberos più grande.  
  
## <a name="autoenrollment-results-in-multiple-certificates-with-same-subject-name-for-machine"></a>Generazione da parte della registrazione automatica di più certificati per computer con lo stesso nome di soggetto  
 La *registrazione* automatica è la funzionalità di Windows Server 2003 per la registrazione automatica di utenti e computer per i certificati. Quando un computer si trova in un dominio con questa funzionalità attivata, viene automaticamente creato un certificato X.509 con l'obiettivo di eseguire l'autenticazione client, tale certificato viene quindi inserito nell'archivio dei certificati personali del computer locale ogni qualvolta un nuovo computer viene associato alla rete. Tuttavia, la registrazione automatica usa lo stesso nome di soggetto per tutti i certificati creati nella cache.  
  
 L'effetto è che i servizi WCF potrebbero non riuscire ad aprirsi nei domini con registrazione automatica. Ciò si verifica perché i criteri predefiniti per la ricerca delle credenziali X.509 del servizio potrebbero essere ambigui, dal momento che esistono più certificati con il nome DNS (Domain Name System) completo del computer. Un certificato ha origine dalla registrazione automatica, l'altro potrebbe invece essere un certificato autorilasciato.  
  
 Per attenuare questo problema, fare riferimento al certificato esatto da usare utilizzando un criterio di ricerca più preciso nel [\<ServiceCredentials](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md). Usare, ad esempio, l'opzione <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> e specificare il certificato in base all'identificazione personale univoca (hash).  
  
 Per ulteriori informazioni sulla funzionalità di registrazione automatica, vedere [registrazione automatica dei certificati in Windows Server 2003](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc778954(v%3dws.10)).  
  
## <a name="last-of-multiple-alternative-subject-names-used-for-authorization"></a>Uso per l'autorizzazione dell'ultimo dei diversi nomi di soggetto alternativi  
 Nel raro caso che un certificato X.509 contenga più nomi di soggetto alternativi e si esegua l'autorizzazione usando il nome di soggetto alternativo, l'autorizzazione potrebbe avere esito negativo.  
  
## <a name="protect-configuration-files-with-acls"></a>Protezione dei file di configurazione con elenchi di controllo di accesso (ACL)  
 È possibile specificare le attestazioni obbligatorie e facoltative nei file di codice e di configurazione per i token rilasciati da CardSpace. Ciò comporta l'emissione di elementi corrispondenti nei messaggi `RequestSecurityToken` inviati al servizio token di sicurezza. L'autore di un attacco può modificare il codice o la configurazione per rimuovere attestazioni obbligatorie o facoltative, facendo in modo che il servizio token di sicurezza rilasci un token che non consente l'accesso al servizio di destinazione.  
  
 Per prevenire il problema: richiedere l'accesso al computer per modificare il file di configurazione. Usare elenchi di controllo di accesso (ACL) per proteggere i file di configurazione. WCF richiede che il codice si trovi nella directory dell'applicazione o nella Global Assembly Cache prima di consentire il caricamento di tale codice dalla configurazione. Usare elenchi di controllo di accesso alle directory per proteggere le directory.  
  
## <a name="maximum-number-of-secure-sessions-for-a-service-is-reached"></a>Raggiunto il numero massimo di sessioni protette per un servizio  
 Quando un client viene correttamente autenticato da un servizio e viene stabilita una sessione protetta con il servizio, il servizio tiene traccia della sessione fino a quando il client non la annulla o la sessione non scade. Ogni sessione stabilita viene conteggiata a fronte del numero massimo consentito di sessioni attive simultanee con un servizio. Quando viene raggiunto questo limite, i client che tentano di creare una nuova sessione con il servizio in questione vengono rifiutati fino a quando una o più sessioni attive non scadono o non vengono annullate da un client. Un client può avere più sessioni con un servizio e ognuna di esse viene conteggiata per il raggiungimento del limite.  
  
> [!NOTE]
> Se si usano sessioni con stato, non vale quanto detto nel paragrafo precedente. Per altre informazioni sulle sessioni con stato, vedere [procedura: creare un token del contesto di sicurezza per una sessione protetta](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
 Per prevenire il problema, impostare il limite per il numero massimo di sessioni attive e la durata massima di una sessione impostando la proprietà <xref:System.ServiceModel.Channels.SecurityBindingElement> della classe <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
## <a name="see-also"></a>Vedere anche

- [Considerazioni sulla sicurezza](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)
- [Divulgazione di informazioni](../../../../docs/framework/wcf/feature-details/information-disclosure.md)
- [Elevazione dei privilegi](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)
- [Negazione del servizio](../../../../docs/framework/wcf/feature-details/denial-of-service.md)
- [Attacchi di tipo replay](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
- [Manomissioni](../../../../docs/framework/wcf/feature-details/tampering.md)
- [Scenari non supportati](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
