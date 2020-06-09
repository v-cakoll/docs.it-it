---
title: Applicazioni client di livello intermedio
ms.date: 03/30/2017
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
ms.openlocfilehash: c50223a55765f211dae710f96bffa7716ce36b32
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598814"
---
# <a name="middle-tier-client-applications"></a>Applicazioni client di livello intermedio
In questo argomento vengono illustrati i vari problemi specifici per le applicazioni client di livello intermedio che utilizzano Windows Communication Foundation (WCF).  
  
## <a name="increasing-middle-tier-client-performance"></a>Miglioramento delle prestazioni dei client di livello intermedio  
 Rispetto alle tecnologie di comunicazione precedenti, ad esempio i servizi Web che usano ASP.NET, la creazione di un'istanza client WCF può essere più complessa grazie al set di funzionalità avanzate di WCF. Ad esempio, quando un oggetto <xref:System.ServiceModel.ChannelFactory%601> viene aperto può stabilire una sessione protetta con il servizio, una procedura che aumenta il tempo di avvio per l'istanza client. In genere, queste funzionalità aggiuntive non influiscono in modo significativo sulle applicazioni client, poiché il client WCF effettua diverse chiamate e quindi viene chiuso.  
  
 Le applicazioni client di livello intermedio, tuttavia, possono creare rapidamente molti oggetti client WCF e, di conseguenza, riscontrare un aumento dei requisiti di inizializzazione. Per migliorare le prestazioni delle applicazioni di livello intermedio durante le chiamate ai servizi è possibile seguire principalmente due diversi approcci:  
  
- Memorizzare nella cache l'oggetto client WCF e riutilizzarlo per le chiamate successive, ove possibile.  
  
- Creare un <xref:System.ServiceModel.ChannelFactory%601> oggetto e quindi utilizzare tale oggetto per creare nuovi oggetti canale client WCF per ogni chiamata.  
  
 Quando si seguono queste procedure è opportuno considerare gli aspetti seguenti:  
  
- Se il servizio gestisce uno stato specifico del client tramite una sessione, non è possibile riutilizzare il client WCF di livello intermedio con richieste a più livelli client perché lo stato del servizio è associato a quello del client di livello intermedio.  
  
- Se il servizio deve eseguire l'autenticazione per ogni singolo client, è necessario creare un nuovo client per ogni richiesta in ingresso nel livello intermedio anziché riutilizzare il client WCF di livello intermedio (o l'oggetto canale client WCF) perché le credenziali client del livello intermedio non possono essere modificate dopo la creazione del client WCF (o <xref:System.ServiceModel.ChannelFactory%601> ).  
  
- Sebbene i canali e i client creati dai canali siano thread-safe, è possibile che non supportino la scrittura di più messaggi in rete contemporaneamente. Se vengono inviati messaggi di grandi dimensioni, in particolare se viene eseguito il flusso, l'operazione di invio potrebbe bloccarsi in attesa del completamento di un'altra operazione di invio. Ciò causa due tipi di problemi: la mancanza di concorrenza e la possibilità di deadlock se il flusso di controllo torna al servizio riutilizzando il canale (ovvero, il client condiviso chiama un servizio il cui percorso di codice comporta un callback al client condiviso). Questo vale indipendentemente dal tipo di client WCF riutilizzato.  
  
- È necessario gestire i canali in stato di errore indipendentemente dal fatto che si condivida o meno il canale. Quando i canali vengono riutilizzati, un canale in stato di errore può tuttavia annullare più richieste o operazioni di invio in sospeso.  
  
 Per un esempio in cui vengono illustrate le procedure consigliate per il riutilizzo di un client per più richieste, vedere [Data Binding in an ASP.NET client](../samples/data-binding-in-an-aspnet-client.md).  
  
 È anche possibile migliorare le prestazioni di avvio per i client che usano tipi di dati serializzabili usando la classe <xref:System.Xml.Serialization.XmlSerializer> per generare e compilare il codice di serializzazione per questi tipi di dati in fase di esecuzione. Questa procedura può comportare una riduzione delle prestazioni di avvio. Lo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) può migliorare le prestazioni di avvio per queste applicazioni generando il codice di serializzazione necessario dagli assembly compilati per l'applicazione. Per ulteriori informazioni, vedere [procedura: migliorare il tempo di avvio delle applicazioni client WCF utilizzando XmlSerializer](startup-time-of-wcf-client-applications-using-the-xmlserializer.md).  
  
## <a name="see-also"></a>Vedere anche

- [Accesso ai servizi tramite client WCF](accessing-services-using-a-client.md)
