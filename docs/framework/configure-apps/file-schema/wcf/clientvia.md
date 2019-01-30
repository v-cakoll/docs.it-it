---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 063dbee71a91e098e26026ea78c74642115c7955
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266663"
---
# <a name="clientvia"></a><span data-ttu-id="1475b-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="1475b-101">\<clientVia></span></span>
<span data-ttu-id="1475b-102">Specifica l'URI per il quale creare il canale del trasporto.</span><span class="sxs-lookup"><span data-stu-id="1475b-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="1475b-103">Per altre informazioni, vedere <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="1475b-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="1475b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1475b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1475b-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="1475b-105">\<behaviors></span></span>  
<span data-ttu-id="1475b-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="1475b-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="1475b-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1475b-107">\<behavior></span></span>  
<span data-ttu-id="1475b-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="1475b-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1475b-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1475b-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1475b-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="1475b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1475b-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="1475b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1475b-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="1475b-112">Attributes</span></span>  
  
|<span data-ttu-id="1475b-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="1475b-113">Attribute</span></span>|<span data-ttu-id="1475b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1475b-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="1475b-115">Stringa che specifica un Uri che indica la route che deve essere presa da un messaggio.</span><span class="sxs-lookup"><span data-stu-id="1475b-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1475b-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="1475b-116">Child Elements</span></span>  
 <span data-ttu-id="1475b-117">nessuno</span><span class="sxs-lookup"><span data-stu-id="1475b-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1475b-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="1475b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1475b-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="1475b-119">Element</span></span>|<span data-ttu-id="1475b-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1475b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1475b-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1475b-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="1475b-122">Specifica un comportamento dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="1475b-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1475b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1475b-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
