---
title: <serviceMetadata>
ms.date: 03/30/2017
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
ms.openlocfilehash: 04bc29e8e842f5bb0252685fc3088a86535f4668
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268535"
---
# <a name="servicemetadata"></a>\<serviceMetadata>
Specifica la pubblicazione dei metadati del servizio e delle informazioni associate.  
  
\<system.serviceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceMetadata>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<serviceMetadata externalMetadataLocation="String"
                 httpGetBinding="String"
                 httpGetBindingConfiguration="String"
                 httpGetEnabled="Boolean"
                 httpGetUrl="String"
                 httpsGetBinding="String"
                 httpsGetBindingConfiguration="String"
                 httpsGetEnabled="Boolean"
                 httpsGetUrl="String"
                 policyVersion="Policy12/Policy15" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|externalMetadataLocation|URI contenente il percorso di un file WSDL. Tale file viene restituito all'utente in risposta a richieste WSDL e MEX al posto del file WSDL generato automaticamente. Se questo attributo non viene impostato, viene restituito il file WSDL predefinito. Il valore predefinito è una stringa vuota.|  
|httpGetBinding|Stringa che specifica il tipo dell'associazione che verrà usata per il recupero di metadati tramite HTTP GET. Questa impostazione è facoltativa. Se non viene specificata, verranno usate le associazioni predefinite.<br /><br /> Verranno supportate sole le associazioni con elementi di associazione interni che supportano <xref:System.ServiceModel.Channels.IReplyChannel>. La proprietà <xref:System.ServiceModel.Channels.MessageVersion> dell'associazione deve inoltre essere <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.|  
|httpGetBindingConfiguration|Stringa che imposta il nome dell'associazione specificata nell'attributo `httpGetBinding` che fa riferimento alle informazioni di configurazione aggiuntive di questa associazione. Lo stesso nome deve essere definito nella sezione `<bindings>`.|  
|httpGetEnabled|Valore booleano che specifica se pubblicare metadati di servizio per il recupero usando una richiesta HTTP GET. Il valore predefinito è `false`.<br /><br /> Se l'attributo httpGetUrl non viene specificato, l'indirizzo di pubblicazione dei metadati è l'indirizzo del servizio seguito da "?wsdl". Ad esempio, se l'indirizzo del servizio è "http://localhost:8080/CalculatorService", l'indirizzo di metadati HTTP/Get è"http://localhost:8080/CalculatorService?wsdl".<br /><br /> Se questa proprietà è `false`, o l'indirizzo del servizio non è basato su HTTP o HTTPS, "? wsdl" viene ignorato.|  
|httpGetUrl|URI che specifica l'indirizzo di pubblicazione dei metadati per il recupero usando una richiesta HTTP GET. Se è specificato un URI relativo, verrà considerato come relativo all'indirizzo di base del servizio.|  
|httpsGetBinding|Stringa che specifica il tipo dell'associazione che verrà usata per il recupero di metadati tramite HTTPS GET. Questa impostazione è facoltativa. Se non viene specificata, verranno usate le associazioni predefinite.<br /><br /> Verranno supportate sole le associazioni con elementi di associazione interni che supportano <xref:System.ServiceModel.Channels.IReplyChannel>. La proprietà <xref:System.ServiceModel.Channels.MessageVersion> dell'associazione deve inoltre essere <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.|  
|httpsGetBindingConfiguration|Stringa che imposta il nome dell'associazione specificata nell'attributo `httpsGetBinding` che fa riferimento alle informazioni di configurazione aggiuntive di questa associazione. Lo stesso nome deve essere definito nella sezione `<bindings>`.|  
|httpsGetEnabled|Valore booleano che specifica se pubblicare metadati di servizio per il recupero usando una richiesta HTTPS GET. Il valore predefinito è `false`.<br /><br /> Se l'attributo httpsGetUrl non viene specificato, l'indirizzo di pubblicazione dei metadati è l'indirizzo del servizio seguito da "?wsdl". Ad esempio, se l'indirizzo del servizio è "https://localhost:8080/CalculatorService", l'indirizzo di metadati HTTP/Get è"https://localhost:8080/CalculatorService?wsdl".<br /><br /> Se questa proprietà è `false`, o l'indirizzo del servizio non è basato su HTTP o HTTPS, "? wsdl" viene ignorato.|  
|httpsGetUrl|URI che specifica l'indirizzo di pubblicazione dei metadati per il recupero usando una richiesta HTTPS GET.|  
|policyVersion|Stringa che indica la versione della specifica WS-Policy usata. L'attributo è di tipo <xref:System.ServiceModel.Description.PolicyVersion>.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Specifica un elemento di comportamento.|  
  
