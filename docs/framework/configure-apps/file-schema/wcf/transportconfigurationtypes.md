---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: 4be08f780c1095b0016bd130b5719a2a7307d019
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854934"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="c3f32-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="c3f32-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="c3f32-102">Rappresenta una raccolta di elementi di configurazione che identificano il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="c3f32-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="c3f32-103">Può essere usato per aggiungere protocolli WAS personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c3f32-103">This can be used to add custom WAS protocols.</span></span>  
  
<span data-ttu-id="c3f32-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c3f32-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c3f32-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c3f32-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c3f32-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> serviceHostingEnvironment**](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="c3f32-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="c3f32-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> transportConfigurationTypes**</span><span class="sxs-lookup"><span data-stu-id="c3f32-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transportConfigurationTypes>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3f32-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3f32-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3f32-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c3f32-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c3f32-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c3f32-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3f32-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="c3f32-111">Attributes</span></span>  
  
|<span data-ttu-id="c3f32-112">Attributo</span><span class="sxs-lookup"><span data-stu-id="c3f32-112">Attribute</span></span>|<span data-ttu-id="c3f32-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3f32-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3f32-114">name</span><span class="sxs-lookup"><span data-stu-id="c3f32-114">name</span></span>|<span data-ttu-id="c3f32-115">Nome del trasporto.</span><span class="sxs-lookup"><span data-stu-id="c3f32-115">The name of the transport</span></span>|  
|<span data-ttu-id="c3f32-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="c3f32-116">transportConfigurationType</span></span>|<span data-ttu-id="c3f32-117">Tipo che implementa il trasporto.</span><span class="sxs-lookup"><span data-stu-id="c3f32-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3f32-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c3f32-118">Child Elements</span></span>  
  
|<span data-ttu-id="c3f32-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3f32-119">Element</span></span>|<span data-ttu-id="c3f32-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3f32-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3f32-121">\<add></span><span class="sxs-lookup"><span data-stu-id="c3f32-121">\<add></span></span>](add-of-transportconfigurationtype.md)|<span data-ttu-id="c3f32-122">Aggiunge un elemento di configurazione che identifica il tipo di un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="c3f32-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c3f32-123">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c3f32-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c3f32-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c3f32-124">Element</span></span>|<span data-ttu-id="c3f32-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3f32-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3f32-126">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="c3f32-126">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="c3f32-127">Definisce il tipo del quale l'ambiente host del servizio crea un'istanza per un determinato trasporto.</span><span class="sxs-lookup"><span data-stu-id="c3f32-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3f32-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3f32-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="c3f32-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="c3f32-129">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
