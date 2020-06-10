---
title: 'Procedura: configurare le impostazioni del servizio COM+'
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], configuring service settings
ms.assetid: f42a55a8-3af8-4394-9fdd-bf12a93780eb
ms.openlocfilehash: 3fb4b31038845d223248e72d32b3e7413f2aef63
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597176"
---
# <a name="how-to-configure-com-service-settings"></a><span data-ttu-id="6dd19-102">Procedura: configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="6dd19-102">How to: Configure COM+ Service Settings</span></span>
<span data-ttu-id="6dd19-103">Quando l'interfaccia di un'applicazione viene aggiunta o rimossa usando lo strumento di configurazione del servizio COM+, la configurazione del servizio Web viene aggiornata nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6dd19-103">When an application interface is added or removed by using the COM+ Service Configuration tool, the Web service configuration is updated within the application's configuration file.</span></span> <span data-ttu-id="6dd19-104">In modalità hosted COM+, il file Application. config si trova nella directory radice dell'applicazione (%programmi%\COMPlus Applications Applications \\ {AppID} è l'impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="6dd19-104">In the COM+ hosted mode, the Application.config file is placed in the Application Root Directory (%PROGRAMFILES%\ComPlus Applications\\{appid} is the default).</span></span> <span data-ttu-id="6dd19-105">In entrambe le modalità di hosting Web il file Web.config è posizionato nella directory vroot specificata.</span><span class="sxs-lookup"><span data-stu-id="6dd19-105">In either of the Web-hosted modes, the Web.config file is placed in the specified vroot directory.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6dd19-106">Per evitare la manomissione dei messaggi tra un client e un server è necessario firmare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="6dd19-106">Message signing should be used to protect against tampering of messages between a client and a server.</span></span> <span data-ttu-id="6dd19-107">Inoltre, per evitare la diffusione di informazioni dai messaggi scambiati tra un client e un server è necessario usare la crittografia a livello di messaggio o di trasporto.</span><span class="sxs-lookup"><span data-stu-id="6dd19-107">Also, message or transport layer encryption should be used to protect against information disclosure from messages between a client and a server.</span></span> <span data-ttu-id="6dd19-108">Come per i servizi Windows Communication Foundation (WCF), è consigliabile usare la limitazione delle richieste per limitare il numero di chiamate simultanee, connessioni, istanze e operazioni in sospeso.</span><span class="sxs-lookup"><span data-stu-id="6dd19-108">As with Windows Communication Foundation (WCF) services, you should use throttling to limit the number of concurrent calls, connections, instances, and pending operations.</span></span> <span data-ttu-id="6dd19-109">Ciò consente di evitare un utilizzo eccessivo di risorse.</span><span class="sxs-lookup"><span data-stu-id="6dd19-109">This helps prevent over-consumption of resources.</span></span> <span data-ttu-id="6dd19-110">Il comportamento della limitazione delle richieste viene specificato tramite impostazioni del file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="6dd19-110">Throttling behavior is specified through service configuration file settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6dd19-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="6dd19-111">Example</span></span>  
 <span data-ttu-id="6dd19-112">Si consideri un componente che implementa l'interfaccia seguente:</span><span class="sxs-lookup"><span data-stu-id="6dd19-112">Consider a component that implements the following interface:</span></span>  
  
```csharp
[Guid("C551FBA9-E3AA-4272-8C2A-84BD8D290AC7")]  
public interface IFinances  
{  
    string Debit(string accountNo, double amount);  
    string Credit(string accountNo, double amount);  
}  
```  
  
 <span data-ttu-id="6dd19-113">Se il componente viene esposto come un servizio Web, il contratto di servizio corrispondente che viene esposto, e al quale si devono conformare i client, è il seguente:</span><span class="sxs-lookup"><span data-stu-id="6dd19-113">If the component is exposed as a Web service, the corresponding service contract that is exposed, and that clients would need to conform to, is as follows:</span></span>  
  
