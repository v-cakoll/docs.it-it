---
title: Panoramica sul modello di programmazione HTTP Web WCF
ms.date: 03/30/2017
ms.assetid: 381fdc3a-6e6c-4890-87fe-91cca6f4b476
ms.openlocfilehash: fb6ef0fdcefbc6ceec75ce30db3abf5896d85c61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184178"
---
# <a name="wcf-web-http-programming-model-overview"></a>Panoramica sul modello di programmazione HTTP Web WCF
Il modello di programmazione HTTP WEB di Windows Communication Foundation (WCF) fornisce gli elementi di base necessari per compilare servizi HTTP WEB con WCF. I servizi HTTP WEB WCF sono progettati per l'accesso da parte della più ampia gamma di client possibili, inclusi i browser Web, e presentano i requisiti univoci seguenti:  
  
- **URI ed elaborazione URI** Gli URI svolgono un ruolo centrale nella progettazione dei servizi HTTP WEB. Il modello di programmazione <xref:System.UriTemplate> <xref:System.UriTemplateTable> HTTP WEB WCF utilizza le classi e per fornire funzionalità di elaborazione URI.  
  
- **Supporto per operazioni GET e POST** I servizi HTTP WEB utilizzano il verbo GET per il recupero dei dati, oltre a vari verbi invoke per la modifica dei dati e la chiamata remota. Il modello di programmazione <xref:System.ServiceModel.Web.WebGetAttribute> <xref:System.ServiceModel.Web.WebInvokeAttribute> HTTP WEB WCF utilizza e per associare le operazioni del servizio a GET e altri verbi HTTP come PUT, POST e DELETE.  
  
- **Formati dati multipli** I servizi di tipo Web elaborano molti tipi di dati oltre ai messaggi SOAP. Il modello di programmazione <xref:System.ServiceModel.WebHttpBinding> <xref:System.ServiceModel.Description.WebHttpBehavior> HTTP WEB WCF utilizza e per supportare molti formati di dati diversi, tra cui documenti XML, oggetti dati JSON e flussi di contenuto binario, ad esempio immagini, file video o testo normale.  
  
 Il modello di programmazione HTTP WEB WCF estende la portata di WCF per illustrare scenari in stile Web che includono servizi HTTP WEB, servizi AJAX e JSON e feed Syndication (ATOM/RSS). Per altre informazioni sui servizi AJAX e JSON, vedere [Integrazione AJAX e supporto JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md). Per ulteriori informazioni su Syndication, vedere [Cenni preliminari](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)sulla diffusione WCF .  
  
 Non sono previste restrizioni aggiuntive sui tipi di dati che possono essere restituiti da un servizio HTTP Web. Qualsiasi tipo serializzabile può essere restituito da un'operazione del servizio HTTP Web. Poiché le operazioni del servizio HTTP Web possono essere richiamate da un Web browser, esiste una limitazione per i tipi di dati che possono essere specificati in un URL. Per altre informazioni sui tipi supportati per impostazione predefinita, vedere la sezione Parametri e URL della stringa di **query UriTemplate** di seguito. È possibile modificare il comportamento predefinito fornendo l'implementazione T:System.ServiceModel.Dispatcher.QueryStringConverter che specifica come convertire i parametri specificati in un URL nel tipo di parametro effettivo. Per altre informazioni, vedere <xref:System.ServiceModel.Dispatcher.QueryStringConverter>  
  
> [!CAUTION]
> I servizi scritti con il modello di programmazione HTTP WEB WCF non utilizzano messaggi SOAP. Poiché SOAP non viene utilizzato, non è possibile utilizzare le funzionalità di sicurezza fornite da WCF. È tuttavia possibile implementare la sicurezza basata sul trasporto ospitando il servizio con HTTPS. Per altre informazioni sulla sicurezza WCF, vedere Cenni preliminari sulla [sicurezzaFor](../../../../docs/framework/wcf/feature-details/security-overview.md) more information about WCF security, see Security Overview  
  
