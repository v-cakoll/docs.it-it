---
title: Istanze
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 1b2801b5df3a5d2ca6d7fd03299ecdf4b7df426a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520269"
---
# <a name="instances"></a><span data-ttu-id="b7a58-102">Istanze</span><span class="sxs-lookup"><span data-stu-id="b7a58-102">Instances</span></span>
<span data-ttu-id="b7a58-103">Nome contatore: istanze.</span><span class="sxs-lookup"><span data-stu-id="b7a58-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b7a58-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b7a58-104">Description</span></span>  
 <span data-ttu-id="b7a58-105">Numero di contesti di istanza attualmente contenuti dal servizio.</span><span class="sxs-lookup"><span data-stu-id="b7a58-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="b7a58-106">In genere, il numero di contesti di istanza è identico al numero di istanze.</span><span class="sxs-lookup"><span data-stu-id="b7a58-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="b7a58-107">Tuttavia, gli scenari seguenti rappresenta un'eccezione a questa regola.</span><span class="sxs-lookup"><span data-stu-id="b7a58-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="b7a58-108">Un metodo di servizio chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="b7a58-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="b7a58-109">Viene applicata un'enumerazione <xref:System.ServiceModel.ReleaseInstanceMode> a un'istanza di <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b7a58-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a58-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7a58-110">See also</span></span>
- <xref:System.ServiceModel.OperationBehaviorAttribute>
