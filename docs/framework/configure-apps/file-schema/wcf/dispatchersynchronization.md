---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: b95f25217c2a3558846cc7a0ef43e21aacd2ee2a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398008"
---
# \<dispatcherSynchronization>
  
<span data-ttu-id="7efa6-101">Specifica un comportamento dell'endpoint che consente a un servizio di inviare risposte in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="7efa6-101">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**  
  
## <a name="syntax"></a><span data-ttu-id="7efa6-102">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7efa6-102">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="7efa6-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="7efa6-103">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7efa6-104">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7efa6-104">Attributes and elements</span></span>  
  
<span data-ttu-id="7efa6-105">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7efa6-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7efa6-106">Attributi</span><span class="sxs-lookup"><span data-stu-id="7efa6-106">Attributes</span></span>

| <span data-ttu-id="7efa6-107">Attributo</span><span class="sxs-lookup"><span data-stu-id="7efa6-107">Attribute</span></span>               | <span data-ttu-id="7efa6-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7efa6-108">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="7efa6-109">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="7efa6-109">asynchronousSendEnabled</span></span> | <span data-ttu-id="7efa6-110">Valore booleano che specifica se il comportamento di invio asincrono è abilitato.</span><span class="sxs-lookup"><span data-stu-id="7efa6-110">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="7efa6-111">Integer che specifica il numero di ricezioni simultanee che è possibile inviare sul canale.</span><span class="sxs-lookup"><span data-stu-id="7efa6-111">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="7efa6-112">Questo valore deve essere configurato solo dopo aver configurato correttamente il comportamento di limitazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="7efa6-112">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="7efa6-113">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7efa6-113">Child elements</span></span>

<span data-ttu-id="7efa6-114">No.</span><span class="sxs-lookup"><span data-stu-id="7efa6-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7efa6-115">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7efa6-115">Parent elements</span></span>

| <span data-ttu-id="7efa6-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="7efa6-116">Element</span></span> | <span data-ttu-id="7efa6-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7efa6-117">Description</span></span> |  
| ------- | ----------- |  
| [\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="7efa6-118">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="7efa6-118">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7efa6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7efa6-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
