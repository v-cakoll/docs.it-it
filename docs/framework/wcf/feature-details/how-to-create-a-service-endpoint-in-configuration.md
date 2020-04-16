---
title: 'Procedura: creare un endpoint di servizio nella configurazione'
ms.date: 06/16/2016
ms.assetid: f474e25d-2a27-4f31-84c5-395c442b8e70
ms.openlocfilehash: 5935f798004de3ec049b9c9f0300675e1660f462
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464135"
---
# <a name="how-to-create-a-service-endpoint-in-configuration"></a><span data-ttu-id="60883-102">Procedura: creare un endpoint di servizio nella configurazione</span><span class="sxs-lookup"><span data-stu-id="60883-102">How to: Create a Service Endpoint in Configuration</span></span>
<span data-ttu-id="60883-103">Gli endpoint forniscono ai client l'accesso alle funzionalità offerte da un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="60883-103">Endpoints provide clients with access to the functionality a Windows Communication Foundation (WCF) service offers.</span></span> <span data-ttu-id="60883-104">È possibile definire uno o più endpoint per un servizio usando una combinazione di indirizzi di endpoint assoluti e relativi. In alternativa, se non si definisce alcun endpoint per il servizio, il runtime ne fornirà automaticamente alcuni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="60883-104">You can define one or more endpoints for a service by using a combination of relative and absolute endpoint addresses, or if you do not define any service endpoints, the runtime provides some by default for you.</span></span> <span data-ttu-id="60883-105">In questo argomento viene illustrato come aggiungere endpoint usando un file di configurazione che contiene indirizzi sia relativi che assoluti.</span><span class="sxs-lookup"><span data-stu-id="60883-105">This topic shows how to add endpoints using a configuration file that contain both relative and absolute addresses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60883-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="60883-106">Example</span></span>  
 <span data-ttu-id="60883-107">Nella configurazione del servizio seguente vengono specificati un indirizzo di base e cinque endpoint.</span><span class="sxs-lookup"><span data-stu-id="60883-107">The following service configuration specifies a base address and five endpoints.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="60883-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="60883-108">Example</span></span>  
 <span data-ttu-id="60883-109">L'indirizzo di base viene specificato usando l'elemento `add`, in service/host/baseAddresses, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="60883-109">The base address is specified using the `add` element, under service/host/baseAddresses, as shown in the following sample.</span></span>  
  
```xml  
<service
    name="Microsoft.ServiceModel.Samples.CalculatorService">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
```  
  
## <a name="example"></a><span data-ttu-id="60883-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="60883-110">Example</span></span>  
 <span data-ttu-id="60883-111">La prima definizione dell'endpoint descritta nella configurazione di esempio seguente specifica un indirizzo relativo, che indica che l'indirizzo endpoint è una combinazione dell'indirizzo di base e dell'indirizzo relativo, in base alle regole di composizione URI (Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="60883-111">The first endpoint definition shown in the following sample specifies a relative address, which means the endpoint address is a combination of the base address and the relative address following the rules of Uniform Resource Identifier (URI) composition.</span></span> <span data-ttu-id="60883-112">L'indirizzo relativo è vuoto (""), pertanto l'indirizzo endpoint corrisponde all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="60883-112">The relative address is empty (""), so the endpoint address is the same as the base address.</span></span> <span data-ttu-id="60883-113">L'indirizzo endpoint `http://localhost:8000/servicemodelsamples/service`effettivo è .</span><span class="sxs-lookup"><span data-stu-id="60883-113">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service`.</span></span>  
  
```xml  
<endpoint address=""
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="60883-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="60883-114">Example</span></span>  
 <span data-ttu-id="60883-115">Anche la seconda definizione dell'endpoint specifica un indirizzo relativo, come illustrato nell'esempio di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="60883-115">The second endpoint definition also specifies a relative address, as shown in the following sample configuration.</span></span> <span data-ttu-id="60883-116">L'indirizzo relativo, "test", viene accodato all'indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="60883-116">The relative address, "test", is appended to the base address.</span></span> <span data-ttu-id="60883-117">L'indirizzo endpoint `http://localhost:8000/servicemodelsamples/service/test`effettivo è .</span><span class="sxs-lookup"><span data-stu-id="60883-117">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service/test`.</span></span>  
  
```xml  
<endpoint address="/test"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="60883-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="60883-118">Example</span></span>  
 <span data-ttu-id="60883-119">La terza definizione dell'endpoint specifica un indirizzo assoluto, come illustrato nell'esempio di configurazione seguente.</span><span class="sxs-lookup"><span data-stu-id="60883-119">The third endpoint definition specifies an absolute address, as shown in the following sample configuration.</span></span> <span data-ttu-id="60883-120">L'indirizzo di base non ha alcun ruolo nell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="60883-120">The base address plays no role in the address.</span></span> <span data-ttu-id="60883-121">L'indirizzo endpoint `http://localhost:8001/hello/servicemodelsamples`effettivo è .</span><span class="sxs-lookup"><span data-stu-id="60883-121">The actual endpoint address is `http://localhost:8001/hello/servicemodelsamples`.</span></span>  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="60883-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="60883-122">Example</span></span>  
 <span data-ttu-id="60883-123">Il quarto indirizzo endpoint specifica un indirizzo assoluto e un trasporto diverso, cioè TCP.</span><span class="sxs-lookup"><span data-stu-id="60883-123">The fourth endpoint address specifies an absolute address and a different transport—TCP.</span></span> <span data-ttu-id="60883-124">L'indirizzo di base non ha alcun ruolo nell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="60883-124">The base address plays no role in the address.</span></span> <span data-ttu-id="60883-125">L'indirizzo dell'endpoint effettivo è net.tcp://localhost:9000/servicemodelsamples/service.</span><span class="sxs-lookup"><span data-stu-id="60883-125">The actual endpoint address is net.tcp://localhost:9000/servicemodelsamples/service.</span></span>  
  
```xml  
<endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
    binding="netTcpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="60883-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="60883-126">Example</span></span>  
 <span data-ttu-id="60883-127">Per usare gli endpoint predefiniti forniti dal runtime, non specificare alcun endpoint del servizio nel codice né nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="60883-127">To use the default endpoints provided by the runtime, do not specify any service endpoints in either the code or the configuration file.</span></span> <span data-ttu-id="60883-128">In questo esempio, il runtime crea gli endpoint predefiniti all'apertura del servizio.</span><span class="sxs-lookup"><span data-stu-id="60883-128">In this example, the runtime creates the default endpoints when the service is opened.</span></span> <span data-ttu-id="60883-129">Per altre informazioni su endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) (Configurazione semplificata) e [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md) (Configurazione semplificata per servizi WCF).</span><span class="sxs-lookup"><span data-stu-id="60883-129">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
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
