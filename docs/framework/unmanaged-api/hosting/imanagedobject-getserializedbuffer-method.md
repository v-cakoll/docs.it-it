---
title: Metodo IManagedObject::GetSerializedBuffer
ms.date: 03/30/2017
api_name:
- IManagedObject.GetSerializedBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetSerializedBuffer
helpviewer_keywords:
- IManagedObject::GetSerializedBuffer method [.NET Framework hosting]
- GetSerializedBuffer method [.NET Framework hosting]
ms.assetid: c17105bb-b49f-434e-8f9b-77f8c85b9220
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb9242160b684b3c7b90756d7b20811ad162fc30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59156143"
---
# <a name="imanagedobjectgetserializedbuffer-method"></a><span data-ttu-id="f0e90-102">Metodo IManagedObject::GetSerializedBuffer</span><span class="sxs-lookup"><span data-stu-id="f0e90-102">IManagedObject::GetSerializedBuffer Method</span></span>
<span data-ttu-id="f0e90-103">Ottiene la rappresentazione di stringa dell'oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="f0e90-103">Gets the string representation of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0e90-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0e90-104">Syntax</span></span>  
  
```  
HRESULT GetSerializedBuffer (  
    [out] BSTR *pBSTR  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0e90-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f0e90-105">Parameters</span></span>  
 `pBSTR`  
 <span data-ttu-id="f0e90-106">[out] Puntatore a una stringa che rappresenta l'oggetto serializzato.</span><span class="sxs-lookup"><span data-stu-id="f0e90-106">[out] A pointer to a string that is the serialized object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0e90-107">Note</span><span class="sxs-lookup"><span data-stu-id="f0e90-107">Remarks</span></span>  
 <span data-ttu-id="f0e90-108">Il `GetSerializedBuffer` metodo serializza l'oggetto che può essere sottoposta a marshalling al client.</span><span class="sxs-lookup"><span data-stu-id="f0e90-108">The `GetSerializedBuffer` method serializes the object so it can be marshaled to the client.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0e90-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0e90-109">Requirements</span></span>  
 <span data-ttu-id="f0e90-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0e90-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0e90-111">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f0e90-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0e90-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f0e90-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0e90-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0e90-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0e90-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0e90-114">See also</span></span>

- [<span data-ttu-id="f0e90-115">Interfaccia IManagedObject</span><span class="sxs-lookup"><span data-stu-id="f0e90-115">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
