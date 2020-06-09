---
title: Attivazione basata sulla configurazione in IIS e WAS
ms.date: 03/30/2017
ms.assetid: 6a927e1f-b905-4ee5-ad0f-78265da38238
ms.openlocfilehash: 5e1672f4dd67950178c95d3e043e16072fcd0ef4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593581"
---
# <a name="configuration-based-activation-in-iis-and-was"></a><span data-ttu-id="fcc59-102">Attivazione basata sulla configurazione in IIS e WAS</span><span class="sxs-lookup"><span data-stu-id="fcc59-102">Configuration-Based Activation in IIS and WAS</span></span>

<span data-ttu-id="fcc59-103">In genere, quando si ospita un servizio Windows Communication Foundation (WCF) in Internet Information Services (IIS) o nel servizio Attivazione processo Windows (WAS), è necessario fornire un file con estensione svc.</span><span class="sxs-lookup"><span data-stu-id="fcc59-103">Normally when hosting a Windows Communication Foundation (WCF) service under Internet Information Services (IIS) or Windows Process Activation Service (WAS), you must provide a .svc file.</span></span> <span data-ttu-id="fcc59-104">Il file con estensione svc contiene il nome del servizio e una factory di host del servizio personalizzata facoltativa.</span><span class="sxs-lookup"><span data-stu-id="fcc59-104">The .svc file contains the name of the service and an optional custom service host factory.</span></span> <span data-ttu-id="fcc59-105">Quest'ulteriore file comporta un sovraccarico ai fini della gestibilità.</span><span class="sxs-lookup"><span data-stu-id="fcc59-105">This additional file adds manageability overhead.</span></span> <span data-ttu-id="fcc59-106">Con la funzionalità di attivazione basata sulla configurazione non è più necessario disporre di un file con estensione svc e quindi tale sovraccarico viene evitato.</span><span class="sxs-lookup"><span data-stu-id="fcc59-106">The configuration-based activation feature removes the requirement to have a .svc file and therefore the associated overhead.</span></span>

## <a name="configuration-based-activation"></a><span data-ttu-id="fcc59-107">Attivazione basata sulla configurazione</span><span class="sxs-lookup"><span data-stu-id="fcc59-107">Configuration-Based Activation</span></span>

<span data-ttu-id="fcc59-108">L'attivazione basata sulla configurazione acquisisce i metadati posizionati nel file con estensione svc e li sposta nel file Web.config.</span><span class="sxs-lookup"><span data-stu-id="fcc59-108">Configuration-based activation takes the metadata that used to be placed in the .svc file and places it in the Web.config file.</span></span> <span data-ttu-id="fcc59-109">All'interno dell' `serviceHostingEnvironment` elemento<> è presente un `serviceActivations` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="fcc59-109">Within the<`serviceHostingEnvironment`> element there is a <`serviceActivations`> element.</span></span> <span data-ttu-id="fcc59-110">All'interno dell' `serviceActivations` elemento <> sono presenti uno o più `add` elementi <>, uno per ogni servizio ospitato.</span><span class="sxs-lookup"><span data-stu-id="fcc59-110">Within the <`serviceActivations`> element are one or more <`add`> elements, one for each hosted service.</span></span> <span data-ttu-id="fcc59-111">L' `add` elemento <> contiene attributi che consentono di impostare l'indirizzo relativo per il servizio e il tipo di servizio o una factory di host del servizio.</span><span class="sxs-lookup"><span data-stu-id="fcc59-111">The <`add`> element contains attributes that let you set the relative address for the service and the service type or a service host factory.</span></span> <span data-ttu-id="fcc59-112">Nell'esempio di codice di configurazione riportato di seguito viene illustrato come utilizzare questa sezione.</span><span class="sxs-lookup"><span data-stu-id="fcc59-112">The following configuration example code shows how this section is used.</span></span>

> [!NOTE]
> <span data-ttu-id="fcc59-113">Ogni `add` elemento <> deve specificare un servizio o un attributo Factory.</span><span class="sxs-lookup"><span data-stu-id="fcc59-113">Each <`add`> element must specify a service or a factory attribute.</span></span> <span data-ttu-id="fcc59-114">È consentita la specifica sia degli attributi del servizio che della factory.</span><span class="sxs-lookup"><span data-stu-id="fcc59-114">Specifying both service and factory attributes is allowed.</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add relativeAddress="MyServiceAddress" service="Service" factory="MyServiceHostFactory"/>
  </serviceActivations>
