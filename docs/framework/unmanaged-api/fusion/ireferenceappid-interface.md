---
title: Interfaccia IReferenceAppId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceAppId
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceAppId
helpviewer_keywords: IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cac4ef63292f1bd342bb94799872b002fdcdf945
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="63bf1-102">Interfaccia IReferenceAppId</span><span class="sxs-lookup"><span data-stu-id="63bf1-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="63bf1-103">Rappresenta un riferimento all'identificatore univoco per l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="63bf1-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63bf1-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="63bf1-104">Methods</span></span>  
  
|<span data-ttu-id="63bf1-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="63bf1-105">Method</span></span>|<span data-ttu-id="63bf1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63bf1-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="63bf1-107">Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di codice per l'applicazione a cui fa riferimento questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="63bf1-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="63bf1-108">Imposta l'identificatore di codice per l'applicazione a cui fa riferimento questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="63bf1-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="63bf1-109">Ottiene un puntatore a interfaccia a un `IEnumReferenceIdentity` istanza contenente il `IReferenceIdentity` istanze che rappresentano i membri di questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="63bf1-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="63bf1-110">Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di token per una sottoscrizione a questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="63bf1-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="63bf1-111">Imposta l'identificatore del token per una sottoscrizione a questo `IReferenceAppId` al valore stringa specificato.</span><span class="sxs-lookup"><span data-stu-id="63bf1-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63bf1-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63bf1-112">Requirements</span></span>  
 <span data-ttu-id="63bf1-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63bf1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63bf1-114">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="63bf1-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="63bf1-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63bf1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63bf1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63bf1-116">See Also</span></span>  
 [<span data-ttu-id="63bf1-117">Fusion (interfacce)</span><span class="sxs-lookup"><span data-stu-id="63bf1-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="63bf1-118">IEnumReferenceIdentity (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="63bf1-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [<span data-ttu-id="63bf1-119">IReferenceIdentity (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="63bf1-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
