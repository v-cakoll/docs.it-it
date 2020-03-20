---
title: Configurazione dei servizi tramite file di configurazione
ms.date: 03/30/2017
helpviewer_keywords:
- configuring services [WCF]
ms.assetid: c9c8cd32-2c9d-4541-ad0d-16dff6bd2a00
ms.openlocfilehash: caf6e238ca286e5e712c0273e10502655fd7ff4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174797"
---
# <a name="configuring-services-using-configuration-files"></a>Configurazione dei servizi tramite file di configurazione
La configurazione di un servizio Windows Communication Foundation (WCF) con un file di configurazione offre la flessibilità di fornire dati sul comportamento dell'endpoint e del servizio nel punto di distribuzione anziché in fase di progettazione. In questo argomento vengono delineate le principali tecniche disponibili.  
  
 Un servizio WCF è configurabile utilizzando la tecnologia di configurazione di .NET Framework.A WCF service is configurable using the .NET Framework configuration technology. In genere, gli elementi XML vengono aggiunti al file Web.config per un sito Internet Information Services (IIS) che ospita un servizio WCF. Gli elementi consentono di modificare dettagli, quali gli indirizzi degli endpoint (gli indirizzi effettivi usati per comunicare con il servizio), per i singoli computer. Inoltre, WCF include diversi elementi forniti dal sistema che consentono di selezionare rapidamente le funzionalità di base per un servizio. A partire da .NET Framework 4.NET Framework 4, WCF viene fornito con un nuovo modello di configurazione predefinito che semplifica i requisiti di configurazione WCF. Se non si fornisce alcuna configurazione WCF per un determinato servizio, il runtime configura automaticamente il servizio con alcuni endpoint standard e l'associazione/comportamento predefinito. In pratica, la scrittura della configurazione è una parte importante della programmazione di applicazioni WCF.  
  
 Per ulteriori informazioni, vedere [Configurazione delle associazioni per i servizi](configuring-bindings-for-wcf-services.md). Per un elenco degli elementi [utilizzati](system-provided-bindings.md)più di più comune, vedere Associazioni fornite dal sistema . Per altre informazioni su endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](simplified-configuration.md) (Configurazione semplificata) e [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md) (Configurazione semplificata per servizi WCF).  
  
> [!IMPORTANT]
> Nel caso di distribuzione di scenari affiancati in cui vengono implementate due versioni diverse di un servizio, è necessario specificare nomi parziali di assembly a cui viene fatto riferimento nei file di configurazione. Questa operazione è necessaria perché il file di configurazione è condiviso tra tutte le versioni di un servizio che potrebbero essere in esecuzione in versioni diverse di .NET Framework.  
  
## <a name="systemconfiguration-webconfig-and-appconfig"></a>System.Configuration: Web.config e App.config  
 WCF utilizza il sistema di configurazione System.Configuration di .NET Framework.  
  
 Quando si configura un servizio in Visual Studio, utilizzare un file Web.config o un file App.config per specificare le impostazioni. La scelta del nome del file di configurazione è determinata dall'ambiente host scelto per il servizio. Se si sta usando IIS per ospitare il servizio, usare un file Web.config. Se si sta usando un altro ambiente host, usare un file App.config.  
  
 In Visual Studio il file denominato App.config viene usato per creare il file di configurazione finale. Il nome finale effettivamente usato per la configurazione dipende dal nome dell'assembly. Ad esempio, un assembly denominato "Cohowinery.exe" ha un file di configurazione finale denominato "Cohowinery.exe.config". Tuttavia, è sufficiente modificare il file App.config. Le modifiche apportate al file vengono automaticamente apportate al file di configurazione finale dell'applicazione in fase di compilazione.  
  
 Quando si usa un file App.config, il sistema di configurazione unisce il file App.config al contenuto del file Machine.config, al momento dell'avvio dell'applicazione e dell'applicazione della configurazione. Questo meccanismo consente di definire impostazioni a livello di computer nel file Machine.config. Il file App.config può essere usato per eseguire l'override del file Machine.config; è inoltre possibile bloccare le impostazioni nel file Machine.config in modo che vengano usate. Nel caso di Web.config, il sistema di configurazione esegue il merge dei file Web.config in tutte le directory che conducono alla directory dell'applicazione nella configurazione che viene applicata. Per altre informazioni sulla configurazione e sulle priorità <xref:System.Configuration> delle impostazioni, vedere gli argomenti nello spazio dei nomi.  
  
