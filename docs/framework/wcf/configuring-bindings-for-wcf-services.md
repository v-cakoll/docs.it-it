---
title: Configurazione di associazioni per i servizi Windows Communication Foundation
description: Informazioni sulla configurazione delle associazioni in fase di distribuzione per un'applicazione WCF modificando gli elementi nel sistema. Elemento ServiceModel.
ms.date: 03/30/2017
helpviewer_keywords:
- binding configuration [WCF]
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
ms.openlocfilehash: a2bb396e65722726e54cd315e931eea933386659
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247628"
---
# <a name="configuring-bindings-for-windows-communication-foundation-services"></a>Configurazione di associazioni per i servizi Windows Communication Foundation
Durante la creazione di un'applicazione, è spesso necessario assegnare all'amministratore il compito di prendere alcune decisioni dopo la distribuzione dell'applicazione. Non è in alcun modo possibile, ad esempio, conoscere in anticipo l'indirizzo di un servizio, o URI (Uniform Resource Identifier). Anziché inserire un indirizzo nel codice, è preferibile consentire che questa operazione venga eseguita da un amministratore dopo la creazione del servizio. Questa flessibilità viene realizzata attraverso la configurazione.  
  
> [!NOTE]
> Utilizzare lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) con l' `/config` opzione per creare rapidamente file di configurazione.  
  
## <a name="major-sections"></a>Sezioni principali  
 Lo schema di configurazione Windows Communication Foundation (WCF) include le tre sezioni principali seguenti ( `serviceModel` , `bindings` e `services` ):  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <bindings>  
        </bindings>  
        <services>  
        </services>  
        <behaviors>  
        </behaviors>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="servicemodel-elements"></a>Elementi ServiceModel  
 È possibile utilizzare la sezione delimitata dall' `system.ServiceModel` elemento per configurare un tipo di servizio con uno o più endpoint, nonché le impostazioni per un servizio. Ogni endpoint può essere quindi configurato con un indirizzo, un contratto e un'associazione. Per ulteriori informazioni sugli endpoint, vedere [Cenni preliminari sulla creazione di endpoint](endpoint-creation-overview.md). Se non è specificato alcun endpoint, il runtime aggiunge gli endpoint predefiniti. Per altre informazioni su endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](simplified-configuration.md) (Configurazione semplificata) e [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md) (Configurazione semplificata per servizi WCF).  
  
 Un'associazione specifica trasporti (HTTP, TCP, pipe, Accodamento messaggi) e protocolli (sicurezza, affidabilità, flussi delle transazioni) e consiste in elementi, ognuno dei quali specifica un aspetto del modo in cui un endpoint comunica con l'esterno.  
  
 Se ad esempio si specifica l'elemento, viene [\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md) indicato di utilizzare http come trasporto per un endpoint. Ciò consente di associare l'endpoint in fase di esecuzione quando il servizio che utilizza l'endpoint è aperto.  
  
 Le associazioni sono di due tipi: predefinite e personalizzate. Le associazioni predefinite contengono combinazioni utili di elementi utilizzati in scenari comuni. Per un elenco di tipi di binding predefiniti forniti da WCF, vedere [associazioni fornite dal sistema](system-provided-bindings.md). Se nessuna raccolta di associazioni predefinite presenta la combinazione corretta delle funzionalità necessarie per un'applicazione di servizio, è possibile costruire associazioni personalizzate che soddisfino i requisiti dell'applicazione. Per ulteriori informazioni sulle associazioni personalizzate, vedere [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md) .  
  
 Nei quattro esempi seguenti vengono illustrate le configurazioni di binding più comuni utilizzate per la configurazione di un servizio WCF.  
  
#### <a name="specifying-an-endpoint-to-use-a-binding-type"></a>Specificare un tipo di associazione per un endpoint  
 Nel primo esempio viene illustrato come specificare un endpoint configurato con un indirizzo, un contratto e un'associazione.  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!-- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
