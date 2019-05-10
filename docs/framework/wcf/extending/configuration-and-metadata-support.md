---
title: Supporto di configurazione e metadati
ms.date: 03/30/2017
ms.assetid: 27c240cb-8cab-472c-87f8-c864f4978758
ms.openlocfilehash: 74dab4528ae11b60fc930a826962b71595073a7f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587721"
---
# <a name="configuration-and-metadata-support"></a><span data-ttu-id="98759-102">Supporto di configurazione e metadati</span><span class="sxs-lookup"><span data-stu-id="98759-102">Configuration and Metadata Support</span></span>
<span data-ttu-id="98759-103">In questo argomento viene illustrato come abilitare il supporto della configurazione e dei metadati per associazioni ed elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="98759-103">This topic describes how to enable configuration and metadata support for bindings and binding elements.</span></span>  
  
## <a name="overview-of-configuration-and-metadata"></a><span data-ttu-id="98759-104">Panoramica della configurazione e dei metadati</span><span class="sxs-lookup"><span data-stu-id="98759-104">Overview of Configuration and Metadata</span></span>  
 <span data-ttu-id="98759-105">In questo argomento vengono illustrate le attività seguenti, che sono elementi facoltativi 1, 2 e 4 nella [emergenti canali](../../../../docs/framework/wcf/extending/developing-channels.md) elenco attività.</span><span class="sxs-lookup"><span data-stu-id="98759-105">This topic discusses the following tasks, which are optional items 1, 2, and 4 in the [Developing Channels](../../../../docs/framework/wcf/extending/developing-channels.md) task list.</span></span>  
  
- <span data-ttu-id="98759-106">Attivazione del supporto dei file di configurazione per un elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="98759-106">Enabling configuration file support for a binding element.</span></span>  
  
- <span data-ttu-id="98759-107">Attivazione del supporto dei file di configurazione per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="98759-107">Enabling configuration file support for a binding.</span></span>  
  
- <span data-ttu-id="98759-108">Esportazione di asserzioni di criteri e WSDL per un elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="98759-108">Exporting WSDL and policy assertions for a binding element.</span></span>  
  
- <span data-ttu-id="98759-109">Identificazione di asserzioni di criteri e WSDL per inserire e configurare l'associazione o l'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="98759-109">Identifying WSDL and policy assertions to insert and configure your binding or binding element.</span></span>  
  
 <span data-ttu-id="98759-110">Per informazioni sulla creazione di associazioni definite dall'utente ed elementi di associazione, vedere [associazioni Creating User-Defined](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md) e [creazione di un oggetto BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md), rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="98759-110">For information about creating user-defined bindings and binding elements, see [Creating User-Defined Bindings](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md) and [Creating a BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md), respectively.</span></span>  
  
## <a name="adding-configuration-support"></a><span data-ttu-id="98759-111">Aggiunta del supporto di configurazione</span><span class="sxs-lookup"><span data-stu-id="98759-111">Adding Configuration Support</span></span>  
 <span data-ttu-id="98759-112">Per abilitare il supporto del file di configurazione per un canale, è necessario implementare due sezioni di configurazione, <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType> che abilita il supporto della configurazione per gli elementi di associazione e <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> e <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType> che abilita il supporto della configurazione per le associazioni.</span><span class="sxs-lookup"><span data-stu-id="98759-112">To enable configuration file support for a channel, you must implement two configuration sections, <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType>, which enables configuration support for binding elements, and the <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> and <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType>, which enable configuration support for bindings.</span></span>  
  
 <span data-ttu-id="98759-113">Un modo più semplice per eseguire questa operazione consiste nell'usare la [ConfigurationCodeGenerator](../../../../docs/framework/wcf/samples/configurationcodegenerator.md) sullo strumento di esempio per generare il codice di configurazione per associazioni ed elementi di associazione.</span><span class="sxs-lookup"><span data-stu-id="98759-113">An easier way to do this is to use the [ConfigurationCodeGenerator](../../../../docs/framework/wcf/samples/configurationcodegenerator.md) sample tool to generate configuration code for your bindings and binding elements.</span></span>  
  
