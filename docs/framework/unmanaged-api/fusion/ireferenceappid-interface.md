---
title: Interfaccia IReferenceAppId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 22ac2d75632b3c670d7c185cbbf5081732dcaffc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="ffe66-102">Interfaccia IReferenceAppId</span><span class="sxs-lookup"><span data-stu-id="ffe66-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="ffe66-103">Rappresenta un riferimento all'identificatore univoco per l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="ffe66-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ffe66-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ffe66-104">Methods</span></span>  
  
|<span data-ttu-id="ffe66-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ffe66-105">Method</span></span>|<span data-ttu-id="ffe66-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ffe66-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="ffe66-107">Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di codice per l'applicazione a cui fa riferimento questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="ffe66-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="ffe66-108">Imposta l'identificatore di codice per l'applicazione a cui fa riferimento questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="ffe66-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="ffe66-109">Ottiene un puntatore a interfaccia a un `IEnumReferenceIdentity` istanza contenente il `IReferenceIdentity` istanze che rappresentano i membri di questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="ffe66-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="ffe66-110">Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di token per una sottoscrizione a questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="ffe66-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="ffe66-111">Imposta l'identificatore del token per una sottoscrizione a questo `IReferenceAppId` al valore stringa specificato.</span><span class="sxs-lookup"><span data-stu-id="ffe66-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffe66-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ffe66-112">Requirements</span></span>  
 <span data-ttu-id="ffe66-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffe66-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffe66-114">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="ffe66-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="ffe66-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffe66-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffe66-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffe66-116">See Also</span></span>  
 [<span data-ttu-id="ffe66-117">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="ffe66-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="ffe66-118">Interfaccia IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="ffe66-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [<span data-ttu-id="ffe66-119">Interfaccia IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="ffe66-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