</serviceHostingEnvironment>
```

 <span data-ttu-id="fcc59-115">Con questa situazione nel file Web.config è possibile posizionare il codice sorgente del servizio nella directory App_Code dell'applicazione o un assembly compilato nella directory bin dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fcc59-115">With this in the Web.config file, you can place the service source code in the App_Code directory of the application or a complied assembly in the Bin directory of the application.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="fcc59-116">Quando si utilizza l'attivazione basata sulla configurazione, il codice inline presente nei file con estensione svc non è supportato.</span><span class="sxs-lookup"><span data-stu-id="fcc59-116">When using configuration-based activation, inline code in .svc files is not supported.</span></span>
> - <span data-ttu-id="fcc59-117">L' `relativeAddress` attributo deve essere impostato su un indirizzo relativo, ad esempio " \<sub-directory> /Service.svc" o "~/ \< Sub-Directory/Service. svc".</span><span class="sxs-lookup"><span data-stu-id="fcc59-117">The `relativeAddress` attribute must be set to a relative address such as "\<sub-directory>/service.svc" or "~/\<sub-directory/service.svc".</span></span>
> - <span data-ttu-id="fcc59-118">Se si registra un indirizzo relativo che non dispone di un'estensione nota associata a WCF, viene generata un'eccezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fcc59-118">A configuration exception is thrown if you register a relative address that does not have a known extension associated with WCF.</span></span>
> - <span data-ttu-id="fcc59-119">L'indirizzo specificato è relativo alla radice dell'applicazione virtuale.</span><span class="sxs-lookup"><span data-stu-id="fcc59-119">The relative address specified is relative to the root of the virtual application.</span></span>
> - <span data-ttu-id="fcc59-120">A causa del modello gerarchico della configurazione, gli indirizzi relativi registrati a livello del computer e del sito vengono ereditati dalle applicazioni virtuali.</span><span class="sxs-lookup"><span data-stu-id="fcc59-120">Due to the hierarchical model of configuration, the registered relative addresses at machine and site level are inherited by virtual applications.</span></span>
> - <span data-ttu-id="fcc59-121">Le registrazioni in un file di configurazione hanno priorità rispetto alle impostazioni in un file con estensione svc, xamlx, xoml o di un altro tipo.</span><span class="sxs-lookup"><span data-stu-id="fcc59-121">Registrations in a configuration file take precedence over settings in a .svc, .xamlx, .xoml, or other file.</span></span>
> - <span data-ttu-id="fcc59-122">Qualsiasi simbolo '\' (barra rovesciata) in un URI inviato a IIS/WAS viene convertito in modo automatico in un simbolo '/' (barra).</span><span class="sxs-lookup"><span data-stu-id="fcc59-122">Any ‘\’ (backslashes) in a URI sent to IIS/WAS are automatically converted to a ‘/’ (forward slash).</span></span> <span data-ttu-id="fcc59-123">Se viene aggiunto un indirizzo relativo che contiene un simbolo '\' e viene inviato a IIS un URI che utilizza l'indirizzo relativo, la barra rovesciata viene convertita in una barra normale e IIS non è in grado di associarla all'indirizzo relativo.</span><span class="sxs-lookup"><span data-stu-id="fcc59-123">If a relative address is added that contains a ‘\’ and you send IIS a URI that uses the relative address, the backslash is converted to a forward slash and IIS cannot match it to the relative address.</span></span> <span data-ttu-id="fcc59-124">IIS invia informazioni di traccia a indicare che non è stata rilevata alcuna corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="fcc59-124">IIS sends out trace information that indicates that there are no matches found.</span></span>

## <a name="see-also"></a><span data-ttu-id="fcc59-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcc59-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection.ServiceActivations%2A>
- [<span data-ttu-id="fcc59-126">Servizi di hosting</span><span class="sxs-lookup"><span data-stu-id="fcc59-126">Hosting Services</span></span>](../hosting-services.md)
- [<span data-ttu-id="fcc59-127">Panoramica dell'hosting dei servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fcc59-127">Hosting Workflow Services Overview</span></span>](hosting-workflow-services-overview.md)
- [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md)
- <span data-ttu-id="fcc59-128">[Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="fcc59-128">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
