---
title: <extensions>sezione
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 35621acaf96a80ffa3ffe4a3c6605143c48995a5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855360"
---
# <a name="extensions-section"></a><span data-ttu-id="dda25-102">\<sezione > estensioni</span><span class="sxs-lookup"><span data-stu-id="dda25-102">\<extensions> section</span></span>
<span data-ttu-id="dda25-103">Questa sezione di configurazione contiene una raccolta di estensioni che consentono all'utente di creare associazioni definite dall'utente, comportamenti e altri aspetti delle estensioni.</span><span class="sxs-lookup"><span data-stu-id="dda25-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="dda25-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dda25-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dda25-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dda25-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dda25-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> estensioni**</span><span class="sxs-lookup"><span data-stu-id="dda25-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dda25-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dda25-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dda25-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="dda25-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dda25-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="dda25-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dda25-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="dda25-110">Attributes</span></span>  
 <span data-ttu-id="dda25-111">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dda25-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dda25-112">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="dda25-112">Child Elements</span></span>  
  
|<span data-ttu-id="dda25-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="dda25-113">Element</span></span>|<span data-ttu-id="dda25-114">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="dda25-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dda25-115">\<behaviorExtensions></span><span class="sxs-lookup"><span data-stu-id="dda25-115">\<behaviorExtensions></span></span>](behaviorextensions.md)|<span data-ttu-id="dda25-116">Contenuto della sezione sono inclusi gli elementi figlio che specificano le estensioni del comportamento che consentono di personalizzare i comportamenti del servizio o dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="dda25-116">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="dda25-117">\<bindingElementExtensions></span><span class="sxs-lookup"><span data-stu-id="dda25-117">\<bindingElementExtensions></span></span>](bindingelementextensions.md)|<span data-ttu-id="dda25-118">Questa sezione consente l'uso di un elemento di associazione personalizzata dal file di configurazione di un computer o di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dda25-118">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="dda25-119">\<bindingExtensions></span><span class="sxs-lookup"><span data-stu-id="dda25-119">\<bindingExtensions></span></span>](bindingextensions.md)|<span data-ttu-id="dda25-120">Questa sezione contiene elementi figlio che specificano estensioni di associazione, le quali consentono all'utente di personalizzare le associazioni.</span><span class="sxs-lookup"><span data-stu-id="dda25-120">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="dda25-121">\<endpointExtensions></span><span class="sxs-lookup"><span data-stu-id="dda25-121">\<endpointExtensions></span></span>](endpointextensions.md)|<span data-ttu-id="dda25-122">Contenuto della sezione sono inclusi gli elementi figlio che registrano endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="dda25-122">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dda25-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="dda25-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dda25-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="dda25-124">Element</span></span>|<span data-ttu-id="dda25-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="dda25-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dda25-126">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dda25-126">system.ServiceModel</span></span>|<span data-ttu-id="dda25-127">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="dda25-127">The root element of all WCF configuration elements.</span></span>|
