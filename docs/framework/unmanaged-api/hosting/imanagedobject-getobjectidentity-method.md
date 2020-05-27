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
ms.openlocfilehash: 1b40ed8e107d30c22b4ade25d29376b1b74583d1
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842413"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="dba68-102">Metodo IManagedObject::GetObjectIdentity</span><span class="sxs-lookup"><span data-stu-id="dba68-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="dba68-103">Ottiene l'identità di questo oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="dba68-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dba68-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dba68-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dba68-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dba68-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="dba68-106">out Puntatore al GUID del processo in cui si trova l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="dba68-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="dba68-107">out Puntatore all'ID del dominio dell'applicazione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="dba68-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="dba68-108">out Puntatore all'indice dell'oggetto nella tabella v classica COM.</span><span class="sxs-lookup"><span data-stu-id="dba68-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dba68-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dba68-109">Remarks</span></span>  
 <span data-ttu-id="dba68-110">L'identità di un oggetto gestito include il GUID del processo, l'ID del dominio dell'applicazione e l'indice dell'oggetto nella tabella v classica COM.</span><span class="sxs-lookup"><span data-stu-id="dba68-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dba68-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dba68-111">Requirements</span></span>  
 <span data-ttu-id="dba68-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dba68-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dba68-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dba68-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dba68-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dba68-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dba68-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dba68-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba68-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dba68-116">See also</span></span>

- [<span data-ttu-id="dba68-117">Interfaccia IManagedObject</span><span class="sxs-lookup"><span data-stu-id="dba68-117">IManagedObject Interface</span></span>](imanagedobject-interface.md)
