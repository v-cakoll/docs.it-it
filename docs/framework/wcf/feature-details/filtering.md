---
title: Filtro
ms.date: 03/30/2017
ms.assetid: 4002946c-e34a-4356-8cfb-e25912a4be63
ms.openlocfilehash: efbedc16fe48d83cdc4223862bc691e9cbe15c10
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964299"
---
# <a name="filtering"></a>Filtro
Il sistema di filtraggio Windows Communication Foundation (WCF) può utilizzare i filtri dichiarativi per trovare la corrispondenza con i messaggi e prendere decisioni operative. È possibile utilizzare filtri per determinare come comportarsi con un messaggio, esaminando parte di esso. Un processo di accodamento, ad esempio, può utilizzare una query XPath 1.0 per controllare l'elemento prioritario di un'intestazione nota e determinare se spostare un messaggio all'inizio della coda.  
  
 Il sistema di filtraggio è costituito da un set di classi che consentono di determinare in modo efficiente quale di un set di filtri sono `true` per un determinato messaggio WCF.  
  
 Il sistema di filtraggio è un componente principale della messaggistica WCF; è progettato per essere estremamente veloce. Ogni implementazione di filtro è stata ottimizzata per un particolare tipo di corrispondenza con i messaggi WCF.  
  
 Il sistema di filtraggio non è thread-safe. L'applicazione deve gestire qualsiasi semantica di blocco. Supporta, ad ogni modo, più reader e un solo writer.  
  
## <a name="where-filtering-fits"></a>Utilizzo di filtri  
 Il filtraggio viene eseguito dopo la ricezione di un messaggio e fa parte del processo di invio del messaggio al componente dell'applicazione corretto. La progettazione del sistema di filtro soddisfa i requisiti di diversi sottosistemi WCF, tra cui la messaggistica, il routing, la sicurezza, la gestione degli eventi e la gestione del sistema.  
  
## <a name="filters"></a>Filtri.  
 Il motore di filtraggio dispone di due componenti primari, filtri e tabelle dei filtri. Un filtro prende decisioni booleane su un messaggio in base alle condizioni logiche specificate dall'utente. I filtri implementano la classe <xref:System.ServiceModel.Dispatcher.MessageFilter>.  
  
 I metodi <xref:System.ServiceModel.Dispatcher.MessageFilter.Match%2A> vengono utilizzati per determinare se un messaggio soddisfa un filtro. Uno dei metodi controlla l'intestazione del messaggio, ma non può controllare il corpo del messaggio. L'altro metodo accetta un *buffer dei messaggi* come parametro di input e può ispezionare il corpo del messaggio.  
  
 I filtri generalmente non vengono controllati individualmente ma come parte di una tabella dei filtri che è una classe generica creata dal metodo <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601.CreateFilterTable%2A>.  
  
 Ogni filtro è specifico per un particolare tipo di condizione booleana. Dopo aver creato un filtro, è impossibile modificare i criteri che utilizza. Per modificarli, creare un nuovo filtro ed eliminare quello esistente.  
  
### <a name="action-filters"></a>Filtri per azioni  
 <xref:System.ServiceModel.Dispatcher.ActionMessageFilter> contiene un elenco di stringhe di azione. Se qualcuna delle azioni nell'elenco dei filtri corrisponde all'intestazione Action nel messaggio o nel buffer dei messaggi, il metodo `Match` restituisce `true`. Se l'elenco è vuoto, il filtro viene considerato a corrispondenza totale, dando luogo a una corrispondenza per qualsiasi messaggio o buffer dei messaggi e `Match` restituisce `true`. Se nessuna delle azioni nell'elenco dei filtri corrisponde all'intestazione Action nel messaggio o nel buffer dei messaggi, il metodo `Match` restituisce `false`. Se non c'è alcuna azione nel messaggio e l'elenco dei filtri non è vuoto, `Match` restituisce `false`.  
  
