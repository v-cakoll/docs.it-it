---
title: Protezione dei messaggi mediante protezione a livello di messaggio
ms.date: 03/30/2017
ms.assetid: a17ebe67-836b-4c52-9a81-2c3d58e225ee
ms.openlocfilehash: a6b062d0d6a74ce2a2ff9afa7e8a0a18853dbd22
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746439"
---
# <a name="securing-messages-using-message-security"></a>Protezione dei messaggi mediante protezione a livello di messaggio
In questa sezione viene illustrata la sicurezza del messaggio WCF quando si utilizza <xref:System.ServiceModel.NetMsmqBinding>.  
  
> [!NOTE]
> Prima di leggere questo argomento, è consigliabile leggere i [concetti relativi alla sicurezza](../../../../docs/framework/wcf/feature-details/security-concepts.md).  
  
 Nella figura seguente viene illustrato un modello concettuale di comunicazione in coda con WCF. L'illustrazione e la terminologia vengono utilizzate nella spiegazione  
  
 dei concetti della protezione del trasporto.  
  
 ![Diagramma dell'applicazione in coda](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "Distributed-Queue-Figure")  
  
 Quando si inviano messaggi in coda tramite WCF, il messaggio WCF viene allegato come corpo del messaggio di Accodamento messaggi (MSMQ). Mentre la protezione del trasporto protegge l'intero messaggio MSMQ, la protezione del messaggio, o SOAP, protegge il corpo del messaggio MSMQ.  
  
 Il concetto chiave della protezione del messaggio consiste nel fatto che il client protegge il messaggio per l'applicazione ricevente (servizio), a differenza dalla protezione del trasporto in cui il client protegge il messaggio per la coda di destinazione. Per questo motivo, MSMQ non svolge alcuna parte quando si protegge il messaggio WCF mediante la sicurezza dei messaggi.  
  
 La sicurezza dei messaggi WCF aggiunge intestazioni di sicurezza al messaggio WCF che si integrano con infrastrutture di sicurezza esistenti, ad esempio un certificato o il protocollo Kerberos.  
  
## <a name="message-credential-type"></a>Tipo di credenziali del messaggio  
 Mediante la protezione del messaggio il servizio e il client possono presentare credenziali per autenticarsi reciprocamente. È possibile selezionare la protezione del messaggio impostando la modalità <xref:System.ServiceModel.NetMsmqBinding.Security%2A> su `Message` o `Both` (ovvero per utilizzare sia la protezione del trasporto che la protezione del messaggio).  
  
 Il servizio può utilizzare la proprietà <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> per controllare la credenziale utilizzata per autenticare il client, nonché per ulteriori controlli di autorizzazione che il servizio scelga di implementare.  
  
 Contenuto della sezione vengono illustrati i diversi tipi di credenziali e viene spiegato come utilizzarli con le code.  
  
### <a name="certificate"></a>Certificato  
 Il tipo di credenziale del certificato utilizza un certificato X.509 per identificare il servizio e il client.  
  
 In uno scenario tipico il client e il servizio ricevono un certificato valido rilasciato da un'autorità di certificazione attendibile. La connessione viene quindi stabilita, il client autentica la validità del servizio utilizzando il certificato del servizio per decidere se il servizio è attendibile. Analogamente il servizio utilizza il certificato del client per verificare l'attendibilità del client.  
  
 In considerazione del fatto che le code funzionano spesso in modalità disconnessa, il client e il servizio potrebbero non essere in linea contemporaneamente e potrebbero doversi scambiare i certificati fuori banda. Il client, in particolare, poiché detiene il certificato del servizio (che può essere collegato a un'autorità di certificazione) nell'archivio attendibile, deve appurare di avere stabilito la comunicazione con il servizio corretto. Per autenticare il client, il servizio utilizza il certificato X.509 allegato al messaggio e cerca una corrispondenza con il certificato esistente nell'archivio. Anche in questo caso il certificato deve essere collegato a un'autorità di certificazione.  
  
 Nei computer che eseguono Windows i certificati sono contenuti in vari tipi di archivio. Per ulteriori informazioni sui diversi archivi, vedere [archivi certificati](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc757138(v=ws.10)).  
  
### <a name="windows"></a>Portale di  
 Il tipo di credenziale del messaggio di Windows utilizza il protocollo Kerberos.  
  
 Il protocollo Kerberos è un meccanismo di sicurezza che esegue l'autenticazione degli utenti in un dominio e consente agli utenti autenticati di stabilire una connessione protetta con le altre entità del dominio.  
  
 Il problema dell'utilizzo del protocollo Kerberos per la comunicazione in coda consiste nel fatto che i ticket che contengono l'identità client distribuita dal centro distribuzione chiavi (KDC, Key Distribution Center) hanno una durata limitata. Una *durata* è associata al ticket Kerberos che indica la validità del ticket. Per questa ragione e in considerazione della latenza elevata non è possibile avere la certezza che il token sia ancora valido per il servizio che autentica il client.  
  
 Si noti che in caso di utilizzo di questo tipo di credenziale, il servizio deve essere in esecuzione nell'account SERVIZIO.  
  
 Il protocollo Kerberos viene utilizzato per impostazione predefinita durante la scelta della credenziale del messaggio.
  
### <a name="username-password"></a>Nome utente/password  
 Mediante questa proprietà il client può eseguire l'autenticazione nel server utilizzando una password di nome utente nell'intestazione di sicurezza del messaggio.  
  
### <a name="issuedtoken"></a>IssuedToken  
 Il client può utilizzare il servizio token di sicurezza per rilasciare un token che può quindi essere allegato al messaggio affinché il servizio autentichi il client.  
  
## <a name="using-transport-and-message-security"></a>Utilizzo della protezione del trasporto e del messaggio  
 In caso di utilizzo della protezione del trasporto e della protezione del messaggio, il certificato utilizzato per proteggere il messaggio sia a livello di trasporto che a livello di messaggio SOAP deve essere lo stesso.  
  
## <a name="see-also"></a>Vedere anche

- [Protezione dei messaggi mediante la sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)
- [Sicurezza dei messaggi nell'accodamento messaggi](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
- [Concetti relativi alla sicurezza](../../../../docs/framework/wcf/feature-details/security-concepts.md)
- [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
