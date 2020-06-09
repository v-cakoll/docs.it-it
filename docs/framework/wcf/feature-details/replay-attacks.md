---
title: Attacchi di tipo replay
ms.date: 03/30/2017
ms.assetid: 7a17e040-93cd-4432-81b9-9f62fec78c8f
ms.openlocfilehash: 47a4726859605415b4e3e1b4d523f2f8059a3989
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586299"
---
# <a name="replay-attacks"></a>Attacchi di tipo replay
Un *attacco di riproduzione* si verifica quando un utente malintenzionato copia un flusso di messaggi tra due parti e riproduce il flusso a una o più entità. Se l'attacco non viene respinto, i computer colpiti elaborano il flusso come se i messaggi fossero legittimi. Ciò determina una serie di conseguenze negative, ad esempio la creazione di ordini ridondanti di un articolo.  
  
## <a name="bindings-may-be-subject-to-reflection-attacks"></a>Vulnerabilità delle associazioni agli attacchi di tipo reflection  
 Gli *attacchi di Reflection* sono Riproduci dei messaggi in un mittente come se venissero restituiti dal ricevitore come risposta. Il *rilevamento della riproduzione* standard nel meccanismo Windows Communication Foundation (WCF) non viene gestito automaticamente.  
  
 Gli attacchi di Reflection vengono attenuati per impostazione predefinita perché il modello del servizio WCF aggiunge un ID messaggio firmato per richiedere messaggi e prevede un'intestazione firmata `relates-to` nei messaggi di risposta. Risulta di conseguenza impossibile riprodurre il messaggio di richiesta come risposta. Negli scenari che prevedono messaggi affidabili gli attacchi di tipo reflection vengono respinti per i motivi seguenti:  
  
- Lo schema dei messaggi di creazione di sequenza non corrisponde a quello di creazione di sequenza di risposta.  
  
- Per le sequenze simplex, i messaggi di sequenza inviati dal client non possono essere riprodotti verso il client stesso in quanto quest'ultimo non è in grado di riconoscere tali messaggi.  
  
- Per le sequenze duplex, i due ID di sequenza devono essere univoci. Inoltre, ogni intestazione e corpo della sequenza è firmato. Risulta pertanto impossibile riprodurre un messaggio di sequenza in uscita sottoforma di messaggio di sequenza in ingresso.  
  
 Le uniche associazioni vulnerabili agli attacchi di tipo reflection sono quelle in cui non viene applicata la specifica WS-Addressing, ovvero le associazioni personalizzate in cui la funzionalità WS-Addressing è stata disattivata e in cui si utilizza la protezione basata su chiavi simmetriche. Per impostazione predefinita, l'associazione <xref:System.ServiceModel.BasicHttpBinding> non applica la specifica WS-Addressing. Tuttavia, tale associazione presenta una modalità di sicurezza basata su chiavi simmetriche in grado di respingere gli attacchi di questo tipo.  
  
 Affinché le associazioni personalizzate siano in grado di respingere gli attacchi di tipo reflection è necessario richiedere l'utilizzo di intestazioni WS-Addressing oppure evitare di stabilire contesti di sicurezza.  
  
## <a name="web-farm-attacker-replays-request-to-multiple-nodes"></a>Web farm: attacco basato sulla riproduzione di richieste verso più nodi  
 Si consideri il caso di un client che utilizza un servizio implementato in una Web farm. In questo caso un utente malintenzionato può riprodurre una richiesta inviata a un determinato nodo della farm verso un'altro nodo della stessa farm. Inoltre, se un servizio viene riavviato, la cache di riproduzione viene svuotata. Ciò consente a un utente malintenzionato di riprodurre una richiesta. Nota: una cache di riproduzione contiene i valori di firma dei messaggi usati o già visualizzati e impedisce che tali firme vengano utilizzate più di una volta, respingendo in questo modo gli attacchi di tipo replay. Tuttavia, le funzionalità di una cache di riproduzione non vengono estese all'intera Web farm.  
  
 Le mitigazioni includono:  
  
- Usare una modalità di sicurezza dei messaggi che preveda token del contesto di sicurezza con stato. La funzionalità di conversazione protetta può essere attiva o disattivata. Per altre informazioni, vedere [procedura: creare un token del contesto di sicurezza per una sessione protetta](how-to-create-a-security-context-token-for-a-secure-session.md).  
  
- Configurare il servizio in modo che utilizzi un meccanismo di sicurezza a livello di trasporto.  
  
## <a name="see-also"></a>Vedere anche

- [Security Considerations](security-considerations-in-wcf.md)
- [Divulgazione di informazioni](information-disclosure.md)
- [Elevazione dei privilegi](elevation-of-privilege.md)
- [Attacco Denial of Service](denial-of-service.md)
- [Manomissione](tampering.md)
- [Scenari non supportati](unsupported-scenarios.md)
