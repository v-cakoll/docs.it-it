---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: bfd2147a8e772848fc98cab7a875a51bdb53b5cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941165"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="ee3e5-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="ee3e5-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="ee3e5-102">Rappresenta una raccolta di elementi di configurazione che identificano il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="ee3e5-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="ee3e5-103">Può essere usato per aggiungere protocolli WAS personalizzati.</span><span class="sxs-lookup"><span data-stu-id="ee3e5-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="ee3e5-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ee3e5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ee3e5-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="ee3e5-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="ee3e5-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="ee3e5-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee3e5-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee3e5-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee3e5-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ee3e5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ee3e5-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ee3e5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee3e5-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="ee3e5-110">Attributes</span></span>  
  
|<span data-ttu-id="ee3e5-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="ee3e5-111">Attribute</span></span>|<span data-ttu-id="ee3e5-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee3e5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee3e5-113">name</span><span class="sxs-lookup"><span data-stu-id="ee3e5-113">name</span></span>|<span data-ttu-id="ee3e5-114">Nome del trasporto.</span><span class="sxs-lookup"><span data-stu-id="ee3e5-114">The name of the transport</span></span>|  
|<span data-ttu-id="ee3e5-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="ee3e5-115">transportConfigurationType</span></span>|<span data-ttu-id="ee3e5-116">Tipo che implementa il trasporto.</span><span class="sxs-lookup"><span data-stu-id="ee3e5-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee3e5-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ee3e5-117">Child Elements</span></span>  
  
|<span data-ttu-id="ee3e5-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee3e5-118">Element</span></span>|<span data-ttu-id="ee3e5-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee3e5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee3e5-120">\<add></span><span class="sxs-lookup"><span data-stu-id="ee3e5-120">\<add></span></span>](add-of-transportconfigurationtype.md)|<span data-ttu-id="ee3e5-121">Aggiunge un elemento di configurazione che identifica il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="ee3e5-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ee3e5-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ee3e5-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ee3e5-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="ee3e5-123">Element</span></span>|<span data-ttu-id="ee3e5-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee3e5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee3e5-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="ee3e5-125">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="ee3e5-126">Definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="ee3e5-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee3e5-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee3e5-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="ee3e5-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="ee3e5-128">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
