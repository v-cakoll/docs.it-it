---
title: Scenari di routing
ms.date: 03/30/2017
helpviewer_keywords:
- routing [WCF], scenarios
ms.assetid: ec22f308-665a-413e-9f94-7267cb665dab
ms.openlocfilehash: 455a6e42aea064d48846994b4e729b90667bc8e1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590501"
---
# <a name="routing-scenarios"></a>Scenari di routing
Sebbene il servizio di routing sia notevolmente personalizzabile, può risultare difficile progettare una logica di routing efficiente quando si crea una nuova configurazione da zero.  Esistono tuttavia diversi scenari comuni seguiti dalla maggior parte delle configurazioni dei servizi di routing. Tali scenari possono non essere direttamente applicabili a una configurazione specifica, tuttavia comprendere le modalità di configurazione del servizio di routing per tali scenari consente di acquisire familiarità con le potenzialità del servizio stesso.  
  
## <a name="common-scenarios"></a>Scenari comuni  
 L'utilizzo più comune del servizio di routing consiste nell'aggregazione di più endpoint di destinazione allo scopo di ridurre il numero degli endpoint esposti alle applicazioni client e quindi nell'utilizzo di filtri messaggi per indirizzare ogni messaggio alla destinazione corretta. I messaggi possono essere indirizzati in base a requisiti di elaborazione fisica o logica, ad esempio a seconda che un messaggio debba essere elaborato da un servizio specifico o in base a esigenze aziendali arbitrarie quali l'elaborazione prioritaria a seconda dell'origine del messaggio. Nella tabella seguente vengono elencati alcuni scenari comuni e le circostanze in cui si verificano:  
  
|Scenario|Casi di utilizzo|  
|--------------|--------------|  
|Controllo delle versioni dei servizi|È necessario supportare più versioni di un servizio o prevedere la distribuzione futura di una versione aggiornata del servizio|  
|Partizionamento dei dati del servizio|È necessario partizionare un servizio tra più host|  
|Aggiornamento dinamico|È necessario riconfigurare dinamicamente la logica di routing al runtime per gestire distribuzioni del servizio mutevoli|  
|Multicast|È necessario inviare un messaggio a più endpoint|  
|Bridging del protocollo|Si ricevono messaggi su un protocollo di trasporto ma l'endpoint di destinazione usa un protocollo diverso|  
|Gestione degli errori|È necessario assicurare la continuità dei servizi in caso di limitazioni di rete ed errori di comunicazione|  
  
> [!NOTE]
> Sebbene molti degli scenari indicati siano specifici di precise esigenze aziendali o di particolari requisiti di elaborazione, prevedere il supporto per gli aggiornamenti dinamici e l'uso della gestione degli errori è spesso consigliabile in quanto in questo modo è possibile modificare la logica di routing al runtime e ripristinare i servizi in caso di errori di rete e di comunicazione temporanei.  
  
### <a name="service-versioning"></a>Controllo delle versioni dei servizi  
 Quando si introduce una nuova versione di un servizio è spesso necessario mantenere la versione precedente finché tutti i client non sono passati al nuovo servizio. Ciò è di particolare importanza se il servizio è un processo a esecuzione prolungata il cui completamento richiede giorni, settimane o perfino mesi. In questi casi, è in genere necessario implementare un nuovo indirizzo per l'endpoint del nuovo servizio e mantenere l'endpoint originale della versione precedente.  
  
 Con il servizio di routing è possibile esporre un endpoint affinché riceva i messaggi dalle applicazioni client e quindi indirizzare ogni messaggio alla versione corretta del servizio in base al contenuto del messaggio. L'implementazione più semplice prevede l'aggiunta di un'intestazione personalizzata al messaggio, la quale indichi la versione del servizio da cui deve essere elaborato il messaggio. Il servizio di routing può usare XPathMessageFilter per verificare in ogni messaggio la presenza dell'intestazione personalizzata e indirizzare il messaggio all'endpoint di destinazione appropriato.  
  
 Per i passaggi usati per creare una configurazione di controllo delle versioni del servizio, vedere [procedura: controllo delle versioni dei servizi](how-to-service-versioning.md).
  
