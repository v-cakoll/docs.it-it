---
title: Indirizzi endpoint
ms.date: 03/30/2017
helpviewer_keywords:
- addresses [WCF]
- Windows Communication Foundation [WCF], addresses
- WCF [WCF], addresses
ms.assetid: 13f269e3-ebb1-433c-86cf-54fbd866a627
ms.openlocfilehash: 71358ed1c16c3c9b490a41f74dd6319af8eb2e7b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593529"
---
# <a name="endpoint-addresses"></a>Indirizzi endpoint
A ogni endpoint è associato un indirizzo, che è utilizzato per individuarlo e identificarlo. L'indirizzo è costituito principalmente da un URI (Uniform Resource Identifier) che specifica il percorso dell'endpoint. L'indirizzo endpoint è rappresentato nel modello di programmazione Windows Communication Foundation (WCF) dalla <xref:System.ServiceModel.EndpointAddress> classe, che contiene una proprietà facoltativa <xref:System.ServiceModel.EndpointAddress.Identity%2A> che consente l'autenticazione dell'endpoint da altri endpoint che scambiano messaggi e un set di proprietà facoltative che <xref:System.ServiceModel.EndpointAddress.Headers%2A> definiscono qualsiasi altra intestazione SOAP necessaria per raggiungere il servizio. Le intestazioni facoltative forniscono dettagli aggiuntivi e più precisi sull'indirizzo per identificare o interagire con l'endpoint del servizio. L'indirizzo di un endpoint è rappresentato in transito come riferimento all'endpoint di WS-Addressing (EPR).  
  
## <a name="uri-structure-of-an-address"></a>Struttura URI di un indirizzo  
 L'indirizzo URI per la maggior parte dei trasporti è costituito da quattro parti. Ad esempio, le quattro parti dell'URI possono essere riportate `http://www.fabrikam.com:322/mathservice.svc/secureEndpoint` come indicato di seguito:  
  
- Schema`http:`
  
- Macchina`www.fabrikam.com`  
  
- (facoltativo) Porta: 322  
  
- Percorso: /mathservice.svc/secureEndpoint  
  
## <a name="defining-an-address-for-a-service"></a>Definizione di un indirizzo per un servizio  
 L'indirizzo endpoint per un servizio può essere specificato in modo imperativo mediante l'utilizzo di codice oppure in modo dichiarativo mediante la configurazione. In genere definire endpoint nel codice non è pratico in quanto le associazioni e gli indirizzi di un servizio distribuito sono solitamente diversi da quelli usati durante lo sviluppo del servizio. In genere è più pratico definire endpoint di servizio mediante la configurazione piuttosto che mediante codice. Se le informazioni sull'associazione e sull'indirizzo non vengono incluse nel codice, tali dati possono essere modificati senza dover compilare o distribuire nuovamente l'applicazione.  
  
### <a name="defining-an-address-in-configuration"></a>Definizione di un indirizzo nella configurazione  
 Per definire un endpoint in un file di configurazione, usare l' [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) elemento. Per informazioni dettagliate e un esempio, vedere [specifica di un indirizzo endpoint](../specifying-an-endpoint-address.md).  
  
### <a name="defining-an-address-in-code"></a>Definizione di un indirizzo nel codice  
 È possibile creare un indirizzo endpoint nel codice con la classe <xref:System.ServiceModel.EndpointAddress>. Per informazioni dettagliate e un esempio, vedere [specifica di un indirizzo endpoint](../specifying-an-endpoint-address.md).  
  
### <a name="endpoints-in-wsdl"></a>Endpoint in WSDL  
 Un indirizzo endpoint può essere rappresentato anche in WSDL come elemento EPR di WS-Addressing all'interno dell'elemento `wsdl:port` dell'endpoint corrispondente. L'EPR contiene l'indirizzo dell'endpoint e qualsiasi proprietà dell'indirizzo. Per informazioni dettagliate e un esempio, vedere [specifica di un indirizzo endpoint](../specifying-an-endpoint-address.md).  
  
