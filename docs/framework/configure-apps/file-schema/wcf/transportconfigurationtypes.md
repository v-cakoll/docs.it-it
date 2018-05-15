---
title: '&lt;transportConfigurationTypes&gt;'
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 422de17f4c1b42579eadc16c7ec1a0037903d1a9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="460d4-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="460d4-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="460d4-103">Rappresenta una raccolta di elementi di configurazione che identificano il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="460d4-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="460d4-104">Può essere usato per aggiungere protocolli WAS personalizzati.</span><span class="sxs-lookup"><span data-stu-id="460d4-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="460d4-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="460d4-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="460d4-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="460d4-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="460d4-107">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="460d4-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="460d4-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="460d4-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="460d4-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="460d4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="460d4-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="460d4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="460d4-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="460d4-111">Attributes</span></span>  
  
|<span data-ttu-id="460d4-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="460d4-112">Attribute</span></span>|<span data-ttu-id="460d4-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="460d4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="460d4-114">name</span><span class="sxs-lookup"><span data-stu-id="460d4-114">name</span></span>|<span data-ttu-id="460d4-115">Nome del trasporto.</span><span class="sxs-lookup"><span data-stu-id="460d4-115">The name of the transport</span></span>|  
|<span data-ttu-id="460d4-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="460d4-116">transportConfigurationType</span></span>|<span data-ttu-id="460d4-117">Tipo che implementa il trasporto.</span><span class="sxs-lookup"><span data-stu-id="460d4-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="460d4-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="460d4-118">Child Elements</span></span>  
  
|<span data-ttu-id="460d4-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="460d4-119">Element</span></span>|<span data-ttu-id="460d4-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="460d4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="460d4-121">\<add></span><span class="sxs-lookup"><span data-stu-id="460d4-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="460d4-122">Aggiunge un elemento di configurazione che identifica il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="460d4-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="460d4-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="460d4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="460d4-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="460d4-124">Element</span></span>|<span data-ttu-id="460d4-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="460d4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="460d4-126">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="460d4-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="460d4-127">Definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="460d4-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="460d4-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="460d4-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="460d4-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="460d4-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
