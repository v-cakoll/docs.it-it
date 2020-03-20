---
title: Nomi di peer e ID PNRP
ms.date: 03/30/2017
ms.assetid: afa538e8-948f-4a98-aa9f-305134004115
ms.openlocfilehash: 15b74317507f69d2339a2e5e49b54ae72cda1a7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047495"
---
# <a name="peer-names-and-pnrp-ids"></a>Nomi di peer e ID PNRP
Il nome di peer rappresenta un endpoint per la comunicazione e può identificarsi in un computer, un utente, un gruppo, un servizio o qualsiasi altro elemento associato a un peer che può essere risolto in un indirizzo IPv6. Il protocollo PNRP (Peer Name Resolution Protocol) accetta il nome di peer statisticamente univoco per la creazione di un ID PNRP, usato per identificare i membri del cloud.  
  
## <a name="peer-names"></a>Nomi di peer  
 I nomi di peer possono essere registrati come non protetti o protetti. I nomi non protetti sono semplicemente stringhe di testo soggette a spoofing, dato che chiunque può registrare un nome non protetto duplicato. È consigliabile usare i nomi non protetti in reti private o comunque protette. I nomi protetti sono protetti da un certificato e una firma digitale. Solo chi li ha pubblicati inizialmente ne potrà dimostrare la proprietà.  
  
 La combinazione di cloud e ambito rende disponibile un ambiente adeguatamente protetto per i peer che partecipano alle attività PNRP. Tuttavia, l'uso di un nome di peer protetto non garantisce la sicurezza a livello generale dell'applicazione di rete. La sicurezza dell'applicazione è dipendente dall'implementazione.  
  
 I nomi di peer protetti vengono registrati solo dal proprietario e sono protetti con crittografia a chiave pubblica. Un nome di peer protetto viene considerato di proprietà dell'entità peer con la chiave privata corrispondente. La proprietà può essere dimostrata tramite l'indirizzo peer certificato (CPA), che viene firmato usando la chiave privata. Un utente malintenzionato non può falsificare la proprietà di un nome di peer senza la chiave privata corrispondente.  
  
## <a name="pnrp-ids"></a>ID PNRP  
 ![ID PNRP](./media/fdc9e8a0-4a1c-488d-a019-bc3a1973220c.gif "fdc9e8a0-4a1c-488d-a019-bc3a1973220c")  
  
 Gli ID PNRP sono composti di:  
  
- I 128 bit di ordine superiore, noti come ID peer-to-peer (P2P) sono un hash di un nome di peer assegnato all'endpoint. Il nome del peer ha il seguente formato: *Autorità.Classificatore*. Nel caso dei nomi protetti, *Autorità* è l'hash SHA1 (Secure Hash Algorithm 1 ) della chiave pubblica del nome di peer in caratteri esadecimali. Per i nomi non protetti, *Autorità* è il singolo carattere: "0". *Classificatore* è una stringa che identifica l'applicazione. Nessun classificatore per nome di peer può essere più lungo di 149 caratteri, compreso il carattere di terminazione `null`.  
  
- I 128 bit di ordine inferiore vengono usati per la posizione del servizio, ovvero un numero generato che identifica diverse istanze dello stesso ID P2P nello stesso cloud.  
  
 La combinazione di ID P2P e posizione del servizio consente la registrazione di più ID PNRP da un unico computer.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.PeerToPeer.PeerName>
- <xref:System.Net.PeerToPeer>
