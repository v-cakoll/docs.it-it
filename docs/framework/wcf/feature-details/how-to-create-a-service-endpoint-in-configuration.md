---
title: 'Procedura: creare un endpoint di servizio nella configurazione'
description: Informazioni su come aggiungere endpoint per un servizio WCF utilizzando un file di configurazione che contiene indirizzi sia relativi che assoluti.
ms.date: 06/16/2016
ms.assetid: f474e25d-2a27-4f31-84c5-395c442b8e70
ms.openlocfilehash: 184bcb5f7f3e83f12608757b55bbb4d57be58f7d
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247065"
---
# <a name="how-to-create-a-service-endpoint-in-configuration"></a><span data-ttu-id="b9eeb-103">Procedura: creare un endpoint di servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="b9eeb-103">How to: Create a Service Endpoint in Configuration</span></span>
<span data-ttu-id="b9eeb-104">Gli endpoint forniscono ai client l'accesso alla funzionalità offerta da un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="b9eeb-104">Endpoints provide clients with access to the functionality a Windows Communication Foundation (WCF) service offers.</span></span> <span data-ttu-id="b9eeb-105">È possibile definire uno o più endpoint per un servizio usando una combinazione di indirizzi di endpoint assoluti e relativi. In alternativa, se non si definisce alcun endpoint per il servizio, il runtime ne fornirà automaticamente alcuni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-105">You can define one or more endpoints for a service by using a combination of relative and absolute endpoint addresses, or if you do not define any service endpoints, the runtime provides some by default for you.</span></span> <span data-ttu-id="b9eeb-106">In questo argomento viene illustrato come aggiungere endpoint usando un file di configurazione che contiene indirizzi sia relativi che assoluti.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-106">This topic shows how to add endpoints using a configuration file that contain both relative and absolute addresses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9eeb-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9eeb-107">Example</span></span>  
 <span data-ttu-id="b9eeb-108">Nella configurazione del servizio seguente vengono specificati un indirizzo di base e cinque endpoint.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-108">The following service configuration specifies a base address and five endpoints.</span></span>  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <services>  
    <!-- This section is optional with the default configuration introduced in .NET Framework 4. -->  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="/test"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="http://localhost:8001/hello/servicemodelsamples"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
                  binding="netTcpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is another relative address exposed at   
             http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="b9eeb-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9eeb-109">Example</span></span>  
 <span data-ttu-id="b9eeb-110">L'indirizzo di base viene specificato usando l'elemento `add`, in service/host/baseAddresses, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-110">The base address is specified using the `add` element, under service/host/baseAddresses, as shown in the following sample.</span></span>  
  
```xml  
<service
    name="Microsoft.ServiceModel.Samples.CalculatorService">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
```  
  
## <a name="example"></a><span data-ttu-id="b9eeb-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9eeb-111">Example</span></span>  
 <span data-ttu-id="b9eeb-112">La prima definizione dell'endpoint descritta nella configurazione di esempio seguente specifica un indirizzo relativo, che indica che l'indirizzo endpoint è una combinazione dell'indirizzo di base e dell'indirizzo relativo, in base alle regole di composizione URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="b9eeb-112">The first endpoint definition shown in the following sample specifies a relative address, which means the endpoint address is a combination of the base address and the relative address following the rules of Uniform Resource Identifier (URI) composition.</span></span> <span data-ttu-id="b9eeb-113">L'indirizzo relativo è vuoto (""), pertanto l'indirizzo endpoint corrisponde all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-113">The relative address is empty (""), so the endpoint address is the same as the base address.</span></span> <span data-ttu-id="b9eeb-114">L'indirizzo endpoint effettivo è `http://localhost:8000/servicemodelsamples/service` .</span><span class="sxs-lookup"><span data-stu-id="b9eeb-114">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service`.</span></span>  
  
```xml  
<endpoint address=""
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="b9eeb-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9eeb-115">Example</span></span>  
 <span data-ttu-id="b9eeb-116">Anche la seconda definizione dell'endpoint specifica un indirizzo relativo, come illustrato nell'esempio di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-116">The second endpoint definition also specifies a relative address, as shown in the following sample configuration.</span></span> <span data-ttu-id="b9eeb-117">L'indirizzo relativo, "test", viene accodato all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-117">The relative address, "test", is appended to the base address.</span></span> <span data-ttu-id="b9eeb-118">L'indirizzo endpoint effettivo è `http://localhost:8000/servicemodelsamples/service/test` .</span><span class="sxs-lookup"><span data-stu-id="b9eeb-118">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service/test`.</span></span>  
  
```xml  
<endpoint address="/test"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="b9eeb-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9eeb-119">Example</span></span>  
 <span data-ttu-id="b9eeb-120">La terza definizione dell'endpoint specifica un indirizzo assoluto, come illustrato nell'esempio di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-120">The third endpoint definition specifies an absolute address, as shown in the following sample configuration.</span></span> <span data-ttu-id="b9eeb-121">L'indirizzo di base non ha alcun ruolo nell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-121">The base address plays no role in the address.</span></span> <span data-ttu-id="b9eeb-122">L'indirizzo endpoint effettivo è `http://localhost:8001/hello/servicemodelsamples` .</span><span class="sxs-lookup"><span data-stu-id="b9eeb-122">The actual endpoint address is `http://localhost:8001/hello/servicemodelsamples`.</span></span>  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="b9eeb-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9eeb-123">Example</span></span>  
 <span data-ttu-id="b9eeb-124">Il quarto indirizzo endpoint specifica un indirizzo assoluto e un trasporto diverso, cioè TCP.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-124">The fourth endpoint address specifies an absolute address and a different transport—TCP.</span></span> <span data-ttu-id="b9eeb-125">L'indirizzo di base non ha alcun ruolo nell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-125">The base address plays no role in the address.</span></span> <span data-ttu-id="b9eeb-126">L'indirizzo dell'endpoint effettivo è net.tcp://localhost:9000/servicemodelsamples/service.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-126">The actual endpoint address is net.tcp://localhost:9000/servicemodelsamples/service.</span></span>  
  
```xml  
<endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
    binding="netTcpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="b9eeb-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9eeb-127">Example</span></span>  
 <span data-ttu-id="b9eeb-128">Per usare gli endpoint predefiniti forniti dal runtime, non specificare alcun endpoint del servizio nel codice né nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-128">To use the default endpoints provided by the runtime, do not specify any service endpoints in either the code or the configuration file.</span></span> <span data-ttu-id="b9eeb-129">In questo esempio, il runtime crea gli endpoint predefiniti all'apertura del servizio.</span><span class="sxs-lookup"><span data-stu-id="b9eeb-129">In this example, the runtime creates the default endpoints when the service is opened.</span></span> <span data-ttu-id="b9eeb-130">Per altre informazioni su endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](../simplified-configuration.md) (Configurazione semplificata) e [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md) (Configurazione semplificata per servizi WCF).</span><span class="sxs-lookup"><span data-stu-id="b9eeb-130">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```