## <a name="multiple-iis-binding-support-in-net-framework-35"></a>Supporto di più associazioni IIS in .NET Framework 3,5  
 I provider di servizi Internet consentono spesso di ospitare diverse applicazioni nello stesso server e nello stesso sito per aumentare la densità del sito e ridurre il costo totale di proprietà. Queste applicazioni sono in genere associate a indirizzi di base diversi. Un sito Web IIS (Internet Information Services) può contenere più applicazioni. Alle applicazioni in un sito è possibile accedere tramite una o più associazioni IIS.  
  
 Le associazioni IIS forniscono due tipi di informazioni: un protocollo di associazione e informazioni di associazione. Il protocollo di associazione definisce lo schema sul quale ha luogo la comunicazione, mentre le informazioni di associazione sono utilizzate per accedere al sito.  
  
 Nell'esempio seguente vengono illustrati i componenti che possono essere presenti in un'associazione IIS:  
  
- Protocollo di associazione: HTTP  
  
- Informazioni di associazione: indirizzo IP, porta, intestazione host  
  
 IIS può specificare più associazioni per ogni sito, il che comporta più indirizzi di base per ogni schema. Prima di .NET Framework 3,5, WCF non supportava più indirizzi per uno schema e, se fossero specificati, generava un' <xref:System.ArgumentException> durante l'attivazione.  
  
 Il .NET Framework 3,5 consente ai provider di servizi Internet di ospitare più applicazioni con indirizzi di base diversi per lo stesso schema nello stesso sito.  
  
 Un sito potrebbe contenere, ad esempio, gli indirizzi di base seguenti:  
  
- `http://payroll.myorg.com/Service.svc`
  
- `http://shipping.myorg.com/Service.svc`
  
 Con .NET Framework 3,5, è necessario specificare un filtro prefisso a livello di AppDomain nel file di configurazione. Questa operazione viene eseguita con l' [\<baseAddressPrefixFilters>](../../configure-apps/file-schema/wcf/baseaddressprefixfilters.md) elemento, che contiene un elenco di prefissi. Gli indirizzi di base in ingresso, forniti da IIS, sono filtrati in base all'elenco di prefissi facoltativo. Per impostazione predefinita, quando non è specificato un prefisso, vengono passati tutti gli indirizzi. La specifica del prefisso fa sì che venga passato solo l'indirizzo di base corrispondente per quello schema.  
  
 Quello che segue è un esempio di codice di configurazione che utilizza i filtri del prefisso.  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="net.tcp://payroll.myorg.com:8000"/>  
        <add prefix="http://shipping.myorg.com:8000"/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 Nell'esempio precedente, `net.tcp://payroll.myorg.com:8000` e `http://shipping.myorg.com:8000` sono gli unici indirizzi di base, per i rispettivi schemi, che vengono passati.  
  
 `baseAddressPrefixFilter` non supporta caratteri jolly.  
  
 Gli indirizzi di base forniti da IIS possono disporre di indirizzi associati ad altri schemi non presenti nell'elenco `baseAddressPrefixFilters`. Questi indirizzi non vengono filtrati.  
  
## <a name="multiple-iis-binding-support-in-net-framework-4-and-later"></a>Supporto per più binding IIS in .NET Framework 4 e versioni successive  
 A partire da .NET 4, è possibile abilitare il supporto di più associazioni in IIS senza dover scegliere un indirizzo di base unico, impostando la proprietà <xref:System.ServiceModel.ServiceHostingEnvironment> dell'oggetto <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A> su true. Questo supporto è limitato agli schemi del protocollo HTTP.  
  
 Di seguito è riportato un esempio di codice di configurazione che usa multipleSiteBindingsEnabled in [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) .  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment multipleSiteBindingsEnabled="true" >  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 Quando questa impostazione viene utilizzata per abilitare più binding di siti, tutte le impostazioni baseAddressPrefixFilters vengono ignorate, sia per i protocolli HTTP sia per quelli non HTTP.  
  
 Per informazioni dettagliate ed esempi, vedere [supporto di più binding del sito IIS](supporting-multiple-iis-site-bindings.md) e <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A> .  
  
## <a name="extending-addressing-in-wcf-services"></a>Estensione dell'indirizzamento nei servizi WCF  
 Il modello di indirizzamento predefinito dei servizi WCF utilizza l'URI dell'indirizzo dell'endpoint per gli scopi seguenti:  
  
- Per specificare l'indirizzo di ascolto del servizio, il percorso su cui l'endpoint resta in ascolto dei messaggi.  
  
- Per specificare il filtro dell'indirizzo SOAP, l'indirizzo che un endpoint si aspetta come intestazione SOAP.  
  
 I valori per ognuno di questi scopi possono essere specificati separatamente, consentendo numerose estensioni di indirizzamento a copertura di scenari utili:  
  