### <a name="endpoint-address-filters"></a>Filtri per indirizzi endpoint  
 <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter> filtra messaggi e buffer dei messaggi in base a un indirizzo endpoint, come rappresentato nella raccolta delle intestazioni. Affinché un messaggio superi tale filtro, devono essere soddisfatte le condizioni seguenti:  
  
- L'URI (Uniform Resource Identifier) dell'indirizzo del filtro deve essere lo stesso di quello presente nell'intestazione To del messaggio.  
  
- Ogni parametro dell'endpoint nell'indirizzo del filtro (raccolta `address.Headers`) deve trovare un'intestazione nel messaggio sulla quale eseguire il mapping. La corrispondenza rimane impostata su `true` anche in presenza di intestazioni aggiuntive nel messaggio o nel buffer dei messaggi.  
  
### <a name="prefix-endpoint-address-filters"></a>Filtri per indirizzi endpoint di prefisso  
  
1. Le funzioni <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> così come il filtro <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter> escludono che vi possa essere corrispondenza con un prefisso dell'URI del messaggio. Ad esempio, un filtro che specifica l'indirizzo `http://www.adatum.com` corrisponde ai messaggi indirizzati a `http://www.adatum.com/userA`.  
  
### <a name="xpath-message-filters"></a>Filtri per messaggi XPath  
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> utilizza un'espressione XPath per determinare se un documento XML contiene elementi specifici, attributi, testo o altri costrutti sintattici XML. Il filtro è ottimizzato per essere estremamente efficiente per un sottoinsieme esatto di XPath. Il linguaggio del percorso XML è descritto nella [specifica W3C XML Path language 1,0](https://www.w3.org/TR/xpath/all/).  
  
 In genere, un'applicazione utilizza <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> in un endpoint per eseguire una query sul contenuto di un messaggio SOAP e quindi agisce appropriatamente in base ai risultati della query. Un processo di accodamento, ad esempio, può utilizzare una query XPath per controllare l'elemento prioritario di un'intestazione nota per decidere se spostare un messaggio all'inizio della coda.  
  
## <a name="filter-tables"></a>Tabelle dei filtri  
 Le tabelle dei filtri vengono utilizzate per archiviare coppie di chiave-valore, dove un filtro corrisponde alla chiave e alcuni dati associati corrispondono al valore. I dati filtro possono essere utilizzati per indicare quali azioni intraprendere se un messaggio corrisponde a un filtro e il tipo di dati filtro è il parametro generico per la classe di tabella dei filtri. I dati filtro possono essere costituiti da regole di routing, stato di sicurezza della sessione, listener su un canale e così via. I dati possono essere utilizzati dove si rende necessario il controllo del flusso di dati.  
  
 Le tabelle dei filtri implementano l'interfaccia generica <xref:System.ServiceModel.Dispatcher.IMessageFilterTable%601>.  
  
 Le tabelle dei filtri dispongono di diversi metodi in grado di creare una corrispondenza tra un messaggio e tutti i filtri nella tabella e di restituire una raccolta non ordinata di dati o di filtri corrispondenti. Alcuni dei metodi di corrispondenza sono a corrispondenza multipla e restituiscono tutti gli elementi corrispondenti. Altri, che sono a corrispondenza singola, restituiscono un solo elemento e generano un'eccezione <xref:System.ServiceModel.Dispatcher.MultipleFilterMatchesException> se vi è corrispondenza con più di un filtro.  
  
### <a name="message-filter-table"></a>Tabelle dei filtri per messaggi  
 <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> è l'implementazione più generica di <xref:System.ServiceModel.Dispatcher.IMessageFilterTable%601>. Nella tabella è possibile archiviare filtri di tutti i tipi.  
  
 È possibile assegnare priorità numeriche ai filtri, dove la priorità più elevata è indicata dal numero più elevato. Più tipi di filtri possono avere la stessa priorità. Un particolare tipo di filtro può apparire in più di un livello di priorità.  
  
 La corrispondenza viene eseguita iniziando dalla priorità più elevata e, dopo aver trovato i filtri corrispondenti con una priorità specificata, non verranno esaminati altri filtri con priorità più basse. Se, pertanto, si sta utilizzando un metodo di corrispondenza a filtro singolo e più di un filtro corrisponde a un messaggio, ma ognuno ha una priorità diversa, non verrà generata alcuna eccezione e verrà restituito il filtro con la priorità più elevata. Allo stesso modo, un metodo di corrispondenza a più filtri restituisce solo i filtri corrispondenti con la priorità più elevata.  
  
