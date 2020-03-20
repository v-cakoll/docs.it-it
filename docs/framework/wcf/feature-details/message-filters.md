---
title: Filtri messaggi
ms.date: 03/30/2017
helpviewer_keywords:
- routing [WCF], message filters
ms.assetid: cb33ba49-8b1f-4099-8acb-240404a46d9a
ms.openlocfilehash: a953dea9224d75907c593d87f06a0b0888f0af2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184667"
---
# <a name="message-filters"></a>Filtri messaggi
Per implementare il routing basato sul contenuto, il servizio di routing usa implementazioni di <xref:System.ServiceModel.Dispatcher.MessageFilter> che controllano sezioni specifiche di un messaggio, ad esempio l'indirizzo, il nome dell'endpoint o un'istruzione XPath. Se nessuno dei filtri messaggi disponibili in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] soddisfa le esigenze specifiche, è possibile creare un filtro personalizzato con un'implementazione della classe <xref:System.ServiceModel.Dispatcher.MessageFilter> di base.  
  
 Quando si configura il servizio di routing, è necessario definire gli elementi filtro (oggetti)<xref:System.ServiceModel.Routing.Configuration.FilterElement> che descrivono il tipo di **MessageFilter** e tutti i dati di supporto necessari per creare il filtro, ad esempio valori stringa specifici da cercare all'interno del messaggio. Si noti che la creazione di elementi di filtro consente solo di definire i singoli filtri messaggi. Per usare i filtri in modo da valutare e indirizzare i messaggio, è inoltre necessario definire una tabella di filtri (<xref:System.ServiceModel.Routing.Configuration.FilterTableEntryCollection>).  
  
 Ogni voce nella tabella dei filtri fa riferimento a un elemento di filtro e specifica l'endpoint client a cui indirizzare un messaggio se corrispondente ai criteri del filtro stesso. Le voci della tabella dei filtri consentono inoltre di specificare una raccolta di endpoint di backup (<xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection>) che rappresenta un elenco di endpoint a cui deve essere trasmesso il messaggio qualora si verifichi un errore di trasmissione durante l'invio all'endpoint primario. Verrà infatti tentato di inviare il messaggio a tali endpoint nell'ordine in cui sono specificati finché l'operazione non ha esito positivo.  
  
## <a name="message-filters"></a>Filtri messaggi  
 I filtri messaggi usati dal servizio di routing offrono funzionalità comuni di selezione dei messaggi, ad esempio la valutazione del nome dell'endpoint a cui viene inviato un messaggio, l'azione SOAP oppure l'indirizzo o il prefisso dell'indirizzo a cui è inviato il messaggio. È inoltre possibile unire i filtri con una condizione `AND` affinché i messaggi vengano indirizzati a un endpoint solo se corrispondono a entrambi i filtri. È inoltre possibile definire filtri personalizzati creando un'implementazione personalizzata di <xref:System.ServiceModel.Dispatcher.MessageFilter>.  
  
 Nella tabella seguente vengono indicati l'elemento <xref:System.ServiceModel.Routing.Configuration.FilterType> usato dal servizio di routing, la classe che implementa il filtro messaggi specificato e i parametri <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A> necessari.  
  
