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
ms.openlocfilehash: 8c884569a452fb2985713956f942205cda6ea1ff
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141241"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="01a9e-102">Metodo IManagedObject::GetObjectIdentity</span><span class="sxs-lookup"><span data-stu-id="01a9e-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="01a9e-103">Ottiene l'identità di questo oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="01a9e-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01a9e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01a9e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01a9e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="01a9e-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="01a9e-106">out Puntatore al GUID del processo in cui si trova l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="01a9e-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="01a9e-107">out Puntatore all'ID del dominio dell'applicazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="01a9e-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="01a9e-108">out Puntatore all'indice dell'oggetto nella tabella v classica COM.</span><span class="sxs-lookup"><span data-stu-id="01a9e-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01a9e-109">Note</span><span class="sxs-lookup"><span data-stu-id="01a9e-109">Remarks</span></span>  
 <span data-ttu-id="01a9e-110">L'identità di un oggetto gestito include il GUID del processo, l'ID del dominio dell'applicazione e l'indice dell'oggetto nella tabella v classica COM.</span><span class="sxs-lookup"><span data-stu-id="01a9e-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01a9e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01a9e-111">Requirements</span></span>  
 <span data-ttu-id="01a9e-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01a9e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01a9e-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="01a9e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01a9e-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="01a9e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01a9e-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01a9e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01a9e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01a9e-116">See also</span></span>

- [<span data-ttu-id="01a9e-117">Interfaccia IManagedObject</span><span class="sxs-lookup"><span data-stu-id="01a9e-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
