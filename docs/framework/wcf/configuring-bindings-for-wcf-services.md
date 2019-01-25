---
title: Configurazione di associazioni per i servizi Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- binding configuration [WCF]
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
ms.openlocfilehash: 52f93acacec434ce6f7ba93678615c104aa94b24
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704043"
---
# <a name="configuring-bindings-for-windows-communication-foundation-services"></a>Configurazione di associazioni per i servizi Windows Communication Foundation
Durante la creazione di un'applicazione, è spesso necessario assegnare all'amministratore il compito di prendere alcune decisioni dopo la distribuzione dell'applicazione. Non è in alcun modo possibile, ad esempio, conoscere in anticipo l'indirizzo di un servizio, o URI (Uniform Resource Identifier). Anziché inserire un indirizzo nel codice, è preferibile consentire che questa operazione venga eseguita da un amministratore dopo la creazione del servizio. Questa flessibilità viene realizzata attraverso la configurazione.  
  
> [!NOTE]
>  Usare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con il `/config` switch per creare rapidamente file di configurazione.  
  
## <a name="major-sections"></a>Sezioni principali  
 Lo schema di configurazione Windows Communication Foundation (WCF) include le tre sezioni principali (`serviceModel`, `bindings`, e `services`):  
  
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
 È possibile usare la sezione delimitata dalla `system.ServiceModel` elemento per configurare un tipo di servizio con uno o più endpoint, nonché le impostazioni per un servizio. Ogni endpoint può essere quindi configurato con un indirizzo, un contratto e un'associazione. Per altre informazioni sugli endpoint, vedere [Cenni preliminari sulla creazione di Endpoint](../../../docs/framework/wcf/endpoint-creation-overview.md). Se non è specificato alcun endpoint, il runtime aggiunge gli endpoint predefiniti. Per altre informazioni su endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) (Configurazione semplificata) e [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md) (Configurazione semplificata per servizi WCF).  
  
 Un'associazione specifica trasporti (HTTP, TCP, pipe, Accodamento messaggi) e protocolli (sicurezza, affidabilità, flussi delle transazioni) e consiste in elementi, ognuno dei quali specifica un aspetto del modo in cui un endpoint comunica con l'esterno.  
  
 Ad esempio, specificando il [ \<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) elemento indica che per usare HTTP come trasporto per un endpoint. Ciò consente di associare l'endpoint in fase di esecuzione quando il servizio che utilizza l'endpoint è aperto.  
  
 Le associazioni sono di due tipi: predefinite e personalizzate. Le associazioni predefinite contengono combinazioni utili di elementi utilizzati in scenari comuni. Per un elenco dei tipi di associazione predefiniti forniti da WCF, vedere [System-provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md). Se nessuna raccolta di associazioni predefinite presenta la combinazione corretta delle funzionalità necessarie per un'applicazione di servizio, è possibile costruire associazioni personalizzate che soddisfino i requisiti dell'applicazione. Per altre informazioni sulle associazioni personalizzate, vedere [ \<customBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
 I quattro esempi seguenti illustrano le configurazioni più comuni di associazione usate per la configurazione di un servizio WCF.  
  
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
  
 In questo esempio l'attributo `name` indica il tipo di servizio per il quale è destinata la configurazione. Quando si crea un servizio nel codice con il contratto `HelloWorld`, viene inizializzato con tutti gli endpoint definiti nella configurazione di esempio. Se l'assembly implementa solo un contratto di servizio, il `name` attributo può essere omesso perché il servizio utilizza l'unico tipo disponibile. L'attributo accetta una stringa che deve presentarsi nel formato `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`  
  
 L'attributo `address` specifica l'URI utilizzato dagli altri endpoint per comunicare con il servizio. L'URI può essere assoluto o relativo. Se viene fornito un indirizzo relativo, l'host deve fornire un indirizzo di base appropriato per lo schema di trasporto utilizzato nell'associazione. Se non viene configurato un indirizzo, si presuppone che l'indirizzo di base valga come indirizzo per quell'endpoint.  
  
 L'attributo `contract` specifica il contratto esposto dall'endpoint. Il tipo di implementazione del servizio deve implementare il tipo di contratto. Se un'implementazione del servizio implementa un tipo di contratto singolo, questa proprietà può essere omessa.  
  
 L'attributo `binding` seleziona un'associazione predefinita o personalizzata da utilizzare per lo specifico endpoint. Un endpoint che non seleziona in modo esplicito un'associazione utilizza l'associazione predefinita, ovvero `BasicHttpBinding`.  
  
#### <a name="modifying-a-predefined-binding"></a>Modifica di un'associazione predefinita  
 Nell'esempio seguente un'associazione predefinita viene modificata. Può quindi essere utilizzata per configurare qualsiasi endpoint nel servizio. L'associazione viene modificata impostando il valore della proprietà <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> su 1 secondo. Si noti che la proprietà restituisce un oggetto <xref:System.TimeSpan>.  
  
 L'associazione alterata si trova nella sezione delle associazioni. L'associazione alterata può a questo punto essere utilizzata durante la creazione di qualsiasi endpoint impostando l'attributo `binding` nell'elemento `endpoint`.  
  
> [!NOTE]
>  Se si assegna un determinato nome all'associazione, `bindingConfiguration` specificato nell'endpoint del servizio deve corrispondere ad esso.  
  
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
 Nell'esempio seguente viene configurato un comportamento specifico per il tipo di servizio. Il `ServiceMetadataBehavior` elemento viene usato per abilitare il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per eseguire query sul servizio e generare documenti Web Services Description Language (WSDL) dai metadati.  
  
> [!NOTE]
>  Se si assegna un determinato nome al comportamento, `behaviorConfiguration` specificato nella sezione del servizio o dell'endpoint deve corrispondere ad esso.  
  
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
 Nell'ultimo esempio sono configurati due endpoint per il tipo di servizio `HelloWorld`. Ogni endpoint utilizza un altro oggetto personalizzato `bindingConfiguration` attributi dello stesso tipo di associazione (ognuno modifica il `basicHttpBinding`).  
  
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
- [Configurazione semplificata](../../../docs/framework/wcf/simplified-configuration.md)
- [Associazioni fornite dal sistema](../../../docs/framework/wcf/system-provided-bindings.md)
- [Panoramica della creazione di endpoint](../../../docs/framework/wcf/endpoint-creation-overview.md)
- [Uso di associazioni per configurare servizi e client](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