### <a name="extending-bindingelementextensionelement"></a><span data-ttu-id="98759-114">Estensione BindingElementExtensionElement</span><span class="sxs-lookup"><span data-stu-id="98759-114">Extending BindingElementExtensionElement</span></span>  
 <span data-ttu-id="98759-115">Esempio di codice seguente è tratto dalla [trasporto: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="98759-115">The following example code is taken from the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span> <span data-ttu-id="98759-116">`UdpTransportElement` è un oggetto <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> che espone `UdpTransportBindingElement` al sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="98759-116">The `UdpTransportElement` is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> that exposes `UdpTransportBindingElement` to the configuration system.</span></span> <span data-ttu-id="98759-117">Con alcuni override di base, nell'esempio vengono definiti il nome della sezione di configurazione, il tipo dell'elemento di associazione e come creare l'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="98759-117">With a few basic overrides, the sample defines the configuration section name, the type of the binding element and how to create the binding element.</span></span> <span data-ttu-id="98759-118">Gli utenti possono quindi registrare la sezione di estensione in un file di configurazione come segue.</span><span class="sxs-lookup"><span data-stu-id="98759-118">Users can then register the extension section in a configuration file as follows.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
      <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="98759-119">È possibile fare riferimento all'estensione da associazioni personalizzate per utilizzare UDP come trasporto.</span><span class="sxs-lookup"><span data-stu-id="98759-119">The extension can be referenced from custom bindings to use UDP as the transport.</span></span>  
  
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
  
### <a name="adding-configuration-for-a-binding"></a><span data-ttu-id="98759-120">Aggiunta di configurazione per un'associazione.</span><span class="sxs-lookup"><span data-stu-id="98759-120">Adding Configuration for a Binding</span></span>  
 <span data-ttu-id="98759-121">La sezione `SampleProfileUdpBindingCollectionElement` è una classe <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> che espone `SampleProfileUdpBinding` al sistema di configurazione.</span><span class="sxs-lookup"><span data-stu-id="98759-121">The section `SampleProfileUdpBindingCollectionElement` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `SampleProfileUdpBinding` to the configuration system.</span></span> <span data-ttu-id="98759-122">La maggior parte dell'implementazione viene delegata a `SampleProfileUdpBindingConfigurationElement` che deriva da <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="98759-122">The bulk of the implementation is delegated to the `SampleProfileUdpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="98759-123">Il `SampleProfileUdpBindingConfigurationElement` dispone di proprietà che corrispondono alle proprietà sul `SampleProfileUdpBinding`e funzioni per eseguire il mapping dal `ConfigurationElement` associazione.</span><span class="sxs-lookup"><span data-stu-id="98759-123">The `SampleProfileUdpBindingConfigurationElement` has properties that correspond to the properties on `SampleProfileUdpBinding`, and functions to map from the `ConfigurationElement` binding.</span></span> <span data-ttu-id="98759-124">Infine, viene eseguito l'override del metodo `OnApplyConfiguration` in `SampleProfileUdpBinding`, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="98759-124">Finally, the `OnApplyConfiguration` method is overridden in the `SampleProfileUdpBinding`, as shown in the following sample code.</span></span>  
  
```csharp 
protected override void OnApplyConfiguration(string configurationName)  
{  
            if (binding == null)  
                throw new ArgumentNullException("binding");  
  
            if (binding.GetType() != typeof(SampleProfileUdpBinding))  
            {  
                throw new ArgumentException(string.Format(CultureInfo.CurrentCulture,  
                    "Invalid type for binding. Expected type: {0}. Type passed in: {1}.",  
                    typeof(SampleProfileUdpBinding).AssemblyQualifiedName,  
                    binding.GetType().AssemblyQualifiedName));  
            }  
            SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;  
  
            udpBinding.OrderedSession = this.OrderedSession;  
            udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;  
            udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;  
            if (this.ClientBaseAddress != null)  
                   udpBinding.ClientBaseAddress = ClientBaseAddress;  
}  
```  
  
 <span data-ttu-id="98759-125">Per registrare questo gestore nel sistema di configurazione, aggiungere la sezione seguente al file di configurazione pertinente.</span><span class="sxs-lookup"><span data-stu-id="98759-125">To register this handler with the configuration system, add the following section to the relevant configuration file.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
         <sectionGroup name="bindings">  
                 <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport />  
         </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 <span data-ttu-id="98759-126">È possibile quindi farvi riferimento dal [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="98759-126">It can then be referenced from the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) configuration section.</span></span>  
  
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
  
## <a name="adding-metadata-support-for-a-binding-element"></a><span data-ttu-id="98759-127">Aggiunta del supporto dei metadati per un elemento di associazione</span><span class="sxs-lookup"><span data-stu-id="98759-127">Adding Metadata Support for a Binding Element</span></span>  
 <span data-ttu-id="98759-128">Per essere integrato in un sistema di metadati, il canale deve supportare sia l'importazione che l'esportazione di un criterio.</span><span class="sxs-lookup"><span data-stu-id="98759-128">To integrate a channel into the metadata system, it must support both the import and export of policy.</span></span> <span data-ttu-id="98759-129">In questo modo gli strumenti, ad esempio [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare client dell'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="98759-129">This allows tools such as [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate clients of the binding element.</span></span>  
  
### <a name="adding-wsdl-support"></a><span data-ttu-id="98759-130">Aggiunta di supporto WSDL</span><span class="sxs-lookup"><span data-stu-id="98759-130">Adding WSDL Support</span></span>  
 <span data-ttu-id="98759-131">L'elemento di associazione del trasporto in un'associazione è responsabile dell'esportazione e importazione delle informazioni di indirizzamento nei metadati.</span><span class="sxs-lookup"><span data-stu-id="98759-131">The transport binding element in a binding is responsible for exporting and importing addressing information in metadata.</span></span> <span data-ttu-id="98759-132">Quando si utilizza un'associazione SOAP, l'elemento di associazione del trasporto deve esportare anche un URI di trasporto corretto nei metadati.</span><span class="sxs-lookup"><span data-stu-id="98759-132">When using a SOAP binding, the transport binding element should also export a correct transport URI in metadata.</span></span> <span data-ttu-id="98759-133">Esempio di codice seguente è tratto dalla [trasporto: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="98759-133">The following example code is taken from the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
#### <a name="wsdl-export"></a><span data-ttu-id="98759-134">Esportazione WSDL</span><span class="sxs-lookup"><span data-stu-id="98759-134">WSDL Export</span></span>  
 <span data-ttu-id="98759-135">Per esportare informazioni di indirizzamento, il `UdpTransportBindingElement` implementa il <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="98759-135">To export addressing information, the `UdpTransportBindingElement` implements the <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="98759-136">Il metodo <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> aggiunge le informazioni di indirizzamento corrette alla porta WSDL.</span><span class="sxs-lookup"><span data-stu-id="98759-136">The <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> method adds the correct addressing information to the WSDL port.</span></span>  
  
```csharp  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 <span data-ttu-id="98759-137">L'implementazione di `UdpTransportBindingElement` del metodo <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> esporta anche un URI di trasporto quando l'endpoint utilizza un'associazione SOAP:</span><span class="sxs-lookup"><span data-stu-id="98759-137">The `UdpTransportBindingElement` implementation of the <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> method also exports a transport URI when the endpoint uses a SOAP binding:</span></span>  
  
```csharp  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a><span data-ttu-id="98759-138">Importazione WSDL</span><span class="sxs-lookup"><span data-stu-id="98759-138">WSDL Import</span></span>  
 <span data-ttu-id="98759-139">Per estendere il sistema di importazione WSDL in modo da gestire l'importazione degli indirizzi, aggiungere la configurazione seguente al file di configurazione per Svcutil.exe, come illustrato nel file Svcutil.exe.config:</span><span class="sxs-lookup"><span data-stu-id="98759-139">To extend the WSDL import system to handle importing the addresses, add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <wsdlImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="98759-140">Quando si esegue Svcutil.exe, esistono due opzioni per ottenere che Svcutil.exe carichi le estensioni di importazione WSDL:</span><span class="sxs-lookup"><span data-stu-id="98759-140">When running Svcutil.exe, there are two options for getting Svcutil.exe to load the WSDL import extensions:</span></span>  
  
1. <span data-ttu-id="98759-141">Punto Svcutil.exe al file di configurazione utilizzando /SvcutilConfig:\<file >.</span><span class="sxs-lookup"><span data-stu-id="98759-141">Point Svcutil.exe to the configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="98759-142">Aggiungere la sezione di configurazione a Svcutil.exe.config nella stessa directory di Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="98759-142">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
 <span data-ttu-id="98759-143">Il tipo `UdpBindingElementImporter` implementa l'interfaccia <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="98759-143">The `UdpBindingElementImporter` type implements the <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="98759-144">Il metodo `ImportEndpoint` importa l'indirizzo dalla porta WSDL:</span><span class="sxs-lookup"><span data-stu-id="98759-144">The `ImportEndpoint` method imports the address from the WSDL port:</span></span>  
  
```csharp  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a><span data-ttu-id="98759-145">Aggiunta del supporto dei criteri</span><span class="sxs-lookup"><span data-stu-id="98759-145">Adding Policy Support</span></span>  
 <span data-ttu-id="98759-146">L'elemento di associazione personalizzato è in grado di esportare asserzioni di criteri nell'associazione WSDL affinché un endpoint del servizio esprima le funzionalità di quell'elemento di associazione.</span><span class="sxs-lookup"><span data-stu-id="98759-146">The custom binding element can export policy assertions in the WSDL binding for a service endpoint to express the capabilities of that binding element.</span></span> <span data-ttu-id="98759-147">Esempio di codice seguente è tratto dalla [trasporto: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="98759-147">The following example code is taken from the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
#### <a name="policy-export"></a><span data-ttu-id="98759-148">Esportazione di criteri</span><span class="sxs-lookup"><span data-stu-id="98759-148">Policy Export</span></span>  
 <span data-ttu-id="98759-149">Il `UdpTransportBindingElement` il tipo implementa <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> per aggiungere il supporto per l'esportazione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="98759-149">The `UdpTransportBindingElement` type implements <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> to add support for exporting policy.</span></span> <span data-ttu-id="98759-150">Di conseguenza, <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> include `UdpTransportBindingElement` nella generazione del criterio per qualsiasi associazione in cui è incluso.</span><span class="sxs-lookup"><span data-stu-id="98759-150">As a result, <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> includes `UdpTransportBindingElement` in the generation of policy for any binding that includes it.</span></span>  
  
 <span data-ttu-id="98759-151">In <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType>, aggiungere un'asserzione per UDP e un'altra asserzione se il canale è in modalità multicast.</span><span class="sxs-lookup"><span data-stu-id="98759-151">In <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType>, add an assertion for UDP and another assertion if the channel is in multicast mode.</span></span> <span data-ttu-id="98759-152">Ciò è dovuto al fatto che la modalità multicast influisce sul modo in cui viene costruito lo stack di comunicazione, pertanto deve essere coordinato tra entrambi i lati.</span><span class="sxs-lookup"><span data-stu-id="98759-152">This is because multicast mode affects how the communication stack is constructed, and thus must be coordinated between both sides.</span></span>  
  
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
  
 <span data-ttu-id="98759-153">Dato che gli elementi di associazione di trasporto personalizzati sono responsabili della gestione dell'indirizzamento, l'implementazione di <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> in `UdpTransportBindingElement` deve gestire anche l'esportazione delle asserzioni di criteri di WS-Addressing appropriate per indicare la versione di WS-Addressing utilizzata.</span><span class="sxs-lookup"><span data-stu-id="98759-153">Because custom transport binding elements are responsible for handling addressing, the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> implementation on the `UdpTransportBindingElement` must also handle exporting the appropriate WS-Addressing policy assertions to indicate the version of WS-Addressing being used.</span></span>  
  
```csharp  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a><span data-ttu-id="98759-154">Importazione di criteri</span><span class="sxs-lookup"><span data-stu-id="98759-154">Policy Import</span></span>  
 <span data-ttu-id="98759-155">Per estendere il sistema di importazione dei criteri, aggiungere la configurazione seguente al file di configurazione per Svcutil.exe, come illustrato nel file Svcutil.exe.config:</span><span class="sxs-lookup"><span data-stu-id="98759-155">To extend the policy import system, add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file:</span></span>  
  
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
  
 <span data-ttu-id="98759-156">Implementare quindi <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> dalla classe registrata (`UdpBindingElementImporter`).</span><span class="sxs-lookup"><span data-stu-id="98759-156">Then we implement <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> from our registered class (`UdpBindingElementImporter`).</span></span> <span data-ttu-id="98759-157">In <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType>, esaminare le asserzioni nello spazio dei nomi appropriato ed elaborare quelle per generare il trasporto e controllare se è multicast.</span><span class="sxs-lookup"><span data-stu-id="98759-157">In <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType>, examine the assertions in the appropriate namespace and process the ones for generating the transport and checking if it is multicast.</span></span> <span data-ttu-id="98759-158">Rimuovere inoltre dall'elenco delle asserzioni di associazione quelle gestite dall'importatore.</span><span class="sxs-lookup"><span data-stu-id="98759-158">In addition, remove the assertions that the importer handles from the list of binding assertions.</span></span> <span data-ttu-id="98759-159">Anche in questo caso, quando si esegue Svcutil.exe esistono due opzioni per l'integrazione:</span><span class="sxs-lookup"><span data-stu-id="98759-159">Again, when running Svcutil.exe, there are two options for integration:</span></span>  
  
1. <span data-ttu-id="98759-160">Punto Svcutil.exe al file di configurazione utilizzando /SvcutilConfig:\<file >.</span><span class="sxs-lookup"><span data-stu-id="98759-160">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="98759-161">Aggiungere la sezione di configurazione a Svcutil.exe.config nella stessa directory di Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="98759-161">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
### <a name="adding-a-custom-standard-binding-importer"></a><span data-ttu-id="98759-162">Aggiunta di un importatore di associazione standard personalizzato</span><span class="sxs-lookup"><span data-stu-id="98759-162">Adding a Custom Standard Binding Importer</span></span>  
 <span data-ttu-id="98759-163">Per impostazione predefinita, Svcutil.exe e il tipo <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> riconoscono e importano associazioni fornite dal sistema.</span><span class="sxs-lookup"><span data-stu-id="98759-163">Svcutil.exe and the <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> type, by default, recognize and import system-provided bindings.</span></span> <span data-ttu-id="98759-164">In caso contrario, l'associazione viene importata come istanza <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="98759-164">Otherwise, the binding gets imported as a <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="98759-165">Per consentire a Svcutil.exe e a <xref:System.ServiceModel.Description.WsdlImporter> di importare `SampleProfileUdpBinding`, `UdpBindingElementImporter` funge anche da importatore di associazione standard personalizzato.</span><span class="sxs-lookup"><span data-stu-id="98759-165">To enable Svcutil.exe and the <xref:System.ServiceModel.Description.WsdlImporter> to import the `SampleProfileUdpBinding` the `UdpBindingElementImporter` also acts as a custom standard binding importer.</span></span>  
  
 <span data-ttu-id="98759-166">Un importatore di associazione standard personalizzato implementa il `ImportEndpoint` metodo sul <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interfaccia per esaminare il <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> istanza importata dai metadati per vedere se si poteva essere generato da un'associazione standard specifica.</span><span class="sxs-lookup"><span data-stu-id="98759-166">A custom standard binding importer implements the `ImportEndpoint` method on the <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interface to examine the <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> instance imported from metadata to see if it could have been generated by specific standard binding.</span></span>  
  
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
  
 <span data-ttu-id="98759-167">In genere, l'implementazione di un importatore dell'associazione standard personalizzato implica il controllo delle proprietà degli elementi di associazione importati per verificare che siano cambiate solo le proprietà che avrebbero potuto essere impostate dall'associazione standard e che tutte le altre siano rimaste sulle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="98759-167">Generally, implementing a custom standard binding importer involves checking the properties of the imported binding elements to verify that only properties that could have been set by the standard binding have changed and all other properties are their defaults.</span></span> <span data-ttu-id="98759-168">Una strategia di base per l'implementazione di un importatore dell'associazione standard consiste nel creare un'istanza dell'associazione standard, propagare le proprietà dagli elementi di associazione all'istanza dell'associazione standard supportata dall'associazione standard e nel confrontare gli elementi di associazione dall'associazione standard con gli elementi di associazione importati.</span><span class="sxs-lookup"><span data-stu-id="98759-168">A basic strategy for implementing a standard binding importer is to create an instance of the standard binding, propagate the properties from the binding elements to the standard binding instance that the standard binding supports, and the compare the binding elements from the standard binding with the imported binding elements.</span></span>
