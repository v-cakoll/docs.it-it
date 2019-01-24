---
title: Interfaccia IReferenceAppId
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2289a9a75311c9642a764844ee466adcc5838655
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744349"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="8638e-102">Interfaccia IReferenceAppId</span><span class="sxs-lookup"><span data-stu-id="8638e-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="8638e-103">Rappresenta un riferimento all'identificatore univoco per l'applicazione nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="8638e-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8638e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8638e-104">Methods</span></span>  
  
|<span data-ttu-id="8638e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8638e-105">Method</span></span>|<span data-ttu-id="8638e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8638e-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="8638e-107">Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di codice per l'applicazione fa riferimento questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="8638e-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="8638e-108">Imposta l'identificatore di codice per l'applicazione fa riferimento questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="8638e-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="8638e-109">Ottiene un puntatore a interfaccia a un `IEnumReferenceIdentity` istanza contenente il `IReferenceIdentity` istanze che rappresentano i membri di questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="8638e-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="8638e-110">Ottiene un puntatore a una rappresentazione di stringa dell'identificatore del token per una sottoscrizione a questo `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="8638e-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="8638e-111">Imposta l'identificatore del token per una sottoscrizione a questo `IReferenceAppId` sul valore di stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="8638e-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8638e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8638e-112">Requirements</span></span>  
 <span data-ttu-id="8638e-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8638e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8638e-114">**Intestazione:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="8638e-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="8638e-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8638e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8638e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8638e-116">See also</span></span>
- [<span data-ttu-id="8638e-117">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="8638e-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="8638e-118">Interfaccia IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="8638e-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)
- [<span data-ttu-id="8638e-119">Interfaccia IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="8638e-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
