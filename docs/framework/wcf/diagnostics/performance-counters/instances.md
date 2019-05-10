---
title: Istanze
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: e0be9c93b5efe17235dbccd426cdd73fbb739361
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651840"
---
# <a name="instances"></a><span data-ttu-id="fa78d-102">Istanze</span><span class="sxs-lookup"><span data-stu-id="fa78d-102">Instances</span></span>
<span data-ttu-id="fa78d-103">Nome contatore: istanze.</span><span class="sxs-lookup"><span data-stu-id="fa78d-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="fa78d-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fa78d-104">Description</span></span>  
 <span data-ttu-id="fa78d-105">Numero di contesti di istanza attualmente contenuti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="fa78d-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="fa78d-106">In genere, il numero di contesti di istanza è identico al numero di istanze.</span><span class="sxs-lookup"><span data-stu-id="fa78d-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="fa78d-107">Tuttavia, gli scenari seguenti rappresenta un'eccezione a questa regola.</span><span class="sxs-lookup"><span data-stu-id="fa78d-107">However, the following scenarios are exception to this rule.</span></span>  
  
- <span data-ttu-id="fa78d-108">Un metodo di servizio chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="fa78d-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
- <span data-ttu-id="fa78d-109">Viene applicata un'enumerazione <xref:System.ServiceModel.ReleaseInstanceMode> a un'istanza di <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fa78d-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa78d-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa78d-110">See also</span></span>

- <xref:System.ServiceModel.OperationBehaviorAttribute>
