---
title: Protocollo PNRP (Peer Name Resolution Protocol)
description: Informazioni sul protocollo PNRP (Peer Name Resolution Protocol), un protocollo sicuro, scalabile e dinamico per la registrazione e la risoluzione dei nomi.
ms.date: 03/30/2017
ms.assetid: 11940511-c124-4d91-ae31-d4ed6e81ee58
ms.openlocfilehash: 72eb63c2c90f398c515d77cd2b2d693237e533a5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502223"
---
# <a name="peer-name-resolution-protocol"></a>Protocollo PNRP (Peer Name Resolution Protocol)
Negli ambienti peer-to-peer, i peer usano sistemi di risoluzione dei nomi specifici per dedurre l'ubicazione di rete reciproca (indirizzi, protocolli e porte) dai nomi o altri tipi di identificatori. Nel passato, la risoluzione dei nomi peer era complicata dalla transitorietà intrinseca della connettività e da altri inconvenienti nel sistema DNS (Domain Name System).  
  
 La piattaforma di rete Microsoft® Windows® Peer-to-Peer Networking risolve il problema relativo al protocollo di risoluzione del nome del peer (PNRP), offrendo un protocollo sicuro, scalabile e dinamico di registrazione e risoluzione dei nomi sviluppato per la prima volta per Windows XP e quindi aggiornato in Windows Vista™. PNRP funziona in modo molto diverso dai tradizionali sistemi di risoluzione dei nomi, aprendo nuove ed entusiasmanti possibilità per gli sviluppatori di applicazioni.  
  
 Con PNRP, i nomi di peer possono essere applicati al computer oppure ad applicazioni o servizi singoli nel computer. Una risoluzione dei nomi peer contiene un indirizzo, una porta e probabilmente anche un payload esteso. I vantaggi di questo sistema includono la tolleranza di errore, l'assenza di colli di bottiglia e risoluzioni dei nomi che non restituiranno mai indirizzi non aggiornati. Il protocollo è quindi una soluzione eccellente per l'individuazione degli utenti mobili.  
  
 A livello di sicurezza, i nomi di peer possono essere pubblicati come protetti o non protetti. PNRP usa la crittografia a chiave pubblica per proteggere i nomi di peer sicuri dallo spoofing. Con PNRP si possono assegnare nomi sia ai computer che ai servizi.  
  
Il protocollo PNRP (Peer Name Resolution Protocol) ha le proprietà seguenti:  
  
- È un protocollo distribuito e quasi del tutto senza server. I server sono necessari solo per il processo di bootstrap.  
  
- Protezione della pubblicazione dei nomi senza il coinvolgimento di terze parti. Diversamente dalla pubblicazione dei nomi DNS, la pubblicazione dei nomi PNRP è istantanea e non comporta costi finanziari.  
  
- PNRP implementa gli aggiornamenti in tempo reale e ciò impedisce la risoluzione di indirizzi non aggiornati.  
  
- La risoluzione dei nomi tramite PNRP si estende oltre i computer, consentendo anche la risoluzione dei nomi per i servizi.  
  
## <a name="the-systemnetpeertopeer-namespace"></a>Spazio dei nomi System.Net.PeerToPeer  
  
- Le funzionalità del protocollo PNRP sono definite dallo spazio dei nomi <xref:System.Net.PeerToPeer> all'interno di .NET Framework versione 3.5. È disponibile un set di tipi che può essere usato per registrare e risolvere i nomi di peer con un servizio PNRP disponibile.  
  
- (È possibile creare e inizializzare resolver PNRP e resolver di peer personalizzati usando i tipi forniti dallo spazio dei nomi <xref:System.ServiceModel.PeerResolvers>.)  
  
- I tipi di base usati per registrare e risolvere i nomi con un servizio PNRP disponibile sono i seguenti:  
  
- <xref:System.Net.PeerToPeer.Cloud>: definisce le informazioni che descrivono un cloud PNRP disponibile, incluso il relativo ambito.  
  
- <xref:System.Net.PeerToPeer.PeerName>: definisce un nome di peer che può essere usato per registrare e risolvere successivamente un peer all'interno di un cloud.  
  
- <xref:System.Net.PeerToPeer.PeerNameRecord>: definisce il record nel cloud PNRP che contiene le informazioni di registrazione per un peer, che include gli endpoint di rete in cui è possibile contattare il peer.  
  
- <xref:System.Net.PeerToPeer.PeerNameRegistration>: definisce il processo di registrazione per un nome di peer, inclusi i metodi per avviare e arrestare la registrazione dei nomi di peer.  
  
- <xref:System.Net.PeerToPeer.PeerNameResolver>: definisce il processo per la risoluzione di un nome di peer negli endpoint di rete corrispondenti, inclusi sia i metodi sincroni che quelli asincroni per la risoluzione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.PeerResolvers>
- <xref:System.Net.PeerToPeer>
- [Esempi di programmazione di rete](network-programming-samples.md)

<!-- to-do: review sample links
- [PeerToPeer Technology Sample](https://go.microsoft.com/fwlink/?LinkID=179571)
-->