> [!WARNING]
> L'installazione dell'estensione WebDAV per IIS può causare la restituzione di un errore HTTP 405 da parte dei servizi HTTP Web quando tramite l'estensione WebDAV viene effettuato il tentativo di gestire tutte le richieste PUT. Per risolvere questo problema è possibile disinstallare l'estensione WebDAV o disabilitarla per il sito Web. Per ulteriori informazioni, vedere [IIS e WebDav](https://learn.iis.net/page.aspx/357/webdav-for-iis-70/)  
  
## <a name="uri-processing-with-uritemplate-and-uritemplatetable"></a>Elaborazione di URI con UriTemplate e UriTemplateTable  
 I modelli URI forniscono una sintassi efficiente per esprimere grandi set di URI strutturalmente simili. Nel modello seguente, ad esempio, viene espresso il set di tutti gli URI di tre segmenti che iniziano con "a" e terminano con "c", a prescindere dal valore del segmento intermedio: a/{segment}/c  
  
 In questo modello vengono descritti URI come il seguente:  
  
- a/x/c  
  
- a/y/c  
  
- a/z/c  
  
- e così via.  
  
 In questo modello, la notazione tra parentesi graffe ("{segment}") indica un segmento variabile anziché un valore letterale.  
  
 In .NET Framework è disponibile un'API da utilizzare con i modelli URI denominata <xref:System.UriTemplate>. Con `UriTemplates` è possibile effettuare le seguenti operazioni:  
  
- È possibile chiamare `Bind` uno dei metodi con un set di parametri per produrre un *URI completamente chiuso* che corrisponde al modello. Ciò significa che tutte le variabili all'interno del modello URI vengono sostituite con i valori effettivi.  
  
- È possibile chiamare `Match`() con un URI candidato che utilizza un modello per suddividere un URI candidato nelle sue parti costitutive e restituisce un dizionario che contiene le varie parti dell'URI etichettate in base alle variabili nel modello.  
  
- `Bind`() e `Match`() sono inverse, pertanto è possibile chiamare `Match`( `Bind`( x ) ) e ottenere lo stesso ambiente dal quale si è partiti.  
  
 Spesso si desidera tenere traccia (specialmente sul server, dove è necessario inviare una richiesta a un'operazione del servizio basata sull'URI) di un set di oggetti <xref:System.UriTemplate> in una struttura dati che possa fare riferimento in modo indipendente a ciascuno dei modelli contenuti. <xref:System.UriTemplateTable> rappresenta un set di modelli URI e seleziona la migliore corrispondenza in base a un set di modelli e a un URI candidato. Questo non è affiliato con qualsiasi particolare stack di rete (WCF incluso) in modo da poterlo utilizzare dove necessario.  
  
 Il modello di servizio WCF si avvale di <xref:System.UriTemplate> e <xref:System.UriTemplateTable> per associare operazioni del servizio a un set di URI descritti da un <xref:System.UriTemplate>. Un'operazione del servizio viene associata a un <xref:System.UriTemplate>, utilizzando <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute>. Per ulteriori <xref:System.UriTemplate> informazioni <xref:System.UriTemplateTable>su e , vedere [UriTemplate e UriTemplateTableFor](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md) more information about, see UriTemplate and UriTemplateTable  
  
## <a name="webget-and-webinvoke-attributes"></a>Attributi WebGet e WebInvoke  
 I servizi HTTP WCF WEB utilizzano verbi di recupero (ad esempio HTTP GET) oltre a vari verbi invoke (ad esempio HTTP POST, PUT e DELETE). Il modello di programmazione HTTP WEB WCF consente agli sviluppatori di servizi <xref:System.ServiceModel.Web.WebGetAttribute> di <xref:System.ServiceModel.Web.WebInvokeAttribute>controllare sia il modello URI che il verbo associato alle operazioni del servizio con e . <xref:System.ServiceModel.Web.WebGetAttribute> e <xref:System.ServiceModel.Web.WebInvokeAttribute> consentono di controllare l'associazione di singole operazioni con gli URI e i metodi HTTP associati a detti URI. L'aggiunta di <xref:System.ServiceModel.Web.WebGetAttribute> e <xref:System.ServiceModel.Web.WebInvokeAttribute>, ad esempio, nel codice seguente.  
  
```csharp
[ServiceContract]  
interface ICustomer  
{  
  //"View It"  
  
  [WebGet]  
  Customer GetCustomer():  
  
  //"Do It"  
    [WebInvoke]  
  Customer UpdateCustomerName( string id,
                               string newName );  
}  
```  
  
 Il codice precedente consente di effettuare le richieste HTTP seguenti.  
  
 `GET /GetCustomer`  
  
 `POST /UpdateCustomerName`  
  
 L'impostazione predefinita di <xref:System.ServiceModel.Web.WebInvokeAttribute> è POST ma è possibile utilizzarlo anche per altri verbi.  
  
```csharp
[ServiceContract]  
interface ICustomer  
{  
  //"View It" -> HTTP GET  
    [WebGet( UriTemplate="customers/{id}" )]  
  Customer GetCustomer( string id ):  
  
  //"Do It" -> HTTP PUT  
  [WebInvoke( UriTemplate="customers/{id}", Method="PUT" )]  
  Customer UpdateCustomer( string id, Customer newCustomer );  
}  
```  
  
 Per visualizzare un esempio completo di un servizio WCF che utilizza il modello di programmazione HTTP WEB WCF, vedere [Procedura: creare un servizio HTTP Web WCF di baseTo](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md) see a complete sample of a WCF service that uses the WCF WEB HTTP programming model, see How to: Create a Basic WCF Web HTTP Service  
  
## <a name="uritemplate-query-string-parameters-and-urls"></a>Nome del parametro della stringa di query UriTemplate e URL.  
 I servizi Web possono essere chiamati da un browser Web digitando un URL associato a un'operazione del servizio. Queste operazioni del servizio possono accettare parametri della stringa di query che devono essere specificati in un formato stringa all'interno dell'URL. Nella tabella seguente vengono illustrati i tipi che è possibile passare all'interno di un URL e il formato utilizzato.  
  
|Type|Format|  
|----------|------------|  
|<xref:System.Byte>|0-255|  
|<xref:System.SByte>|-128 - 127|  
|<xref:System.Int16>|-32768 - 32767|  
|<xref:System.Int32>|-2,147,483,648 - 2,147,483,647|  
|<xref:System.Int64>|-9,223,372,036,854,775,808 - 9,223,372,036,854,775,807|  
|<xref:System.UInt16>|0 - 65535|  
|<xref:System.UInt32>|0 - 4,294,967,295|  
|<xref:System.UInt64>|0 - 18,446,744,073,709,551,615|  
|<xref:System.Single>|-3,402823e38 - 3,402823e38 (la notazione esponenziale non è obbligatoria)|  
|<xref:System.Double>|-1,79769313486232e308 - 1,79769313486232e308 (la notazione esponenziale non è obbligatoria)|  
|<xref:System.Char>|Un solo carattere|  
|<xref:System.Decimal>|Qualsiasi numero decimale in notazione standard (nessun esponente)|  
|<xref:System.Boolean>|True o False (senza distinzione maiuscole/minuscole)|  
|<xref:System.String>|Qualsiasi stringa (la stringa null non è supportata e non viene effettuata alcuna operazione di escape)|  
|<xref:System.DateTime>|MM/GG/AAAA<br /><br /> MM/GG/AAAA HH:MM:SS [AM&#124;PM]<br /><br /> Mese Giorno Anno<br /><br /> Mese Giorno Anno HH:MM:SS [AM&#124;PM]|  
|<xref:System.TimeSpan>|GG.HH:MM:SS<br /><br /> Dove GG = Giorni, HH = Ore, MM = Minuti, SS = Secondi|  
|<xref:System.Guid>|Un GUID, ad esempio:<br /><br /> 936DA01F-9ABD-4d9d-80C7-02AF85C822A8|  
|<xref:System.DateTimeOffset>|MM/GG/AAAA HH:MM:SS MM:SS<br /><br /> Dove GG = Giorni, HH = Ore, MM = Minuti, SS = Secondi|  
|Enumerazioni|Valore di enumerazione che definisce l'enumerazione come illustrato nel codice seguente.<br /><br /> `public enum Days{ Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday };`<br /><br /> Nella stringa di query è possibile specificare uno qualsiasi dei singoli valori di enumerazione (o i valori integer corrispondenti).|  
|Tipi con `TypeConverterAttribute` in grado di convertire il tipo in e da una rappresentazione di stringa.|Dipende dal convertitore del tipo.|  
  
## <a name="formats-and-the-wcf-web-http-programming-model"></a>Formati e modello di programmazione HTTP Web WCF  
 Il modello di programmazione HTTP WEB WCF include nuove funzionalità per l'utilizzo con molti formati di dati diversi. A livello di associazione, <xref:System.ServiceModel.WebHttpBinding> è in grado di leggere e scrivere i diversi tipi di dati seguenti:  
  
- XML  
  
- JSON  
  
- Flussi binari opachi  
  
 Ciò significa che il modello di programmazione HTTP WEB WCF <xref:System.IO.Stream>può gestire qualsiasi tipo di dati, ma è possibile che si stia programmando in base a .  
  
 .NET Framework 3.5 fornisce il supporto per i dati JSON (AJAX) e i feed di diffusione (inclusi ATOM e RSS). For more information about these features, see [WCF Web HTTP Formatting](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)[WCF Syndication Overview](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md) and [AJAX Integration and JSON Support](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md).  
  
## <a name="wcf-web-http-programming-model-and-security"></a>Modello di programmazione HTTP Web WCF e sicurezza  

Poiché il modello di programmazione HTTP WEB WCF non supporta i protocolli WS- , l'unico modo per proteggere un servizio HTTP WEB WCF consiste nell'esporre il servizio tramite HTTPS utilizzando SSL. Per ulteriori informazioni sull'impostazione di SSL con IIS 7.0, vedere [Come implementare SSL in IIS](https://support.microsoft.com/help/299875/how-to-implement-ssl-in-iis).
  
## <a name="troubleshooting-the-wcf-web-http-programming-model"></a>Risoluzione dei problemi nel modello di programmazione HTTP WEb WCF  
 Quando si chiamano i servizi HTTP Web WCF utilizzando un oggetto <xref:System.ServiceModel.Channels.ChannelFactoryBase%601> per creare un canale, l'oggetto <xref:System.ServiceModel.Description.WebHttpBehavior> utilizza l'oggetto <xref:System.ServiceModel.EndpointAddress> impostato nel file di configurazione anche se un oggetto <xref:System.ServiceModel.EndpointAddress> viene passato all'oggetto <xref:System.ServiceModel.Channels.ChannelFactoryBase%601>.  
  
## <a name="see-also"></a>Vedere anche

- [Diffusione WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
- [Modello a oggetti per la programmazione HTTP Web di WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)
- [Modello di programmazione HTTP Web WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
