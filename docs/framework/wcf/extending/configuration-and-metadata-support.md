---
title: Supporto di configurazione e metadati
ms.date: 03/30/2017
ms.assetid: 27c240cb-8cab-472c-87f8-c864f4978758
ms.openlocfilehash: fb4e1cc51b827f083e580362f57df27ced770179
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345290"
---
# <a name="configuration-and-metadata-support"></a>Supporto di configurazione e metadati
In questo argomento viene illustrato come abilitare il supporto della configurazione e dei metadati per associazioni ed elementi di associazione.  
  
## <a name="overview-of-configuration-and-metadata"></a>Panoramica della configurazione e dei metadati  
 In questo argomento vengono illustrate le attività seguenti, ovvero elementi facoltativi 1, 2 e 4 nell'elenco attività Canali di [sviluppo.](developing-channels.md)  
  
- Attivazione del supporto dei file di configurazione per un elemento di associazione.  
  
- Attivazione del supporto dei file di configurazione per un'associazione.  
  
- Esportazione di asserzioni di criteri e WSDL per un elemento di associazione.  
  
- Identificazione di asserzioni di criteri e WSDL per inserire e configurare l'associazione o l'elemento di associazione.  
  
 Per informazioni sulla creazione di associazioni definite dall'utente ed elementi di associazione, vedere rispettivamente [Creating User-Defined Bindings](creating-user-defined-bindings.md) e [Creating a BindingElement](creating-a-bindingelement.md).  
  
## <a name="adding-configuration-support"></a>Aggiunta del supporto di configurazione  
 Per abilitare il supporto del file di configurazione per un canale, è necessario implementare due sezioni di configurazione, <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType> che abilita il supporto della configurazione per gli elementi di associazione e <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> e <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType> che abilita il supporto della configurazione per le associazioni.  
  
 Un modo più semplice per eseguire questa operazione consiste nell'utilizzare lo strumento di esempio [ConfigurationCodeGenerator](../samples/configurationcodegenerator.md) per generare il codice di configurazione per le associazioni e gli elementi di associazione.  
  
### <a name="extending-bindingelementextensionelement"></a>Estensione BindingElementExtensionElement  
 Il codice di esempio seguente è tratto dall'esempio [Transport: UDP.](../samples/transport-udp.md) `UdpTransportElement` è un oggetto <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> che espone `UdpTransportBindingElement` al sistema di configurazione. Con alcuni override di base, nell'esempio vengono definiti il nome della sezione di configurazione, il tipo dell'elemento di associazione e come creare l'elemento di associazione. Gli utenti possono quindi registrare la sezione di estensione in un file di configurazione come segue.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
      <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport" />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 È possibile fare riferimento all'estensione da associazioni personalizzate per utilizzare UDP come trasporto.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="adding-configuration-for-a-binding"></a>Aggiunta di configurazione per un'associazione.  
 La sezione `SampleProfileUdpBindingCollectionElement` è una classe <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> che espone `SampleProfileUdpBinding` al sistema di configurazione. La maggior parte dell'implementazione viene delegata a `SampleProfileUdpBindingConfigurationElement` che deriva da <xref:System.ServiceModel.Configuration.StandardBindingElement>. Dispone `SampleProfileUdpBindingConfigurationElement` di proprietà che corrispondono alle proprietà `SampleProfileUdpBinding`in `ConfigurationElement` , e funzioni di cui eseguire il mapping dall'associazione. Infine, viene eseguito l'override del metodo `OnApplyConfiguration` in `SampleProfileUdpBinding`, come illustrato nell'esempio di codice seguente.  
  
```csharp
protected override void OnApplyConfiguration(string configurationName)  
{  
            if (binding == null)  
                throw new ArgumentNullException("binding");  
  
            if (binding.GetType() != typeof(SampleProfileUdpBinding))  
            {  
                var expectedType = typeof(SampleProfileUdpBinding).AssemblyQualifiedName;
                var typePassedIn = binding.GetType().AssemblyQualifiedName;
                throw new ArgumentException($"Invalid type for binding. Expected type: {expectedType}. Type passed in: {typePassedIn}.");  
            }  
            SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;  
  
            udpBinding.OrderedSession = this.OrderedSession;  
            udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;  
            udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;  
            if (this.ClientBaseAddress != null)  
                   udpBinding.ClientBaseAddress = ClientBaseAddress;  
}  
```  
  
 Per registrare questo gestore nel sistema di configurazione, aggiungere la sezione seguente al file di configurazione pertinente.  
  
```xml  
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
         <sectionGroup name="bindings">  
                 <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
         </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 È quindi possibile farvi riferimento dalla sezione di configurazione [ \<del>system.serviceModel.](../../configure-apps/file-schema/wcf/system-servicemodel.md)  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="adding-metadata-support-for-a-binding-element"></a>Aggiunta del supporto dei metadati per un elemento di associazione  
 Per essere integrato in un sistema di metadati, il canale deve supportare sia l'importazione che l'esportazione di un criterio. Ciò consente a strumenti quali [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) di generare client dell'elemento di associazione.  
  
### <a name="adding-wsdl-support"></a>Aggiunta di supporto WSDL  
 L'elemento di associazione del trasporto in un'associazione è responsabile dell'esportazione e importazione delle informazioni di indirizzamento nei metadati. Quando si utilizza un'associazione SOAP, l'elemento di associazione del trasporto deve esportare anche un URI di trasporto corretto nei metadati. Il codice di esempio seguente è tratto dall'esempio [Transport: UDP.](../samples/transport-udp.md)  
  
#### <a name="wsdl-export"></a>Esportazione WSDL  
 Per esportare le `UdpTransportBindingElement` informazioni <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> di indirizzamento, implementa l'interfaccia. Il metodo <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> aggiunge le informazioni di indirizzamento corrette alla porta WSDL.  
  
```csharp  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 L'implementazione di `UdpTransportBindingElement` del metodo <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> esporta anche un URI di trasporto quando l'endpoint utilizza un'associazione SOAP:  
  
