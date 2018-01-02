---
title: Sezione &lt;extensions&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04905ae0f40a1f9ca88b4a04d4e49b0ce895ca56
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltextensionsgt-section"></a><span data-ttu-id="3edc9-102">Sezione &lt;extensions&gt;</span><span class="sxs-lookup"><span data-stu-id="3edc9-102">&lt;extensions&gt; section</span></span>
<span data-ttu-id="3edc9-103">Questa sezione di configurazione contiene una raccolta di estensioni che consentono all'utente di creare associazioni definite dall'utente, comportamenti e altri aspetti delle estensioni.</span><span class="sxs-lookup"><span data-stu-id="3edc9-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="3edc9-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3edc9-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3edc9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3edc9-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <extensions>  
    <bindingExtensions>  
    </bindingExtensions>  
    <behaviorExtensions>  
    </behaviorExtensions>  
    <bindingElementExtensions>  
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3edc9-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="3edc9-106">Attributes and Elements</span></span>  
 <span data-ttu-id="3edc9-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="3edc9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3edc9-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="3edc9-108">Attributes</span></span>  
 <span data-ttu-id="3edc9-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="3edc9-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3edc9-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="3edc9-110">Child Elements</span></span>  
  
|<span data-ttu-id="3edc9-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="3edc9-111">Element</span></span>|<span data-ttu-id="3edc9-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3edc9-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3edc9-113">\<behaviorExtensions ></span><span class="sxs-lookup"><span data-stu-id="3edc9-113">\<behaviorExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md)|<span data-ttu-id="3edc9-114">Contenuto della sezione sono inclusi gli elementi figlio che specificano le estensioni del comportamento che consentono di personalizzare i comportamenti del servizio o dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="3edc9-114">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="3edc9-115">\<bindingElementExtensions ></span><span class="sxs-lookup"><span data-stu-id="3edc9-115">\<bindingElementExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md)|<span data-ttu-id="3edc9-116">Questa sezione consente l'uso di un elemento di associazione personalizzata dal file di configurazione di un computer o di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3edc9-116">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="3edc9-117">\<bindingExtensions ></span><span class="sxs-lookup"><span data-stu-id="3edc9-117">\<bindingExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingextensions.md)|<span data-ttu-id="3edc9-118">Questa sezione contiene elementi figlio che specificano estensioni di associazione, le quali consentono all'utente di personalizzare le associazioni.</span><span class="sxs-lookup"><span data-stu-id="3edc9-118">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="3edc9-119">\<endpointExtensions ></span><span class="sxs-lookup"><span data-stu-id="3edc9-119">\<endpointExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointextensions.md)|<span data-ttu-id="3edc9-120">Contenuto della sezione sono inclusi gli elementi figlio che registrano endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="3edc9-120">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3edc9-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="3edc9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3edc9-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="3edc9-122">Element</span></span>|<span data-ttu-id="3edc9-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3edc9-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3edc9-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3edc9-124">system.ServiceModel</span></span>|<span data-ttu-id="3edc9-125">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="3edc9-125">The root element of all WCF configuration elements.</span></span>|