```csharp
[ServiceContract(Session = true,  
Namespace = "http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7",  
Name = "IFinances")]  
public interface IFinancesContract : IDisposable  
{  
    [OperationContract]  
    string Debit(string accountNo, double amount);  
    [OperationContract]  
    string Credit(string accountNo, double amount);  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="6dd19-114">L'IID fa parte dello spazio dei nomi iniziale per il contratto.</span><span class="sxs-lookup"><span data-stu-id="6dd19-114">IID forms part of the initial namespace for the contract.</span></span>  
  
 <span data-ttu-id="6dd19-115">Le applicazioni client che usano questo servizio dovrebbero essere conformi a questo contratto, nonché usare un'associazione che sia compatibile con quella specificata nella configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6dd19-115">Client applications that use this service would need to conform to this contract, along with using a binding that is compatible with the one specified in the application configuration.</span></span>  
  
 <span data-ttu-id="6dd19-116">Nell'esempio di codice seguente viene illustrato un file di configurazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="6dd19-116">The following code example shows a default configuration file.</span></span> <span data-ttu-id="6dd19-117">Essendo un servizio Web Windows Communication Foundation (WCF), è conforme allo schema di configurazione del modello di servizio standard e può essere modificato in modo analogo ad altri file di configurazione dei servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="6dd19-117">Being a Windows Communication Foundation (WCF) Web service, this conforms to the standard service model configuration schema and can be edited in the same way as other WCF services configuration files.</span></span>  
  
 <span data-ttu-id="6dd19-118">Modifiche tipiche includono:</span><span class="sxs-lookup"><span data-stu-id="6dd19-118">Typical modifications would include:</span></span>  
  
- <span data-ttu-id="6dd19-119">Modifica dell'indirizzo endpoint dal modulo ApplicationName/ComponentName/InterfaceName predefinito in un modulo maggiormente utilizzabile.</span><span class="sxs-lookup"><span data-stu-id="6dd19-119">Changing the endpoint address from the default ApplicationName/ComponentName/InterfaceName form to a more usable form.</span></span>  
  
- <span data-ttu-id="6dd19-120">Modifica dello spazio dei nomi del servizio dal `http://tempuri.org/InterfaceID` modulo predefinito a un form più pertinente.</span><span class="sxs-lookup"><span data-stu-id="6dd19-120">Modifying the namespace of the service from the default `http://tempuri.org/InterfaceID` form to a more relevant form.</span></span>  
  
- <span data-ttu-id="6dd19-121">Modifica dell'endpoint per l'uso di un'associazione del trasporto differente.</span><span class="sxs-lookup"><span data-stu-id="6dd19-121">Changing the endpoint to use a different transport binding.</span></span>  
  
     <span data-ttu-id="6dd19-122">Nel caso di un servizio COM+ ospitato, per impostazione predefinita viene usato il trasporto tramite named pipe. È comunque possibile usare un trasporto esterno al computer come TCP.</span><span class="sxs-lookup"><span data-stu-id="6dd19-122">In the COM+-hosted case, the named pipes transport is used by default, but an off-machine transport like TCP can be used instead.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="comNonTransactionalBinding" />  
                <binding name="comTransactionalBinding" transactionFlow="true" />  
            </netNamedPipeBinding>  
        </bindings>  
        <comContracts>  
            <comContract contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"  
                name="IFinances" namespace="http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7"  
                requiresSession="true">  
                <exposedMethods>  
                    <add exposedMethod="Debit" />  
                    <add exposedMethod="Credit" />  
                </exposedMethods>  
            </comContract>  
        </comContracts>  
        <services>  
            <service name="{DCDB24CC-0B19-4534-95CD-FBBFF4D67DD9},{C942B840-AD54-4A44-B5F7-928130980AB9}">  
                <endpoint address="IFinances" binding="netNamedPipeBinding" bindingConfiguration="comNonTransactionalBinding"  
                    contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" />  
                <host>  
                    <baseAddresses>  
                        <add baseAddress="net.pipe://localhost/ServiceModelDocSampleApp/ServiceModelDocSample.esFinance" />  
                    </baseAddresses>  
                </host>  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6dd19-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6dd19-123">See also</span></span>

- [<span data-ttu-id="6dd19-124">Integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="6dd19-124">Integrating with COM+ Applications</span></span>](integrating-with-com-plus-applications.md)