|Tipo di filtro|Descrizione|Significato dei dati del filtro|Filtro di esempio|  
|------------------|-----------------|-------------------------|--------------------|  
|Azione|Usa la classe <xref:System.ServiceModel.Dispatcher.ActionMessageFilter> per individuare i messaggi contenenti un'azione specifica.|L'azione in base a cui filtrare.|\<nome del filtro: "action1" filterType ""Action" filterData "http://namespace/contract/operation> /|  
|EndpointAddress|Utilizza <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter> la classe <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter.IncludeHostNameInComparison%2A>  ==  `true` , con per trovare una corrispondenza con i messaggi contenenti un indirizzo specifico.|Indirizzo in base al quale applicare il filtro (nell'intestazione To).|\<nome del filtro: "indirizzo1" filterType "IndirizzoEndpoint" filterData "http://host/vdir/s.svc/b/ >|  
|EndpointAddressPrefix|Utilizza <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> la classe <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter.IncludeHostNameInComparison%2A>  ==  `true` , con per trovare una corrispondenza con i messaggi contenenti un prefisso di indirizzo specifico.|Indirizzo in base al quale applicare il filtro usando la corrispondenza del prefisso più lunga.|\<nome del filtro: "prefisso1" filterType "EndpointAddressPrefix" filterData "http://host// />|  
|e|Usa la classe <xref:System.ServiceModel.Dispatcher.StrictAndMessageFilter> che esegue sempre la valutazione di entrambe le condizioni prima della restituzione.|filterData non viene utilizzato; invece filter1 e filter2 hanno i nomi dei filtri messaggi corrispondenti (anche nella tabella), che devono essere **ed**insieme.|\<nome filtro "and1" filterType "E" filtro1 "indirizzo1" filtro2 "azione1" />|  
|Personalizzato|Tipo definito dall'utente che estende la classe <xref:System.ServiceModel.Dispatcher.MessageFilter> e dispone di un costruttore che accetta una stringa.|L'attributo customType rappresenta il nome completo del tipo della classe da creare; filterData corrisponde alla stringa da passare al costruttore per la creazione del filtro.|\<nome del filtro: "custom1" filterType "Custom" customType "CustomAssembly.CustomMsgFilter, CustomAssembly" filterData "Dati personalizzati" />|  
|EndpointName|Usa la classe <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter> per individuar i messaggi in base al nome dell'endpoint del servizio su cui arrivano.|Il nome dell'endpoint del servizio, ad esempio: "serviceEndpoint1".  Deve essere uno degli endpoint esposti sul servizio di routing.|\<nome del filtro: "stock1" filterType " "Endpoint" filterData "SvcEndpoint" />|  
|MatchAll|Usa la classe <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>. Questo filtro corrisponde a tutti i messaggi in arrivo.|filterData non è usato. Questo filtro corrisponderà sempre a tutti i messaggi.|\<nome del filtro: "matchAll1" filterType "MatchAll" />|  
|XPath|Usa la classe <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> per individuare la corrispondenza con query XPath specifiche all'interno del messaggio.|Query XPath da usare per verificare la corrispondenza di messaggi.|\<nome del filtro: "XPath1" filterType "XPath" filterData "//ns:element" />|  
  
 Nell'esempio seguente vengono definite voci di filtro che usano i filtri messaggi XPath, EndpointName e PrefixEndpointAddress. In questo esempio viene illustrato l'uso di un filtro personalizzato per le voci RoundRobinFilter1 e RoundRobinFilter2.  
  
```xml  
<filters>  
     <filter name="XPathFilter" filterType="XPath"
             filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 1"/>  
     <filter name="EndpointNameFilter" filterType="EndpointName"
             filterData="calculatorEndpoint"/>  
     <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress"
             filterData="http://localhost/routingservice/router/rounding/"/>  
     <filter name="RoundRobinFilter1" filterType="Custom"
             customType="RoutingServiceFilters.RoundRobinMessageFilter,
             RoutingService" filterData="group1"/>  
     <filter name="RoundRobinFilter2" filterType="Custom"
             customType="RoutingServiceFilters.RoundRobinMessageFilter,
             RoutingService" filterData="group1"/>  
</filters>  
```  
  
> [!NOTE]
> La definizione di un filtro non è sufficiente a determinare la valutazione dei messaggi in base al filtro stesso. È necessario aggiungere il filtro a una tabella di filtri associato all'endpoint servizio esposto dal servizio di routing.  
  
### <a name="namespace-table"></a>Tabella degli spazi dei nomi  
 Se si usa un filtro XPath, i relativi dati contenenti la query XPath possono diventare di dimensioni notevoli a causa dell'uso degli spazi dei nomi. Per risolvere questo problema, il servizio di routing consente di definire prefissi degli spazi dei nomi personalizzati mediante un'apposita tabella.  
  
 La tabella degli spazi dei nomi è una raccolta di oggetti <xref:System.ServiceModel.Routing.Configuration.NamespaceElement> che definisce i prefissi degli spazi dei nomi comuni usabili in una query XPath. Di seguito sono indicati gli spazi dei nomi predefiniti e i relativi prefissi contenuti nella tabella.  
  
|Prefisso|Spazio dei nomi|  
|------------|---------------|  
|s11|`http://schemas.xmlsoap.org/soap/envelope`|  
|s12|`http://www.w3.org/2003/05/soap-envelope`|  
|wsaAugust2004|`http://schemas.xmlsoap.org/ws/2004/08/addressing`|  
|wsa10|`http://www.w3.org/2005/08/addressing`|  
|sm|`http://schemas.microsoft.com/serviceModel/2004/05/xpathfunctions`|  
|tempuri|`http://tempuri.org`|  
|ser|`http://schemas.microsoft.com/2003/10/Serialization`|  
  
 Se si prevede di usare uno specifico spazio dei nomi nelle query XPath, è possibile aggiungerlo alla tabella degli spazi dei nomi insieme a un prefisso univoco e usare quindi nella query XPath tale prefisso invece dello spazio dei nomi completo. Nell'esempio seguente viene definito un prefisso `"http://my.custom.namespace"`"custom" per lo spazio dei nomi , che viene quindi utilizzato nella query XPath contenuta in filterData.  
  
```xml  
<namespaceTable>  
     <add prefix="custom" namespace="http://my.custom.namespace/"/>  
</namespaceTable>  
<filters>  
     <filter name="XPathFilter" filterType="XPath" filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 1"/>  
</filters>  
```  
  
## <a name="filter-tables"></a>Tabelle dei filtri  
 Sebbene ogni elemento di filtro definisca un confronto logico da applicare a un messaggio, la tabella dei filtri consente l'associazione tra l'elemento di filtro e l'endpoint client di destinazione. Una tabella dei filtri è una raccolta denominata di oggetti <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement> che definiscono un'associazione tra un filtro, un endpoint di destinazione principale e un elenco di endpoint del backup alternativi. Le voci della tabella di filtro consentono inoltre di specificare facoltativamente una priorità per ogni condizione di filtro. Nell'esempio seguente vengono definiti due filtri, quindi viene definita una tabella che associa ogni filtro a un endpoint di destinazione.  
  
```xml  
<routing>  
     <filters>  
       <filter name="AddAction" filterType="Action" filterData="Add" />  
       <filter name="SubtractAction" filterType="Action" filterData="Subtract" />  
     </filters>  
     <filterTables>  
       <table name="routingTable1">  
         <filters>  
           <add filterName="AddAction" endpointName="Addition" />  
           <add filterName="SubtractAction" endpointName="Subtraction" />  
         </filters>  
       </table>  
     </filterTables>
</routing>  
```  
  
### <a name="filter-evaluation-priority"></a>Priorità di valutazione dei filtri  
 Per impostazione predefinita, tutte le voci della tabella dei filtri vengono valutate contemporaneamente e il messaggio esaminato viene indirizzato agli endpoint associati con le voci di filtri che corrispondono. Se più filtri restituiscono `true` ed il messaggio è unidirezionale o duplex, il messaggio è inviato in modalità multicast agli endpoint associati a tutti i filtri corrispondenti. I messaggi di tipo request/reply non possono essere multicast perché al client può essere restituita una sola risposta.  
  
 È possibile implementare logica di routing più complessa specificando livelli di priorità per ogni filtro. Il servizio di routing valuterà quindi prima tutti i filtri con priorità massima. Se un messaggio corrisponde a un filtro di questo livello, i filtri con priorità inferiore non vengono elaborati. Ad esempio, un messaggio unidirezionale in ingresso viene prima valutato rispetto a tutti i filtri con priorità 2. Il messaggio non corrisponde ad alcuno filtro di tale livello, pertanto il messaggio viene confrontato con i filtri di priorità 1. Due filtri di priorità 1 corrispondono al messaggio, pertanto si tratta di un messaggio unidirezionale inviato a entrambi gli endpoint di destinazione.  Poiché è stata individuata una corrispondenza con i filtri di priorità 1, non vengono visualizzati quelli con priorità 0.  
  
> [!NOTE]
> Se non viene specificata alcuna priorità, viene usata quella predefinita, ovvero 0.  
  
 Nell'esempio seguente viene definita una tabella di filtri con le priorità 2, 1 e 0 assegnate ai filtri a cui viene fatto riferimento.  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="XPathFilter" endpointName="roundingCalcEndpoint"
               priority="2"/>  
          <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint"
               priority="1"/>  
          <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint"
               priority="1"/>  
          <add filterName="MatchAllMessageFilter" endpointName="defaultCalcEndpoint"
               priority="0"/>  
     </filterTable>  
</filterTables>  
```  
  
 Nell'esempio precedente, se un messaggio corrisponde a XPathFilter, sarà indirizzato a roundingCalcEndpoint e non verrà valutato nessun altro filtro in quanto di priorità inferiore. Se tuttavia il messaggio non corrisponde a XPathFilter esso sarà valutato rispetto a tutti i filtri del livello di priorità immediatamente successivo, ovvero EndpointNameFilter e PrefixAddressFilter.  
  
> [!NOTE]
> Se possibile, usare filtri esclusivi anziché priorità perché la valutazione in base alla priorità può influire negativamente sulle prestazioni.  
  
### <a name="backup-lists"></a>Elenchi di backup  
 Per ogni filtro nella tabella dei filtri può essere specificato un elenco di backup, ovvero una raccolta denominata di endpoint (<xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection>). Tale raccolta contiene un elenco ordinato di endpoint a cui trasmettere il messaggio qualora si verifichi un'eccezione <xref:System.ServiceModel.CommunicationException> durante l'invio all'endpoint primario specificato in <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.EndpointName%2A>. Nell'esempio seguente viene definito un elenco di backup denominato "backupServiceEndpoints" che contiene due endpoint.  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
 Nell'esempio precedente, se un invio all'endpoint primario "Destinazione" ha esito negativo, il servizio di routing tenterà di inviare a ogni endpoint nella sequenza in cui sono elencati, inviando prima a backupServiceQueue e successivamente inviando a alternateServiceQueue se il invio a backupServiceQueue ha esito negativo. Se l'operazione non riesce con nessuno degli endpoint di backup, viene restituito un errore.
