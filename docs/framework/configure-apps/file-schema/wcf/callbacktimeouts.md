---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e1b40718638ded54e59743730159ea6e65a51a57
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398190"
---
# \<callbackTimeouts>
<span data-ttu-id="ccf63-101">Specifica il valore di timeout durante la propagazione delle transazioni dal server al client in un scenario di contratto di callback duplex.</span><span class="sxs-lookup"><span data-stu-id="ccf63-101">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="ccf63-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ccf63-102">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="ccf63-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="ccf63-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccf63-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="ccf63-104">Attributes and Elements</span></span>  
 <span data-ttu-id="ccf63-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="ccf63-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccf63-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="ccf63-106">Attributes</span></span>  
  
|<span data-ttu-id="ccf63-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="ccf63-107">Attribute</span></span>|<span data-ttu-id="ccf63-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ccf63-108">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="ccf63-109">Valore <xref:System.TimeSpan> che specifica l'intervallo di tempo entro il quale le transazioni devono essere completate o interrotte automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ccf63-109">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="ccf63-110">Il valore predefinito è "00:00:00".</span><span class="sxs-lookup"><span data-stu-id="ccf63-110">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ccf63-111">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ccf63-111">Child Elements</span></span>  
 <span data-ttu-id="ccf63-112">No.</span><span class="sxs-lookup"><span data-stu-id="ccf63-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ccf63-113">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="ccf63-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ccf63-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ccf63-114">Element</span></span>|<span data-ttu-id="ccf63-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ccf63-115">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ccf63-116">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="ccf63-116">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccf63-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccf63-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
