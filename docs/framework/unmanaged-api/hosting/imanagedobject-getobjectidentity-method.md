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
ms.openlocfilehash: 291246169a5cc2c95b117bc55bc269791885b2ea
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749111"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="13cc5-102">Metodo IManagedObject::GetObjectIdentity</span><span class="sxs-lookup"><span data-stu-id="13cc5-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="13cc5-103">Ottiene l'identità dell'oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="13cc5-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13cc5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13cc5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13cc5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="13cc5-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="13cc5-106">[out] Puntatore al GUID del processo in cui risiede l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="13cc5-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="13cc5-107">[out] Un puntatore all'ID del dominio applicazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="13cc5-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="13cc5-108">[out] Un puntatore all'indice dell'oggetto nella v-table COM classico.</span><span class="sxs-lookup"><span data-stu-id="13cc5-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13cc5-109">Note</span><span class="sxs-lookup"><span data-stu-id="13cc5-109">Remarks</span></span>  
 <span data-ttu-id="13cc5-110">L'identità di un oggetto gestito include GUID processo, ID di dominio dell'applicazione e l'indice dell'oggetto nella v-table COM classico.</span><span class="sxs-lookup"><span data-stu-id="13cc5-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13cc5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13cc5-111">Requirements</span></span>  
 <span data-ttu-id="13cc5-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13cc5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13cc5-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="13cc5-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13cc5-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="13cc5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13cc5-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13cc5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13cc5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13cc5-116">See also</span></span>

- [<span data-ttu-id="13cc5-117">Interfaccia IManagedObject</span><span class="sxs-lookup"><span data-stu-id="13cc5-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