### <a name="service-data-partitioning"></a>Partizionamento dei dati del servizio  
 Quando si progetta un ambiente distribuito, è spesso consigliabile suddividere il carico di elaborazione tra più computer in modo da offrire disponibilità elevata, ridurre il carico sui singoli computer o fornire risorse dedicate per uno specifico subset di messaggi. Sebbene il servizio di routing non sostituisca una soluzione di bilanciamento del carico dedicata, la possibilità di eseguire il routing basato sul contenuto consente di indirizzare messaggi simili a specifiche destinazioni. Potrebbe essere ad esempio necessario elaborare i messaggi di un determinato cliente separatamente da quelli ricevuti da altri client.  
  
 Per i passaggi usati per creare una configurazione di partizionamento dei dati del servizio, vedere [procedura: partizionamento dei dati del servizio](how-to-service-data-partitioning.md).  
  
### <a name="dynamic-routing"></a>Routing dinamico  
 È spesso necessario modificare la configurazione di routing per soddisfare nuove esigenze aziendali, ad esempio con l'aggiunta di una route a una versione più recente di un servizio, la modifica dei criteri di routing oppure la modifica dell'endpoint di destinazione di uno specifico messaggio. Queste modifiche sono possibile tramite <xref:System.ServiceModel.Routing.RoutingExtension> grazie al quale è possibile specificare una nuova configurazione di routing in fase di esecuzione. La nuova configurazione viene applicata immediatamente, ma influisce solo sulle nuove sessioni elaborate dal servizio di routing.  
  
 Per i passaggi usati per implementare il routing dinamico, vedere [procedura: aggiornamento dinamico](how-to-dynamic-update.md).
  
### <a name="multicast"></a>Multicast  
 Il routing dei messaggi avviene in genere a uno specifico endpoint di destinazione.  Può tuttavia risultare talvolta necessario indirizzare una copia del messaggio a più endpoint di destinazione. Per il routing multicast, è necessario che siano soddisfatte le condizioni seguenti:  
  
- La forma del canale non deve essere di tipo request/reply (tuttavia può essere unidirezionale o duplex), poiché tale forma impone che l'applicazione client debba ricevere una sola risposta alla richiesta.  
  
- Quando si valuta il messaggio, più filtri devono restituire **true** .  
  
 Se vengono soddisfatte queste condizioni, ogni endpoint di destinazione associato a un filtro che restituisce true riceverà una copia del messaggio.  
  
### <a name="protocol-bridging"></a>Bridging del protocollo  
 Per il routing dei messaggi tra protocolli SOAP diversi, il servizio di routing usa le API WCF per convertire il messaggio da un protocollo all'altro. Il bridging viene eseguito automaticamente se l'endpoint servizio esposto dal servizio di routing usa un protocollo diverso rispetto agli endpoint client ai quali vengono indirizzati i messaggi. È possibile disabilitare questo comportamento se i protocolli usati non sono standard; tuttavia, è necessario fornire codice di bridging specifico.
  
### <a name="error-handling"></a>Gestione degli errori  
 In un ambiente distribuito non è insolito che si verifichino errori di rete o di comunicazione temporanei. In assenza di un servizio intermediario quale quello di routing, la gestione di tali errori dipende dall'applicazione client. Se l'applicazione client non include logica specifica per eseguire un nuovo tentativo in caso di errori di rete o di comunicazione e non sono noti indirizzi alternativi, è possibile che un messaggio debba essere inviato più volte affinché possa essere elaborato correttamente dal servizio di destinazione. Ciò può determinare disservizi per i clienti che potrebbero considerare l'applicazione inaffidabile.  
  
 Il servizio di routing offre affidabili funzionalità di gestione degli errori di rete e di comunicazione allo scopo di rimediare a tali scenari. Creando un elenco di possibili endpoint di destinazione da associare a ogni filtro messaggi, è possibile evitare il singolo punto di errore determinato dalla presenza di un'unica possibile destinazione. In caso di errore, il servizio di routing tenta di recapitare il messaggio all'endpoint successivo nell'elenco finché l'operazione non ha esito positivo, si verifica un errore non di comunicazione o si esauriscono tutti gli endpoint.  
  
 Per i passaggi usati per configurare la gestione degli errori, vedere [procedura: gestione degli errori](how-to-error-handling.md).
  
### <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: controllo delle versioni dei servizi](how-to-service-versioning.md)  
  
 [Procedura: partizionamento dei dati del servizio](how-to-service-data-partitioning.md)  
  
 [Procedura: Aggiornamento dinamico](how-to-dynamic-update.md)  
  
 [Procedura: gestione degli errori](how-to-error-handling.md)  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione al routing](routing-introduction.md)
