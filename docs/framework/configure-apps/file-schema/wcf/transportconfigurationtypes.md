---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 4be08f780c1095b0016bd130b5719a2a7307d019
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854934"
---
# \<transportConfigurationTypes>
<span data-ttu-id="59943-101">Rappresenta una raccolta di elementi di configurazione che identificano il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="59943-101">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="59943-102">Può essere usato per aggiungere protocolli WAS personalizzati.</span><span class="sxs-lookup"><span data-stu-id="59943-102">This can be used to add custom WAS protocols.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**  
  
## <a name="syntax"></a><span data-ttu-id="59943-103">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59943-103">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59943-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="59943-104">Attributes and Elements</span></span>  
 <span data-ttu-id="59943-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="59943-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59943-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="59943-106">Attributes</span></span>  
  
|<span data-ttu-id="59943-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="59943-107">Attribute</span></span>|<span data-ttu-id="59943-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59943-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59943-109">name</span><span class="sxs-lookup"><span data-stu-id="59943-109">name</span></span>|<span data-ttu-id="59943-110">Nome del trasporto.</span><span class="sxs-lookup"><span data-stu-id="59943-110">The name of the transport</span></span>|  
|<span data-ttu-id="59943-111">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="59943-111">transportConfigurationType</span></span>|<span data-ttu-id="59943-112">Tipo che implementa il trasporto.</span><span class="sxs-lookup"><span data-stu-id="59943-112">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59943-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="59943-113">Child Elements</span></span>  
  
|<span data-ttu-id="59943-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="59943-114">Element</span></span>|<span data-ttu-id="59943-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59943-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-transportconfigurationtype.md)|<span data-ttu-id="59943-116">Aggiunge un elemento di configurazione che identifica il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="59943-116">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59943-117">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="59943-117">Parent Elements</span></span>  
  
|<span data-ttu-id="59943-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="59943-118">Element</span></span>|<span data-ttu-id="59943-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59943-119">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="59943-120">Definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="59943-120">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59943-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="59943-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="59943-122">Hosting</span><span class="sxs-lookup"><span data-stu-id="59943-122">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