## <a name="remarks"></a>Note  
 Questo elemento di configurazione consente di controllare le funzionalità di pubblicazione dei metadati di un servizio. Per evitare la diffusione accidentale di metadati del servizio potenzialmente riservati, la configurazione predefinita per i servizi Windows Communication Foundation (WCF) consente di disattivare la pubblicazione dei metadati. Questo comportamento è protetto per impostazione predefinita, ma significa inoltre che non è possibile usare uno strumento di importazione di metadati (ad esempio Svcutil.exe) per generare il codice client necessario per chiamare il servizio, a meno che il comportamento del servizio di pubblicazione dei metadati non venga abilitato in modo esplicito in fase di configurazione. Tale elemento di configurazione consente di abilitare questo comportamento di pubblicazione per il servizio.  
  
 Per un esempio dettagliato della configurazione di questo comportamento, vedere [comportamento di pubblicazione dei metadati](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).  
  
 Gli attributi `httpGetBinding` e `httpsGetBinding` facoltativi consentono di configurare le associazioni usate per il recupero di metadati tramite HTTP GET (o HTTPS GET). Se non vengono specificati, per il recupero dei metadati verranno usate le associazioni predefinite (`HttpTransportBindingElement` per HTTP e `HttpsTransportBindingElement` per HTTPS) a seconda dei casi. Si noti che non è possibile usare questi attributi con le associazioni WCF incorporate. Verranno supportate sole le associazioni con elementi di associazione interni che supportano <xref:System.ServiceModel.Channels.IReplyChannel>. La proprietà <xref:System.ServiceModel.Channels.MessageVersion> dell'associazione deve inoltre essere <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.  
  
 Per ridurre l'esposizione di un servizio agli utenti malintenzionati, questo trasferimento può essere protetto mediante il meccanismo HTTPS (ovvero SSL su HTTP). A tale scopo, è anzitutto necessario associare un certificato X.509 adatto a una porta specifica del computer che ospita il servizio. (Per altre informazioni, vedere [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Aggiungere quindi questo elemento alla configurazione del servizio e impostare l'attributo `httpsGetEnabled` su `true`. Impostare infine l'attributo `httpsGetUrl` sull'URL dell'endpoint dei metadati del servizio, come illustrato nell'esempio seguente.  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="NewBehavior">
      <serviceMetadata httpsGetEnabled="true"
                       httpsGetUrl="https://myComputerName/myEndpoint" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente configura un servizio per esporre metadati tramite il \<serviceMetadata > elemento. Viene inoltre configurato un endpoint per esporre il contratto `IMetadataExchange` come un'implementazione di un protocollo WS-MetadataExchange (MEX). Nell'esempio viene usata l'associazione `mexHttpBinding`, ovvero un'utile associazione standard equivalente all'associazione `wsHttpBinding` con la modalità di sicurezza impostata su `None`. Viene usato un indirizzo relativo "MEX" nell'endpoint, che, quando risolto rispetto ai servizi di base comporta un indirizzo dell'endpoint di indirizzo `http://localhost/servicemodelsamples/service.svc/mex`.  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc -->
        <endpoint address=""
                  binding="wsHttpBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex
             To expose the IMetadataExchange contract, you must enable the serviceMetadata behavior as demonstrated below. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <!-- The serviceMetadata behavior publishes metadata through the IMetadataExchange contract. When this behavior is
               present, you can expose this contract through an endpoint as shown above. Setting httpGetEnabled to true publishes
               the service's WSDL at the <baseaddress>?wsdl eg. http://localhost/servicemodelsamples/service.svc?wsdl -->
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [Comportamenti di sicurezza](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Comportamento di pubblicazione dei metadati](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