## <a name="major-sections-of-the-configuration-file"></a>Principali sezioni del file di configurazione  
 Le sezioni principali del file di configurazione includono gli elementi seguenti.  
  
```xml  
<system.ServiceModel>  
  
   <services>  
   <!-- Define the service endpoints. This section is optional in the new  
    default configuration model in .NET Framework 4. -->  
      <service>  
         <endpoint/>  
      </service>  
   </services>  
  
   <bindings>  
   <!-- Specify one or more of the system-provided binding elements,  
    for example, <basicHttpBinding> -->
   <!-- Alternatively, <customBinding> elements. -->  
      <binding>  
      <!-- For example, a <BasicHttpBinding> element. -->  
      </binding>  
   </bindings>  
  
   <behaviors>  
   <!-- One or more of the system-provided or custom behavior elements. -->  
      <behavior>  
      <!-- For example, a <throttling> element. -->  
      </behavior>  
   </behaviors>  
  
</system.ServiceModel>  
```  
  
> [!NOTE]
> Le sezioni di associazioni e comportamenti sono facoltative e vengono incluse solo se necessario.  
  
### <a name="the-services-element"></a>I \<servizi> Element  
 L'elemento `services` contiene le specifiche per tutti i servizi ospitati dall'applicazione. A partire dal modello di configurazione semplificato in .NET Framework 4, questa sezione è facoltativa.  
  
 [\<servizi>](../configure-apps/file-schema/wcf/services.md)  
  
### <a name="the-service-element"></a>Il \<servizio> Element  
 Ogni servizio ha gli attributi seguenti:  
  
- `name`. Specifica il tipo che fornisce un'implementazione di un contratto di servizio. Si tratta di un nome completo costituito dallo spazio dei nomi, seguito da un punto e quindi dal nome del tipo. Ad esempio `"MyNameSpace.myServiceType"`.  
  
- `behaviorConfiguration`. Specifica il nome di uno degli elementi `behavior` presenti nell'elemento `behaviors` . Il comportamento specificato regola azioni, stabilendo, ad esempio, se il servizio consente la rappresentazione. Se il valore è il nome vuoto o se non viene specificato alcun attributo `behaviorConfiguration` , viene aggiunto al servizio il set predefinito di comportamenti del servizio.  
  
- [\<>di servizio](../configure-apps/file-schema/wcf/service.md)  
  
### <a name="the-endpoint-element"></a>Elemento \<> dell'endpoint  
 Ogni endpoint richiede un indirizzo, un'associazione e un contratto, rappresentati dagli attributi seguenti:  
  
- `address`. Specifica l'URI (Uniform Resource Identifier) del servizio, che può essere un indirizzo assoluto o uno relativo all'indirizzo di base del servizio. Se impostato su una stringa vuota, indica che l'endpoint è disponibile all'indirizzo di base specificato durante la creazione di <xref:System.ServiceModel.ServiceHost> per il servizio.  
  
- `binding`. In genere, specifica un'associazione fornita dal sistema come <xref:System.ServiceModel.WSHttpBinding>, ma può specificare anche un'associazione definita dall'utente. L'associazione specificata determina il tipo di trasporto, sicurezza e codifica usato e se sono supportati o attivati flussi, sessioni affidabili o transazioni.  
  
- `bindingConfiguration`. Se i valori predefiniti di un'associazione devono essere modificati, è possibile farlo configurando l'elemento `binding` appropriato nell'elemento `bindings` . A questo attributo deve essere assegnato lo stesso valore dell'attributo `name` dell'elemento `binding` usato per modificare le impostazioni predefinite. Se non viene assegnato alcun nome o non si specifica alcun attributo `bindingConfiguration` nell'associazione, nell'endpoint viene usata l'associazione predefinita del tipo di associazione.  
  
