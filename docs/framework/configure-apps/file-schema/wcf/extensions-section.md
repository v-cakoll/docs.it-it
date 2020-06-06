---
title: <extensions>sezione
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 35621acaf96a80ffa3ffe4a3c6605143c48995a5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855360"
---
# <a name="extensions-section"></a><span data-ttu-id="a3edc-102">\<extensions>sezione</span><span class="sxs-lookup"><span data-stu-id="a3edc-102">\<extensions> section</span></span>
<span data-ttu-id="a3edc-103">Questa sezione di configurazione contiene una raccolta di estensioni che consentono all'utente di creare associazioni definite dall'utente, comportamenti e altri aspetti delle estensioni.</span><span class="sxs-lookup"><span data-stu-id="a3edc-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**  
  
## <a name="syntax"></a><span data-ttu-id="a3edc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3edc-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3edc-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a3edc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a3edc-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a3edc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3edc-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="a3edc-107">Attributes</span></span>  
 <span data-ttu-id="a3edc-108">No.</span><span class="sxs-lookup"><span data-stu-id="a3edc-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a3edc-109">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a3edc-109">Child Elements</span></span>  
  
|<span data-ttu-id="a3edc-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3edc-110">Element</span></span>|<span data-ttu-id="a3edc-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3edc-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviorExtensions>](behaviorextensions.md)|<span data-ttu-id="a3edc-112">Contenuto della sezione sono inclusi gli elementi figlio che specificano le estensioni del comportamento che consentono di personalizzare i comportamenti del servizio o dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="a3edc-112">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[\<bindingElementExtensions>](bindingelementextensions.md)|<span data-ttu-id="a3edc-113">Questa sezione consente l'uso di un elemento di associazione personalizzata dal file di configurazione di un computer o di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a3edc-113">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[\<bindingExtensions>](bindingextensions.md)|<span data-ttu-id="a3edc-114">Questa sezione contiene elementi figlio che specificano estensioni di associazione, le quali consentono all'utente di personalizzare le associazioni.</span><span class="sxs-lookup"><span data-stu-id="a3edc-114">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[\<endpointExtensions>](endpointextensions.md)|<span data-ttu-id="a3edc-115">Contenuto della sezione sono inclusi gli elementi figlio che registrano endpoint standard.</span><span class="sxs-lookup"><span data-stu-id="a3edc-115">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a3edc-116">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a3edc-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a3edc-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3edc-117">Element</span></span>|<span data-ttu-id="a3edc-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3edc-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3edc-119">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a3edc-119">system.ServiceModel</span></span>|<span data-ttu-id="a3edc-120">Elemento radice di tutti gli elementi di configurazione WCF.</span><span class="sxs-lookup"><span data-stu-id="a3edc-120">The root element of all WCF configuration elements.</span></span>|
