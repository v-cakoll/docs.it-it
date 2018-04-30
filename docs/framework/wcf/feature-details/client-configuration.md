---
title: Configurazione del client
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c2c0d17c7274cc9fdaf1b5080950ddb4f69f539a
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="client-configuration"></a><span data-ttu-id="5dd3b-102">Configurazione del client</span><span class="sxs-lookup"><span data-stu-id="5dd3b-102">Client Configuration</span></span>
<span data-ttu-id="5dd3b-103">La configurazione client di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] può essere utilizzata per specificare l'indirizzo, l'associazione, il comportamento e il contratto, ovvero le proprietà di base dell'endpoint client utilizzate dai client per connettersi agli endpoint di servizio.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-103">You can use the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="5dd3b-104">Il [ \<client >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) elemento ha un [ \<endpoint >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) i cui attributi consentono di configurare l'endpoint di base sull'elemento.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-104">The [\<client>](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="5dd3b-105">Questi attributi sono descritti nella sezione "Configurazione degli endpoint" di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-105">These attributes are discussed in the "Configuring Endpoints" section of this topic.</span></span>  
  
 <span data-ttu-id="5dd3b-106">Il [ \<endpoint >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento contiene inoltre un [ \<metadati >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) elemento utilizzato per specificare le impostazioni per l'importazione e l'esportazione dei metadati, un [ \<intestazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) elemento che contiene una raccolta di intestazioni di indirizzo personalizzate e un [ \<identità >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elemento che consente l'autenticazione di un endpoint da altri endpoint lo scambio di messaggi con esso.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-106">The [\<endpoint>](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element also contains a [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata , a [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="5dd3b-107">Il [ \<intestazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) e [ \<identità >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elementi fanno parte di <xref:System.ServiceModel.EndpointAddress> e sono descritti nella [indirizzi](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-107">The [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span> <span data-ttu-id="5dd3b-108">I collegamenti agli argomenti che spiegano l'utilizzo delle estensioni di metadati sono riportati nella sottosezione "Configurazione di metadati" di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-108">Links to topics that explain the use of metadata extensions are provided in the Configuring Metadata sub-section of this topic.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="5dd3b-109">Configurazione degli endpoint</span><span class="sxs-lookup"><span data-stu-id="5dd3b-109">Configuring Endpoints</span></span>  
 <span data-ttu-id="5dd3b-110">La configurazione del client è progettata per consentire al client di specificare uno o più endpoint, ognuno con il proprio nome, indirizzo e contratto, con ogni tipo di riferimento di [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) e [ \< i comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elementi nella configurazione del client da utilizzare per configurare tale endpoint.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-110">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="5dd3b-111">Il file di configurazione client deve essere denominato con il nome previsto dal runtime di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], ovvero "App.config".</span><span class="sxs-lookup"><span data-stu-id="5dd3b-111">The client configuration file should be named "App.config" because this is the name that the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime expects.</span></span> <span data-ttu-id="5dd3b-112">Nell'esempio seguente viene illustrato un file di configurazione client.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-112">The following example shows a client configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
// Add another endpoint by adding another <endpoint> element.  
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"   
                 bypassProxyOnLocal="false"   
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"   
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
        //Configure this binding here.  
        </binding>  
          </wsHttpBinding>  
        </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="5dd3b-113">L'attributo `name` facoltativo identifica in modo univoco un endpoint per un dato contratto.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-113">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="5dd3b-114">In particolare, tale attributo viene utilizzato dal costruttore <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> o dal costruttore <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> per specificare l'endpoint della configurazione client da configurare e da caricare quando viene creato un canale per il servizio.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-114">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="5dd3b-115">È possibile scegliere come nome di configurazione di endpoint il carattere jolly "\*". In questo caso, il metodo <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> carica qualsiasi configurazione di endpoint contenuta nel file, purché ne sia presente soltanto una. Se sono presenti più configurazioni di endpoint, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-115">A wildcard endpoint configuration name "\*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="5dd3b-116">Se questo attributo viene omesso, l'endpoint corrispondente viene utilizzato come endpoint predefinito associato al tipo di contratto specificato.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-116">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="5dd3b-117">Il valore predefinito dell'attributo `name` è una stringa vuota a cui si fa riferimento con le stesse modalità utilizzate per qualsiasi altro nome.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-117">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="5dd3b-118">Affinché possa essere individuato e identificato, ogni endpoint deve presentare un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-118">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="5dd3b-119">L'attributo `address` può essere utilizzato per specificare l'URL che indica la posizione dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-119">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="5dd3b-120">Tuttavia, l'indirizzo di un endpoint di servizio può anche essere specificato in codice creando un Uniform Resource Identifier (URI) e aggiungendo tale identificatore all'elemento <xref:System.ServiceModel.ServiceHost> tramite uno dei metodi <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-120">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> <span data-ttu-id="5dd3b-121">Per altre informazioni, vedere [indirizzi](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span><span class="sxs-lookup"><span data-stu-id="5dd3b-121">For more information, see [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span></span> <span data-ttu-id="5dd3b-122">Come indicato di introduzione, il [ \<intestazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) e [ \<identità >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elementi fanno parte di <xref:System.ServiceModel.EndpointAddress> e vengono illustrati anche nel [ Gli indirizzi](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-122">As the introduction indicates, the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="5dd3b-123">L'attributo `binding` indica il tipo di associazione che l'endpoint prevede di utilizzare per la connessione a un servizio.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-123">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="5dd3b-124">Se si prevede di fare riferimento al tipo occorre registrare per quest'ultimo una sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-124">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="5dd3b-125">Nell'esempio precedente, si tratta di [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) , che indica che l'endpoint utilizza un <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-125">In the previous example, this is the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="5dd3b-126">È tuttavia possibile che l'endpoint utilizzi più di un'associazione di un determinato tipo.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-126">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="5dd3b-127">Ognuna di queste ha il proprio [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento all'interno dell'elemento di tipo (binding).</span><span class="sxs-lookup"><span data-stu-id="5dd3b-127">Each of these has its own [\<binding>](../../../../docs/framework/misc/binding.md) element within the (binding) type element.</span></span> <span data-ttu-id="5dd3b-128">L'attributo `bindingconfiguration` viene utilizzato per distinguere le associazioni dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-128">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="5dd3b-129">Il valore viene confrontato con il `name` attributo del [ \<associazione >](../../../../docs/framework/misc/binding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-129">Its value is matched with the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) element.</span></span> <span data-ttu-id="5dd3b-130">Per ulteriori informazioni su come configurare un client di associazione utilizzando la configurazione, vedere [procedura: specificare un'associazione Client nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="5dd3b-130">For more information about how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="5dd3b-131">Il `behaviorConfiguration` attributo viene utilizzato per specificare quali [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) del [ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) l'endpoint deve utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-131">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="5dd3b-132">Il valore viene confrontato con il `name` attributo del [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-132">Its value is matched with the `name` attribute of the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="5dd3b-133">Per un esempio di utilizzo della configurazione per specificare i comportamenti client, vedere [configurazione dei comportamenti Client](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="5dd3b-133">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="5dd3b-134">L'attributo `contract` specifica il contratto esposto dall'endpoint.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-134">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="5dd3b-135">Questo valore fa riferimento alla proprietà <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> dell'attributo <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-135">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="5dd3b-136">Il valore predefinito è il nome di tipo completo della classe che implementa il servizio.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-136">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="5dd3b-137">Configurazione di metadati</span><span class="sxs-lookup"><span data-stu-id="5dd3b-137">Configuring Metadata</span></span>  
 <span data-ttu-id="5dd3b-138">Il [ \<metadati >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) elemento viene usato per specificare le impostazioni utilizzate per registrare i metadati le estensioni di importazione.</span><span class="sxs-lookup"><span data-stu-id="5dd3b-138">The [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> <span data-ttu-id="5dd3b-139">Per ulteriori informazioni sull'estensione del sistema dei metadati, vedere[estensione del sistema di metadati](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span><span class="sxs-lookup"><span data-stu-id="5dd3b-139">For more information about extending the metadata system, see[Extending the Metadata System](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd3b-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dd3b-140">See Also</span></span>  
 [<span data-ttu-id="5dd3b-141">Endpoint: indirizzi, associazioni e contratti</span><span class="sxs-lookup"><span data-stu-id="5dd3b-141">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [<span data-ttu-id="5dd3b-142">Configurazione dei comportamenti client</span><span class="sxs-lookup"><span data-stu-id="5dd3b-142">Configuring Client Behaviors</span></span>](../../../../docs/framework/wcf/configuring-client-behaviors.md)
