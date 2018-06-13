---
title: Applicazioni client di livello intermedio
ms.date: 03/30/2017
ms.assetid: f9714a64-d0ae-4a98-bca0-5d370fdbd631
ms.openlocfilehash: 4cca832266b2eb2ab7b1b4eb1a5fe937525db97d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493494"
---
# <a name="middle-tier-client-applications"></a>Applicazioni client di livello intermedio
In questo argomento vengono illustrati alcuni aspetti specifici per le applicazioni client di livello intermedio che usano Windows Communication Foundation (WCF).  
  
## <a name="increasing-middle-tier-client-performance"></a>Miglioramento delle prestazioni dei client di livello intermedio  
 Paragonata alle tecnologie di comunicazione precedenti, ad esempio servizi Web che usano [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], la creazione di un'istanza del client WCF può essere più complessa a causa del set completo di funzionalità di WCF. Ad esempio, quando un oggetto <xref:System.ServiceModel.ChannelFactory%601> viene aperto può stabilire una sessione protetta con il servizio, una procedura che aumenta il tempo di avvio per l'istanza client. In genere, queste funzionalità aggiuntive non influiscono sulle applicazioni client notevolmente poiché il client WCF effettua più chiamate e quindi viene chiusa.  
  
 Le applicazioni client di livello intermedio, tuttavia, possono creare rapidamente molti oggetti client WCF e, di conseguenza, esperienza maggiori requisiti di inizializzazione. Per migliorare le prestazioni delle applicazioni di livello intermedio durante le chiamate ai servizi è possibile seguire principalmente due diversi approcci:  
  
-   Memorizzare nella cache l'oggetto client WCF e riutilizzarla per le chiamate successive, dove possibile.  
  
-   Creare un <xref:System.ServiceModel.ChannelFactory%601> oggetto, quindi utilizzare quell'oggetto per creare oggetti di canale per ogni chiamata nuovi client WCF.  
  
 Quando si seguono queste procedure è opportuno considerare gli aspetti seguenti:  
  
-   Se il servizio gestisce uno stato di specifiche del client tramite una sessione, quindi non è possibile riutilizzare il client WCF di livello intermedio con richieste di vari livelli poiché lo stato del servizio è legato a quella del client di livello intermedio.  
  
-   Se il servizio deve eseguire l'autenticazione in base al client, è necessario creare un nuovo client per ogni richiesta in ingresso nel livello intermedio anziché riutilizzare il client WCF di livello intermedio (o un oggetto del canale client WCF) perché le credenziali del client di livello intermedio non può essere modificato dopo il client di WCF (o <xref:System.ServiceModel.ChannelFactory%601>) è stato creato.  
  
-   Sebbene i canali e i client creati dai canali siano thread-safe, è possibile che non supportino la scrittura di più messaggi in rete contemporaneamente. Se vengono inviati messaggi di grandi dimensioni, in particolare se viene eseguito il flusso, l'operazione di invio potrebbe bloccarsi in attesa del completamento di un'altra operazione di invio. Ciò causa due tipi di problemi: la mancanza di concorrenza e la possibilità di deadlock se il flusso di controllo torna al servizio riutilizzando il canale (ovvero, il client condiviso chiama un servizio il cui percorso di codice comporta un callback al client condiviso). Questo vale indipendentemente dal tipo di client WCF che è riutilizzare.  
  
-   È necessario gestire i canali in stato di errore indipendentemente dal fatto che si condivida o meno il canale. Quando i canali vengono riutilizzati, un canale in stato di errore può tuttavia annullare più richieste o operazioni di invio in sospeso.  
  
 Per un esempio che illustra le procedure consigliate per il riutilizzo di un client di più richieste, vedere [Data Binding in un Client ASP.NET](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md).  
  
 È anche possibile migliorare le prestazioni di avvio per i client che usano tipi di dati serializzabili usando la classe <xref:System.Xml.Serialization.XmlSerializer> per generare e compilare il codice di serializzazione per questi tipi di dati in fase di esecuzione. Questa procedura può comportare una riduzione delle prestazioni di avvio. Il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) può migliorare le prestazioni di avvio per queste applicazioni per la generazione del codice di serializzazione necessari dagli assembly compilati per l'applicazione. Per ulteriori informazioni, vedere [procedura: migliorare l'avvio del tempo di applicazioni Client WCF usando XmlSerializer](../../../../docs/framework/wcf/feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Accesso ai servizi tramite client WCF](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)