### <a name="xpath-message-filter-table"></a>Tabelle dei filtri per messaggi XPath  
 <xref:System.ServiceModel.Dispatcher.XPathMessageFilterTable%601> è ottimizzato per filtri XPath dichiarativi, pertanto la chiave tabella è <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>.  
  
 La classe <xref:System.ServiceModel.Dispatcher.XPathMessageFilterTable%601> ottimizza la corrispondenza per un sottoinsieme di XPath che tratta la maggior parte degli scenari di messaggistica e supporta inoltre la grammatica di XPath 1.0 completa. Sono stati ottimizzati algoritmi per una corrispondenza parallela efficiente.  
  
 In questa tabella esistono diversi metodi `Match` specializzati che operano su <xref:System.Xml.XPath.XPathNavigator> e su <xref:System.ServiceModel.Dispatcher.SeekableXPathNavigator>. <xref:System.ServiceModel.Dispatcher.SeekableXPathNavigator> estende la classe <xref:System.Xml.XPath.XPathNavigator> aggiungendo una proprietà <xref:System.ServiceModel.Dispatcher.SeekableXPathNavigator.CurrentPosition%2A>. Questa proprietà consente di salvare e caricare velocemente le posizioni all'interno del documento XML, senza dovere clonare il navigatore, occupando molta memoria necessaria a <xref:System.Xml.XPath.XPathNavigator> per eseguire questa operazione. Il motore XPath WCF deve registrare frequentemente la posizione del cursore durante l'esecuzione di query su documenti XML, pertanto il <xref:System.ServiceModel.Dispatcher.SeekableXPathNavigator> fornisce un'importante ottimizzazione per l'elaborazione dei messaggi.  
  
## <a name="customer-scenarios"></a>Scenari utente  
 È possibile utilizzare i filtri in qualsiasi momento per inviare un messaggio a moduli di elaborazione differenti in base ai dati contenuti nel messaggio. Due scenari tipici sono il routing di un messaggio basato sul codice di azione e il demultiplexing di un flusso di messaggi basato sull'indirizzo endpoint dei messaggi.  
  
### <a name="routing"></a>Routing  
 Il listener di un endpoint è in ascolto di messaggi che dispongono di uno o più codici di azione nell'intestazione SOAP del messaggio. L'implementazione avviene tramite la creazione di <xref:System.ServiceModel.Dispatcher.ActionMessageFilter> con il passaggio al costruttore di una matrice che contiene i codici di azione. Questo filtro viene utilizzato per registrare in `ListenerFactory`, in tal modo solo i messaggi la cui azione corrisponde a una di quelle presenti nel filtro raggiungono quel particolare endpoint.  
  
### <a name="de-multiplexing"></a>Demultiplexing  
 Quando più endpoint eseguono il fan-out dallo stesso `ServiceListener` dalla rete, l'unico modo per eseguire demultiplexing sui messaggi e per sapere se appartengono a un certo indirizzo endpoint è utilizzare <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter>. In questo modo vengono selezionati i messaggi prossimi agli endpoint registrati eseguendo una ricerca sulle informazioni archiviate nelle intestazioni. In questi filtri, solo i messaggi che passano dispongono di tutte le intestazioni necessarie che corrispondono a entrambi:  
  
- L'URI in `EndpointAddress`.  
  
- Il resto dei parametri dell'endpoint in `EndpointAddress` come specificato in <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter>.  
  
## <a name="see-also"></a>Vedere anche

- [Trasferimento e serializzazione dei dati](../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
