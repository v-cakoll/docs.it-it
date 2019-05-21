---
title: Protezione di applicazioni del canale peer
ms.date: 03/30/2017
ms.assetid: d4a0311d-3f78-4525-9c4b-5c93c4492f28
ms.openlocfilehash: 4b52e0476ce6ac54a2e4a3a8cfceb112d662186b
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959878"
---
# <a name="securing-peer-channel-applications"></a>Protezione di applicazioni del canale peer
Analogamente alle altre associazioni in WinFX, `NetPeerTcpBinding` è attivata per impostazione predefinita la sicurezza e offre sia sicurezza basate sul trasporto e messaggio (o entrambi). In questo argomento vengono illustrati questi due tipi di sicurezza. Il tipo di sicurezza viene specificato dal tag della modalità di sicurezza nella specifica dell'associazione (<xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>`Mode` ).  
  
## <a name="transport-based-security"></a>Protezione basata sul trasporto  
 Il canale peer supporta due tipi di credenziali di autenticazione per la protezione del trasporto ed entrambi richiedono l'impostazione della proprietà `ClientCredentialSettings.Peer` sulla `ChannelFactory` associata:  
  
- Password. I client usano la conoscenza di una password segreta per autenticare le connessioni. Quando viene usato questo tipo di credenziale, `ClientCredentialSettings.Peer.MeshPassword` deve passare una password valida e, facoltativamente, un'istanza di `X509Certificate2`.  
  
- Certificato. Viene usata l'autenticazione dell'applicazione specifica. Quando viene usato questo tipo di credenziale, è necessario usare un'implementazione concreta di <xref:System.IdentityModel.Selectors.X509CertificateValidator> in `ClientCredentialSettings.Peer.PeerAuthentication`.  
  
## <a name="message-based-security"></a>Protezione basata sui messaggi  
 Usando la protezione dei messaggi, un'applicazione può firmare i messaggi in uscita in modo che tutte le parti riceventi possano verificare che il messaggio sia stato inviato da una parte attendibile e non sia stato manomesso. Il canale peer supporta attualmente solo la firma dei messaggi con la credenziale X.509.  
  
## <a name="best-practices"></a>Suggerimenti  
  
- Contenuto della sezione vengono illustrate le procedure consigliate per la protezione di applicazioni del canale peer.  
  
### <a name="enable-security-with-peer-channel-applications"></a>Attivare la protezione con le applicazioni del canale peer  
 A causa della natura distribuita dei protocolli del canale peer, è difficile imporre appartenenza, riservatezza e privacy in una rete non protetta. È inoltre importante ricordare di proteggere la comunicazione tra i client e il servizio resolver. In PNRP (Peer Name Resolution Protocol) usare nomi protetti per evitare lo spoofing e altri attacchi comuni. Proteggere un servizio resolver personalizzato attivando la protezione sui client di connessione usati per contattare il servizio resolver, prevedendo entrambe le forme di sicurezza, quella basata sul trasporto e quella basata sui messaggi.  
  
### <a name="use-the-strongest-possible-security-model"></a>Usare il modello di sicurezza più sicuro possibile  
 Ad esempio, se ogni membro della mesh deve essere identificato individualmente, usare il modello di autenticazione basato sui certificati. Se ciò non è possibile, usare l'autenticazione basata sulle password, seguendo i consigli correnti per mantenerle protette, tra cui sono inclusi i seguenti: condividere le password solo con parti attendibili, trasmettere le password usando un canale protetto, modificare le password frequentemente e verificare che le password siano complesse, che siano cioè lunghe almeno otto caratteri e includano almeno una lettera maiuscola e una minuscola, un numero e un carattere speciale.  
  
### <a name="never-accept-self-signed-certificates"></a>Non accettare mai certificati autofirmati  
 Non accettare mai una credenziale di certificato basata sui nomi dei soggetti. Si noti che chiunque può creare un certificato e chiunque può scegliere un nome che si sta convalidando. Per evitare la possibilità di spoofing, convalidare i certificati sulla base delle credenziali dell'autorità emittente (un'autorità emittente attendibile o un'autorità di certificazione radice).  
  
### <a name="use-message-authentication"></a>Usare l'autenticazione dei messaggi  
 Usare l'autenticazione dei messaggi per verificare che un messaggio abbia origine da una fonte attendibile e che non sia stato manomesso durante la trasmissione. Senza l'autenticazione dei messaggi è facile per un client dannoso effettuare lo spoofing dei messaggi nella mesh o manometterli.  
  
## <a name="peer-channel-code-examples"></a>Esempi di codice del canale peer  
 [Scenari relativi al canale peer](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md)  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza del canale peer](../../../../docs/framework/wcf/feature-details/peer-channel-security.md)
- [Creazione di un'applicazione del canale peer](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
