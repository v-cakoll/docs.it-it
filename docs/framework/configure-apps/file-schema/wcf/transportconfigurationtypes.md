---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: b3683a198ec403fb9966bb902c936108fd043bfa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788245"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="02ef0-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="02ef0-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="02ef0-102">Rappresenta una raccolta di elementi di configurazione che identificano il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="02ef0-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="02ef0-103">Può essere usato per aggiungere protocolli WAS personalizzati.</span><span class="sxs-lookup"><span data-stu-id="02ef0-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="02ef0-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="02ef0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="02ef0-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="02ef0-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="02ef0-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="02ef0-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02ef0-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02ef0-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02ef0-108">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="02ef0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="02ef0-109">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="02ef0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02ef0-110">Attributi</span><span class="sxs-lookup"><span data-stu-id="02ef0-110">Attributes</span></span>  
  
|<span data-ttu-id="02ef0-111">Attributo</span><span class="sxs-lookup"><span data-stu-id="02ef0-111">Attribute</span></span>|<span data-ttu-id="02ef0-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02ef0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02ef0-113">name</span><span class="sxs-lookup"><span data-stu-id="02ef0-113">name</span></span>|<span data-ttu-id="02ef0-114">Nome del trasporto.</span><span class="sxs-lookup"><span data-stu-id="02ef0-114">The name of the transport</span></span>|  
|<span data-ttu-id="02ef0-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="02ef0-115">transportConfigurationType</span></span>|<span data-ttu-id="02ef0-116">Tipo che implementa il trasporto.</span><span class="sxs-lookup"><span data-stu-id="02ef0-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02ef0-117">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="02ef0-117">Child Elements</span></span>  
  
|<span data-ttu-id="02ef0-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="02ef0-118">Element</span></span>|<span data-ttu-id="02ef0-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02ef0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02ef0-120">\<add></span><span class="sxs-lookup"><span data-stu-id="02ef0-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="02ef0-121">Aggiunge un elemento di configurazione che identifica il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="02ef0-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02ef0-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="02ef0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="02ef0-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="02ef0-123">Element</span></span>|<span data-ttu-id="02ef0-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02ef0-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02ef0-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="02ef0-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="02ef0-126">Definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="02ef0-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02ef0-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02ef0-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="02ef0-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="02ef0-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