- `contract`. Specifica l'interfaccia che definisce il contratto. Si tratta dell'interfaccia implementata nel tipo CLR (Common Language Runtime) specificato dall'attributo `name` dell'elemento `service` .  
  
- [\<>endpoint](../configure-apps/file-schema/wcf/endpoint-element.md)  
  
### <a name="the-bindings-element"></a>Elemento \<di> delle associazioniThe bindings> Element  
 L'elemento `bindings` contiene le specifiche per tutte le associazioni usabili da qualsiasi endpoint definito in qualsiasi servizio.  
  
 [\<associazioni>](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-binding-element"></a>Elemento \<della> di associazioneThe binding> Element  
 L'elemento `binding` contenuto nell'elemento `bindings` può essere una delle associazioni fornite dal sistema (vedere [System-Provided Bindings](system-provided-bindings.md)) o un'associazione personalizzata (vedere [Custom Bindings](./extending/custom-bindings.md)). L'elemento `binding` ha un attributo `name` che mette in correlazione l'associazione e l'endpoint specificato nell'attributo `bindingConfiguration` dell'elemento `endpoint` . Se non è specificato alcun nome, l'associazione corrisponde all'impostazione predefinita del tipo di associazione.  
  
Per ulteriori informazioni sulla configurazione di servizi e client, vedere [Configurazione dei servizi WCF](configuring-services.md).
  
 [\<>di associazione](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-behaviors-element"></a>Il \<> dei comportamenti  
 Si tratta di un elemento contenitore per gli elementi `behavior` che definiscono i comportamenti di un servizio.  
  
 [\<comportamenti>](../configure-apps/file-schema/wcf/behaviors.md)  
  
### <a name="the-behavior-element"></a>Il \<comportamento>elementoThe behavior> Element  
 Ogni `behavior` elemento è `name` identificato da un attributo e fornisce `throttling` un comportamento fornito dal sistema, ad esempio <> o un comportamento personalizzato. Se non viene assegnato alcun nome, l'elemento relativo al comportamento corrisponde al comportamento del servizio o dell'endpoint predefinito.  
  
 [\<>di comportamento](../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)  
  
## <a name="how-to-use-binding-and-behavior-configurations"></a>Come usare configurazioni di associazioni e comportamenti  
 WCF semplifica la condivisione delle configurazioni tra gli endpoint usando un sistema di riferimento nella configurazione. Invece di assegnare direttamente valori di configurazione a un endpoint, i valori di configurazione relativi all'associazione vengono raggruppati in elementi `bindingConfiguration` nella sezione `<binding>` . Una configurazione di associazione è un gruppo denominato di impostazioni su un'associazione. Gli endpoint possono quindi fare riferimento a `bindingConfiguration` in base al nome.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
 <system.serviceModel>  
  <bindings>  
    <basicHttpBinding>  
     <binding name="myBindingConfiguration1" closeTimeout="00:01:00" />  
     <binding name="myBindingConfiguration2" closeTimeout="00:02:00" />  
     <binding closeTimeout="00:03:00" />  <!-- Default binding for basicHttpBinding -->  
    </basicHttpBinding>  
     </bindings>  
     <services>  
      <service name="MyNamespace.myServiceType">  
       <endpoint
          address="myAddress" binding="basicHttpBinding"
          bindingConfiguration="myBindingConfiguration1"  
          contract="MyContract"  />  
       <endpoint
          address="myAddress2" binding="basicHttpBinding"
          bindingConfiguration="myBindingConfiguration2"  
          contract="MyContract" />  
       <endpoint
          address="myAddress3" binding="basicHttpBinding"
          contract="MyContract" />  
       </service>  
      </services>  
    </system.serviceModel>  
</configuration>  
```  
  
 L'attributo `name` di `bindingConfiguration` è impostato nell'elemento `<binding>` . Deve `name` essere una stringa univoca all'interno dell'ambito del tipo di associazione, in questo caso il [<basicHttpBinding\>](../configure-apps/file-schema/wcf/basichttpbinding.md), o un valore vuoto per fare riferimento all'associazione predefinita. L'endpoint si collega alla configurazione impostando l'attributo `bindingConfiguration` su questa stringa.  
  
 Un attributo `behaviorConfiguration` viene implementato nello stesso modo, come illustrato nell'esempio seguente.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myBehavior">  
           <callbackDebug includeExceptionDetailInFaults="true" />  
         </behavior>  
      </endpointBehaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
  
    </behaviors>  
    <services>  
     <service name="NewServiceType">  
       <endpoint
          address="myAddress3" behaviorConfiguration="myBehavior"  
          binding="basicHttpBinding"  
          contract="MyContract" />  
      </service>  
    </services>  
   </system.serviceModel>  
</configuration>  
```  
  
 Si noti che al servizio viene aggiunto il set predefinito di comportamenti del servizio. Questo sistema consente agli endpoint di condividere configurazioni comuni senza ridefinire le impostazioni. Se è necessario un ambito a livello di computer, creare la configurazione dell'associazione o del comportamento in Machine.config.If machine-wide scope is required, create the binding or behavior configuration in Machine.config. Le impostazioni di configurazione sono disponibili in tutti i file App.config. [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md) semplifica la creazione di configurazioni.  
  
## <a name="behavior-merge"></a>Unione di comportamenti  
 La funzionalità di unione dei comportamenti semplifica la gestione di questi ultimi quando si desidera un set di comportamenti comuni da usare in modo coerente. Tale funzionalità consente di specificare i comportamenti a livelli diversi della gerarchia di configurazione e consente altresì ai servizi di ereditare i comportamenti da più livelli della gerarchia di configurazione. Per illustrare questo funzionamento, si presupponga di disporre del layout di directory virtuale seguente in IIS:  
  
 `~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc`
  
 E `~\Web.config` il file ha i seguenti contenuti:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 Un figlio Web.config è situato in ~\Child\Web.config con il contenuto seguente:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 Il servizio presente in ~\Child\Service.svc si comporterà come se disponesse di entrambi i comportamenti di serviceDebug e serviceMetadata, mentre il servizio in ~ \Service.svc disporrà solo del comportamento di serviceDebug. In pratica vengono unite le due raccolte di comportamenti con lo stesso nome (in questo caso la stringa vuota).  
  
 È inoltre possibile cancellare \<le raccolte di comportamenti utilizzando il tag \<clear> e rimuovere singoli comportamenti dalla raccolta utilizzando il tag remove>. Le due configurazioni seguenti, ad esempio, determinano il solo comportamento di serviceMetadata per il servizio figlio:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <remove name="serviceDebug"/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <clear/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 L'unione di comportamenti può essere eseguita per raccolte di comportamenti anonimi, come illustrato in precedenza, e raccolte di comportamenti denominati.  
  
 L'unione dei comportamenti funziona nell'ambiente di hosting IIS, in cui i file Web.config vengono uniti gerarchicamente con il file Web.config radice e machine.config. Ma funziona anche nell'ambiente dell'applicazione, dove machine.config può essere unito al file App.config.  
  
 L'unione di comportamenti si applica sia comportamenti dell'endpoint che a comportamenti del servizio nella configurazione.  
  
 Se una raccolta di comportamenti figlio contiene un comportamento già presente nella raccolta di comportamenti padre, il comportamento figlio sostituisce quello del padre. Pertanto, se una `<serviceMetadata httpGetEnabled="False" />` raccolta di comportamenti `<serviceMetadata httpGetEnabled="True" />`padre e una raccolta di comportamenti figlio avevano , il comportamento figlio eseguirebbe l'override del comportamento padre nell'insieme di comportamenti e httpGetEnabled sarebbe "true".  
  
## <a name="see-also"></a>Vedere anche

- [Configurazione semplificata](simplified-configuration.md)
- [Configurazione dei servizi WCFConfiguring WCF services](configuring-services.md)
- [\<>di servizio](../configure-apps/file-schema/wcf/service.md)
- [\<>di associazione](../configure-apps/file-schema/wcf/bindings.md)
