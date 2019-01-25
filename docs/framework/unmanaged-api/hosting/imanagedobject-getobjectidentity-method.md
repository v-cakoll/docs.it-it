---
title: Metodo IManagedObject::GetObjectIdentity
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fbc4abe55d59c3140c5c180d5844404e357e3a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586308"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="99555-102">Metodo IManagedObject::GetObjectIdentity</span><span class="sxs-lookup"><span data-stu-id="99555-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="99555-103">Ottiene l'identità dell'oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="99555-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99555-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99555-104">Syntax</span></span>  
  
```  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99555-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="99555-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="99555-106">[out] Puntatore al GUID del processo in cui risiede l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="99555-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="99555-107">[out] Un puntatore all'ID del dominio applicazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="99555-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="99555-108">[out] Un puntatore all'indice dell'oggetto nella v-table COM classico.</span><span class="sxs-lookup"><span data-stu-id="99555-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99555-109">Note</span><span class="sxs-lookup"><span data-stu-id="99555-109">Remarks</span></span>  
 <span data-ttu-id="99555-110">L'identità di un oggetto gestito include GUID processo, ID di dominio dell'applicazione e l'indice dell'oggetto nella v-table COM classico.</span><span class="sxs-lookup"><span data-stu-id="99555-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99555-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="99555-111">Requirements</span></span>  
 <span data-ttu-id="99555-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99555-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99555-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="99555-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99555-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="99555-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99555-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99555-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99555-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99555-116">See also</span></span>
- [<span data-ttu-id="99555-117">Interfaccia IManagedObject</span><span class="sxs-lookup"><span data-stu-id="99555-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
