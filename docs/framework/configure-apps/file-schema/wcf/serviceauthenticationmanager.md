---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: cc5ebcf36a10e88d48ed14f1f10dac6396d7b242
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399713"
---
# \<serviceAuthenticationManager>
<span data-ttu-id="ec2bc-101">Fornisce un elemento di configurazione del flusso di lavoro che stabilisce a livello di servizio la validità di una trasmissione, un messaggio o un'origine.</span><span class="sxs-lookup"><span data-stu-id="ec2bc-101">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="ec2bc-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec2bc-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec2bc-103">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ec2bc-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ec2bc-104">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ec2bc-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec2bc-105">Attributi</span><span class="sxs-lookup"><span data-stu-id="ec2bc-105">Attributes</span></span>  
  
|<span data-ttu-id="ec2bc-106">Attributo</span><span class="sxs-lookup"><span data-stu-id="ec2bc-106">Attribute</span></span>|<span data-ttu-id="ec2bc-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec2bc-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec2bc-108">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="ec2bc-108">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="ec2bc-109">Stringa che specifica il tipo del criterio di autenticazione per il comportamento corrente.</span><span class="sxs-lookup"><span data-stu-id="ec2bc-109">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec2bc-110">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ec2bc-110">Child Elements</span></span>  
 <span data-ttu-id="ec2bc-111">No.</span><span class="sxs-lookup"><span data-stu-id="ec2bc-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec2bc-112">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ec2bc-112">Parent Elements</span></span>  
  
|<span data-ttu-id="ec2bc-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="ec2bc-113">Element</span></span>|<span data-ttu-id="ec2bc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec2bc-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ec2bc-115">Specifica un elemento di comportamento.</span><span class="sxs-lookup"><span data-stu-id="ec2bc-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec2bc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec2bc-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
