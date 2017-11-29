---
title: '&lt;transportConfigurationTypes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b048b160f337897765fa4fcff73a4906534ab08b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="0933a-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="0933a-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="0933a-103">Rappresenta una raccolta di elementi di configurazione che identificano il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="0933a-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="0933a-104">Può essere usato per aggiungere protocolli WAS personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0933a-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="0933a-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0933a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="0933a-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="0933a-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="0933a-107">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="0933a-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0933a-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0933a-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0933a-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="0933a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0933a-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="0933a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0933a-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="0933a-111">Attributes</span></span>  
  
|<span data-ttu-id="0933a-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="0933a-112">Attribute</span></span>|<span data-ttu-id="0933a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0933a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0933a-114">name</span><span class="sxs-lookup"><span data-stu-id="0933a-114">name</span></span>|<span data-ttu-id="0933a-115">Nome del trasporto.</span><span class="sxs-lookup"><span data-stu-id="0933a-115">The name of the transport</span></span>|  
|<span data-ttu-id="0933a-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="0933a-116">transportConfigurationType</span></span>|<span data-ttu-id="0933a-117">Tipo che implementa il trasporto.</span><span class="sxs-lookup"><span data-stu-id="0933a-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0933a-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="0933a-118">Child Elements</span></span>  
  
|<span data-ttu-id="0933a-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="0933a-119">Element</span></span>|<span data-ttu-id="0933a-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0933a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0933a-121">\<add></span><span class="sxs-lookup"><span data-stu-id="0933a-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="0933a-122">Aggiunge un elemento di configurazione che identifica il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="0933a-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0933a-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="0933a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0933a-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0933a-124">Element</span></span>|<span data-ttu-id="0933a-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0933a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0933a-126">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="0933a-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="0933a-127">Definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="0933a-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0933a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0933a-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="0933a-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="0933a-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
