---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e1b40718638ded54e59743730159ea6e65a51a57
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398190"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="c6bb7-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="c6bb7-101">\<callbackTimeouts></span></span>
<span data-ttu-id="c6bb7-102">Specifica il valore di timeout durante la propagazione delle transazioni dal server al client in un scenario di contratto di callback duplex.</span><span class="sxs-lookup"><span data-stu-id="c6bb7-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
<span data-ttu-id="c6bb7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c6bb7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c6bb7-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c6bb7-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c6bb7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamenti >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c6bb7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="c6bb7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c6bb7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="c6bb7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="c6bb7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="c6bb7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> callbackTimeOuts**</span><span class="sxs-lookup"><span data-stu-id="c6bb7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6bb7-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6bb7-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="c6bb7-110">Type</span><span class="sxs-lookup"><span data-stu-id="c6bb7-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6bb7-111">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="c6bb7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c6bb7-112">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c6bb7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6bb7-113">Attributi</span><span class="sxs-lookup"><span data-stu-id="c6bb7-113">Attributes</span></span>  
  
|<span data-ttu-id="c6bb7-114">Attributo</span><span class="sxs-lookup"><span data-stu-id="c6bb7-114">Attribute</span></span>|<span data-ttu-id="c6bb7-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c6bb7-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="c6bb7-116">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo entro il quale le transazioni devono essere completate o interrotte automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c6bb7-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="c6bb7-117">Il valore predefinito è "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="c6bb7-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6bb7-118">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="c6bb7-118">Child Elements</span></span>  
 <span data-ttu-id="c6bb7-119">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c6bb7-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6bb7-120">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="c6bb7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c6bb7-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="c6bb7-121">Element</span></span>|<span data-ttu-id="c6bb7-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c6bb7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6bb7-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c6bb7-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c6bb7-124">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="c6bb7-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6bb7-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6bb7-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
