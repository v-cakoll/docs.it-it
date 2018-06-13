---
title: Istanze
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: a95acf8e775e0802dc0ed781c562fa6373995a70
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473042"
---
# <a name="instances"></a><span data-ttu-id="38625-102">Istanze</span><span class="sxs-lookup"><span data-stu-id="38625-102">Instances</span></span>
<span data-ttu-id="38625-103">Nome contatore: istanze.</span><span class="sxs-lookup"><span data-stu-id="38625-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="38625-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38625-104">Description</span></span>  
 <span data-ttu-id="38625-105">Numero di contesti di istanza attualmente contenuti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="38625-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="38625-106">In genere, il numero di contesti di istanza è identico al numero di istanze.</span><span class="sxs-lookup"><span data-stu-id="38625-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="38625-107">Tuttavia, gli scenari seguenti rappresenta un'eccezione a questa regola.</span><span class="sxs-lookup"><span data-stu-id="38625-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="38625-108">Un metodo di servizio chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="38625-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="38625-109">Viene applicata un'enumerazione <xref:System.ServiceModel.ReleaseInstanceMode> a un'istanza di <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="38625-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38625-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38625-110">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
