---
title: Istanze
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 668cfb3026b9ab7259665f5e53873a512b1e2238
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118989"
---
# <a name="instances"></a><span data-ttu-id="e68a9-102">Istanze</span><span class="sxs-lookup"><span data-stu-id="e68a9-102">Instances</span></span>
<span data-ttu-id="e68a9-103">Nome contatore: istanze.</span><span class="sxs-lookup"><span data-stu-id="e68a9-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e68a9-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e68a9-104">Description</span></span>  
 <span data-ttu-id="e68a9-105">Numero di contesti di istanza attualmente contenuti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="e68a9-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="e68a9-106">In genere, il numero di contesti di istanza è identico al numero di istanze.</span><span class="sxs-lookup"><span data-stu-id="e68a9-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="e68a9-107">Tuttavia, gli scenari seguenti rappresenta un'eccezione a questa regola.</span><span class="sxs-lookup"><span data-stu-id="e68a9-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="e68a9-108">Un metodo di servizio chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="e68a9-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="e68a9-109">Viene applicata un'enumerazione <xref:System.ServiceModel.ReleaseInstanceMode> a un'istanza di <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e68a9-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e68a9-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e68a9-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