- Intermediari SOAP: un messaggio inviato da un client attraversa uno o più servizi aggiuntivi che elaborano il messaggio prima che raggiunga la sua destinazione finale. Gli intermediari SOAP possono eseguire numerose attività, ad esempio memorizzazione nella cache, routing, bilanciamento del carico o convalida dello schema sui messaggi. Per realizzare questo scenario, inviare messaggi a un indirizzo fisico separato (`via`) destinato all'intermediario piuttosto che a un indirizzo logico (`wsa:To`) per la destinazione finale.  
  
- L'indirizzo di ascolto dell'endpoint è un URI privato ed è impostato su un valore diverso dalla sua proprietà `listenURI`.  
  
 L'indirizzo di trasporto specificato da `via` è il percorso al quale dovrebbe inizialmente essere inviato un messaggio mentre si sta dirigendo verso un altro indirizzo remoto specificato dal parametro `to` in cui si trova il servizio. Nella maggior parte degli scenari Internet, l'URI `via` corrisponde alla proprietà <xref:System.ServiceModel.EndpointAddress.Uri%2A> dell'indirizzo finale `to` del servizio. La distinzione tra i due indirizzi è necessaria solo quando è richiesto il routing manuale.  
  
### <a name="addressing-headers"></a>Intestazioni di indirizzamento  
 Un endpoint può essere indirizzato da una o più intestazioni SOAP oltre che dal proprio URI di base. Ciò è utile, ad esempio, in presenza di scenari di intermediari SOAP in cui per un endpoint viene richiesto che nei relativi client siano incluse intestazioni SOAP destinate agli intermediari.  
  
 È possibile definire intestazioni di indirizzo personalizzate in due modi: codice o configurazione:  
  
- Nel codice, creare intestazioni di indirizzo personalizzate utilizzando la classe <xref:System.ServiceModel.Channels.AddressHeader>, quindi utilizzarle nella costruzione di un oggetto <xref:System.ServiceModel.EndpointAddress>.  
  
- Nella configurazione, i personalizzati [\<headers>](../../configure-apps/file-schema/wcf/headers.md) vengono specificati come elementi figlio dell' [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) elemento.  
  
 La configurazione è in genere preferibile al codice, poiché consente di modificare le intestazioni dopo la distribuzione.  
  
### <a name="custom-listening-addresses"></a>Indirizzi di ascolto personalizzati  
 È possibile impostare l'indirizzo di ascolto su un valore diverso dall'URI dell'endpoint. Ciò è utile negli scenari di intermediari in cui l'indirizzo SOAP da esporre è quello di un intermediario SOAP pubblico, mentre l'indirizzo su cui l'endpoint è effettivamente in ascolto è un indirizzo di rete privata.  
  
 È possibile specificare un indirizzo di ascolto personalizzato utilizzando codice o configurazione:  
  
- Nel codice, specificare un indirizzo di ascolto personalizzato aggiungendo una classe <xref:System.ServiceModel.Description.ClientViaBehavior> alla raccolta di comportamenti dell'endpoint.  
  
- In configurazione specificare un indirizzo di ascolto personalizzato con l' `ListenUri` attributo dell'elemento del servizio [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) .  
  
### <a name="custom-soap-address-filter"></a>Filtro dell'indirizzo SOAP personalizzato  
 <xref:System.ServiceModel.EndpointAddress.Uri%2A> viene utilizzato insieme a una proprietà <xref:System.ServiceModel.EndpointAddress.Headers%2A> per definire il filtro dell'indirizzo SOAP di un endpoint (<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>). Per impostazione predefinita, questo filtro consente di verificare che un messaggio in arrivo disponga di un'intestazione del messaggio `To` che corrisponde all'URI dell'endpoint e che nel messaggio siano presenti tutte le intestazioni dell'endpoint richieste.  
  
 In alcuni scenari, un endpoint riceve tutti i messaggi che arrivano sul trasporto sottostante e non solo quelli con l'intestazione `To` appropriata. Affinché ciò sia possibile, l'utente può utilizzare la classe <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>.  
  
## <a name="see-also"></a>Vedere anche

- [Specifica di un indirizzo dell'endpoint](../specifying-an-endpoint-address.md)
- [Identità del servizio e autenticazione](service-identity-and-authentication.md)