```csharp  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a>Importazione WSDL  
 Per estendere il sistema di importazione WSDL in modo da gestire l'importazione degli indirizzi, aggiungere la configurazione seguente al file di configurazione per Svcutil.exe, come illustrato nel file Svcutil.exe.config:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <wsdlImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </wsdlImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 Quando si esegue Svcutil.exe, esistono due opzioni per ottenere che Svcutil.exe carichi le estensioni di importazione WSDL:  
  
1. Puntare Svcutil.exe al file di configurazione utilizzando\<il file /SvcutilConfig:>.  
  
2. Aggiungere la sezione di configurazione a Svcutil.exe.config nella stessa directory di Svcutil.exe.  
  
 Il tipo `UdpBindingElementImporter` implementa l'interfaccia <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType>. Il metodo `ImportEndpoint` importa l'indirizzo dalla porta WSDL:  
  
```csharp  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a>Aggiunta del supporto dei criteri  
 L'elemento di associazione personalizzato è in grado di esportare asserzioni di criteri nell'associazione WSDL affinché un endpoint del servizio esprima le funzionalità di quell'elemento di associazione. Il codice di esempio seguente è tratto dall'esempio [Transport: UDP.](../samples/transport-udp.md)  
  
#### <a name="policy-export"></a>Esportazione di criteri  
 Tipo `UdpTransportBindingElement` implementa <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> per aggiungere il supporto per l'esportazione dei criteri. Di conseguenza, <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> include `UdpTransportBindingElement` nella generazione del criterio per qualsiasi associazione in cui è incluso.  
  
 In <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType>, aggiungere un'asserzione per UDP e un'altra asserzione se il canale è in modalità multicast. Ciò è dovuto al fatto che la modalità multicast influisce sul modo in cui viene costruito lo stack di comunicazione, pertanto deve essere coordinato tra entrambi i lati.  
  
```csharp  
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.MulticastAssertion,     UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 Dato che gli elementi di associazione di trasporto personalizzati sono responsabili della gestione dell'indirizzamento, l'implementazione di <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> in `UdpTransportBindingElement` deve gestire anche l'esportazione delle asserzioni di criteri di WS-Addressing appropriate per indicare la versione di WS-Addressing utilizzata.  
  
```csharp  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a>Importazione di criteri  
 Per estendere il sistema di importazione dei criteri, aggiungere la configurazione seguente al file di configurazione per Svcutil.exe, come illustrato nel file Svcutil.exe.config:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 Implementare quindi <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> dalla classe registrata (`UdpBindingElementImporter`). In <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType>, esaminare le asserzioni nello spazio dei nomi appropriato ed elaborare quelle per generare il trasporto e controllare se è multicast. Rimuovere inoltre dall'elenco delle asserzioni di associazione quelle gestite dall'importatore. Anche in questo caso, quando si esegue Svcutil.exe esistono due opzioni per l'integrazione:  
  
1. Puntare Svcutil.exe al file di configurazione utilizzando\<il file /SvcutilConfig:>.  
  
2. Aggiungere la sezione di configurazione a Svcutil.exe.config nella stessa directory di Svcutil.exe.  
  
### <a name="adding-a-custom-standard-binding-importer"></a>Aggiunta di un importatore di associazione standard personalizzato  
 Per impostazione predefinita, Svcutil.exe e il tipo <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> riconoscono e importano associazioni fornite dal sistema. In caso contrario, l'associazione viene importata come istanza <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>. Per consentire a Svcutil.exe e a <xref:System.ServiceModel.Description.WsdlImporter> di importare `SampleProfileUdpBinding`, `UdpBindingElementImporter` funge anche da importatore di associazione standard personalizzato.  
  
 Un'utilità di importazione `ImportEndpoint` dell'associazione standard personalizzata implementa il metodo sull'interfaccia <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> per esaminare l'istanza <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> importata dai metadati per verificare se potrebbe essere stata generata da un'associazione standard specifica.  
  
```csharp  
if (context.Endpoint.Binding is CustomBinding)  
{  
    Binding binding;  
    if (transportBindingElement is UdpTransportBindingElement)  
    {  
        //if TryCreate is true, the CustomBinding will be replace by a SampleProfileUdpBinding in the  
        //generated config file for better typed generation.  
        if (SampleProfileUdpBinding.TryCreate(bindingElements, out binding))  
        {  
            binding.Name = context.Endpoint.Binding.Name;  
            binding.Namespace = context.Endpoint.Binding.Namespace;  
            context.Endpoint.Binding = binding;  
        }  
    }  
}  
```  
  
 In genere, l'implementazione di un importatore dell'associazione standard personalizzato implica il controllo delle proprietà degli elementi di associazione importati per verificare che siano cambiate solo le proprietà che avrebbero potuto essere impostate dall'associazione standard e che tutte le altre siano rimaste sulle impostazioni predefinite. Una strategia di base per l'implementazione di un importatore dell'associazione standard consiste nel creare un'istanza dell'associazione standard, propagare le proprietà dagli elementi di associazione all'istanza dell'associazione standard supportata dall'associazione standard e nel confrontare gli elementi di associazione dall'associazione standard con gli elementi di associazione importati.
