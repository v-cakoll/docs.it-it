---
title: Sezione &lt;extensions&gt;
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 09cabfc6c03602c3b6de343a29b5b25755f2cf0f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="ltextensionsgt-section"></a><span data-ttu-id="2b89d-102">Sezione &lt;extensions&gt;</span><span class="sxs-lookup"><span data-stu-id="2b89d-102">&lt;extensions&gt; section</span></span>
<span data-ttu-id="2b89d-103">Questa sezione di configurazione contiene una raccolta di estensioni che consentono all'utente di creare associazioni definite dall'utente, comportamenti e altri aspetti delle estensioni.</span><span class="sxs-lookup"><span data-stu-id="2b89d-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="2b89d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2b89d-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b89d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b89d-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b89d-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="2b89d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2b89d-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="2b89d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b89d-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="2b89d-108">Attributes</span></span>  
 <span data-ttu-id="2b89d-109">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="2b89d-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2b89d-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="2b89d-110">Child Elements</span></span>  
  
|<span data-ttu-id="2b89d-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b89d-111">Element</span></span>|<span data-ttu-id="2b89d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b89d-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b89d-113">\<behaviorExtensions ></span><span class="sxs-lookup"><span data-stu-id="2b89d-113">\<behaviorExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md)|<span data-ttu-id="2b89d-114">Contenuto della sezione sono inclusi gli elementi figlio che specificano le estensioni del comportamento che consentono di personalizzare i comportamenti del servizio o dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2b89d-114">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="2b89d-115">\<bindingElementExtensions ></span><span class="sxs-lookup"><span data-stu-id="2b89d-115">\<bindingElementExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md)|<span data-ttu-id="2b89d-116">Questa sezione consente l'uso di un elemento di associazione personalizzata dal file di configurazione di un computer o di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2b89d-116">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="2b89d-117">\<bindingExtensions ></span><span class="sxs-lookup"><span data-stu-id="2b89d-117">\<bindingExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingextensions.md)|<span data-ttu-id="2b89d-118">Questa sezione contiene elementi figlio che specificano estensioni di associazione, le quali consentono all'utente di personalizzare le associazioni.</span><span class="sxs-lookup"><span data-stu-id="2b89d-118">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="2b89d-119">\<endpointExtensions ></span><span class="sxs-lookup"><span data-stu-id="2b89d-119">\<endpointExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointextensions.md)|<span data-ttu-id="2b89d-120">Contenuto della sezione sono inclusi gli elementi figlio che registrano endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="2b89d-120">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b89d-121">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="2b89d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2b89d-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b89d-122">Element</span></span>|<span data-ttu-id="2b89d-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b89d-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b89d-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2b89d-124">system.ServiceModel</span></span>|<span data-ttu-id="2b89d-125">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="2b89d-125">The root element of all WCF configuration elements.</span></span>|