```  
  
 In questo esempio l'attributo `name` indica il tipo di servizio per il quale è destinata la configurazione. Quando si crea un servizio nel codice con il contratto `HelloWorld`, viene inizializzato con tutti gli endpoint definiti nella configurazione di esempio. Se l'assembly implementa solo un contratto di servizio, l' `name` attributo può essere omesso perché il servizio utilizza l'unico tipo disponibile. L'attributo accetta una stringa che deve presentarsi nel formato `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`  
  
 L'attributo `address` specifica l'URI utilizzato dagli altri endpoint per comunicare con il servizio. L'URI può essere assoluto o relativo. Se viene fornito un indirizzo relativo, l'host deve fornire un indirizzo di base appropriato per lo schema di trasporto utilizzato nell'associazione. Se non viene configurato un indirizzo, si presuppone che l'indirizzo di base valga come indirizzo per quell'endpoint.  
  
 L'attributo `contract` specifica il contratto esposto dall'endpoint. Il tipo di implementazione del servizio deve implementare il tipo di contratto. Se un'implementazione del servizio implementa un tipo di contratto singolo, questa proprietà può essere omessa.  
  
 L'attributo `binding` seleziona un'associazione predefinita o personalizzata da utilizzare per lo specifico endpoint. Un endpoint che non seleziona in modo esplicito un'associazione utilizza l'associazione predefinita, ovvero `BasicHttpBinding`.  
  
#### <a name="modifying-a-predefined-binding"></a>Modifica di un'associazione predefinita  
 Nell'esempio seguente un'associazione predefinita viene modificata. Può quindi essere utilizzata per configurare qualsiasi endpoint nel servizio. L'associazione viene modificata impostando il valore della proprietà <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> su 1 secondo. Si noti che la proprietà restituisce un oggetto <xref:System.TimeSpan>.  
  
 L'associazione alterata si trova nella sezione delle associazioni. L'associazione alterata può a questo punto essere utilizzata durante la creazione di qualsiasi endpoint impostando l'attributo `binding` nell'elemento `endpoint`.  
  
> [!NOTE]
> Se si assegna un determinato nome all'associazione, `bindingConfiguration` specificato nell'endpoint del servizio deve corrispondere ad esso.  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
<bindings>  
    <basicHttpBinding
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## <a name="configuring-a-behavior-to-apply-to-a-service"></a>Configurare un comportamento da applicare a un servizio  
 Nell'esempio seguente viene configurato un comportamento specifico per il tipo di servizio. L' `ServiceMetadataBehavior` elemento viene utilizzato per abilitare lo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) per eseguire una query sul servizio e generare documenti Web Services Description Language (WSDL) dai metadati.  
  
> [!NOTE]
> Se si assegna un determinato nome al comportamento, `behaviorConfiguration` specificato nella sezione del servizio o dell'endpoint deve corrispondere ad esso.  
  
```xml  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />
    </behavior>  
</behaviors>  
<services>  
    <service
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">
       <endpoint
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />
    </service>  
</services>  
```  
  
 La configurazione precedente consente a un client di chiamare e di ottenere i metadati del servizio "HelloWorld".  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## <a name="specifying-a-service-with-two-endpoints-using-different-binding-values"></a>Specificare un servizio con due endpoint che utilizzano valori di associazione diversi  
 Nell'ultimo esempio sono configurati due endpoint per il tipo di servizio `HelloWorld`. Ogni endpoint usa un attributo personalizzato diverso `bindingConfiguration` dello stesso tipo di binding (ogni modifica di `basicHttpBinding` ).  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout" />
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure" />
</service>  
<bindings>  
    <basicHttpBinding
        name="shortTimeout"  
        timeout="00:00:00:01"
     />  
     <basicHttpBinding
        name="Secure">  
        <Security mode="Transport" />  
     </basicHttpBinding>
</bindings>  
```  
  
 È possibile ottenere lo stesso comportamento utilizzando la configurazione predefinita mediante l'aggiunta di una sezione `protocolMapping` e la configurazione delle associazioni, come mostrato nell'esempio seguente.  
  
```xml  
<protocolMapping>  
    <add scheme="http" binding="basicHttpBinding" bindingConfiguration="shortTimeout" />  
    <add scheme="https" binding="basicHttpBinding" bindingConfiguration="Secure" />  
</protocolMapping>  
<bindings>  
    <basicHttpBinding
        name="shortTimeout"  
        timeout="00:00:00:01"
     />  
     <basicHttpBinding
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione semplificata](simplified-configuration.md)
- [Associazioni fornite dal sistema](system-provided-bindings.md)
- [Cenni preliminari sulla creazione di endpoint](endpoint-creation-overview.md)
- [Uso di associazioni per configurare servizi e client](using-bindings-to-configure-services-and-clients.md)
