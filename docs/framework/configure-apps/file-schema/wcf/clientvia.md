---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b12a882d942555a24c145b243d2cea764ba106b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919499"
---
# <a name="clientvia"></a><span data-ttu-id="fa33a-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="fa33a-101">\<clientVia></span></span>
<span data-ttu-id="fa33a-102">Specifica l'URI per il quale creare il canale del trasporto.</span><span class="sxs-lookup"><span data-stu-id="fa33a-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="fa33a-103">Per altre informazioni, vedere <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="fa33a-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="fa33a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fa33a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fa33a-105">\<comportamenti ></span><span class="sxs-lookup"><span data-stu-id="fa33a-105">\<behaviors></span></span>  
<span data-ttu-id="fa33a-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="fa33a-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="fa33a-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="fa33a-107">\<behavior></span></span>  
<span data-ttu-id="fa33a-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="fa33a-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa33a-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa33a-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa33a-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="fa33a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fa33a-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="fa33a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa33a-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="fa33a-112">Attributes</span></span>  
  
|<span data-ttu-id="fa33a-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="fa33a-113">Attribute</span></span>|<span data-ttu-id="fa33a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa33a-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="fa33a-115">Stringa che specifica un Uri che indica la route che deve essere presa da un messaggio.</span><span class="sxs-lookup"><span data-stu-id="fa33a-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa33a-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="fa33a-116">Child Elements</span></span>  
 <span data-ttu-id="fa33a-117">Nessuna</span><span class="sxs-lookup"><span data-stu-id="fa33a-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa33a-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="fa33a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fa33a-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa33a-119">Element</span></span>|<span data-ttu-id="fa33a-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa33a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa33a-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fa33a-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="fa33a-122">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="fa33a-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa33a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa33a-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
