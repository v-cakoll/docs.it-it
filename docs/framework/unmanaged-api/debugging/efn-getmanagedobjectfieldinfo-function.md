---
title: Funzione _EFN_GetManagedObjectFieldInfo
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
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4822cab8816e97bd1d13c36ea7b63dc9a6f679d0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="efngetmanagedobjectfieldinfo-function"></a><span data-ttu-id="d37e5-102">Funzione _EFN_GetManagedObjectFieldInfo</span><span class="sxs-lookup"><span data-stu-id="d37e5-102">_EFN_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="d37e5-103">Ottiene l'offset per un campo dall'inizio di un oggetto e il valore del campo, usando il puntatore all'oggetto e il nome di campo forniti.</span><span class="sxs-lookup"><span data-stu-id="d37e5-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d37e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d37e5-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d37e5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d37e5-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="d37e5-106">[in] Puntatore al client di debug.</span><span class="sxs-lookup"><span data-stu-id="d37e5-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="d37e5-107">[in] Puntatore a un oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="d37e5-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="d37e5-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="d37e5-108">szFieldName</span></span>  
 <span data-ttu-id="d37e5-109">[in] Un puntatore all'oggetto gestito per il nome del campo.</span><span class="sxs-lookup"><span data-stu-id="d37e5-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="d37e5-110">[out] Il valore del campo.</span><span class="sxs-lookup"><span data-stu-id="d37e5-110">[out] The field value.</span></span> <span data-ttu-id="d37e5-111">Questo parametro può essere null.</span><span class="sxs-lookup"><span data-stu-id="d37e5-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="d37e5-112">[out] L'offset dal `objAddr` al campo.</span><span class="sxs-lookup"><span data-stu-id="d37e5-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="d37e5-113">Questo parametro può essere null.</span><span class="sxs-lookup"><span data-stu-id="d37e5-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d37e5-114">Note</span><span class="sxs-lookup"><span data-stu-id="d37e5-114">Remarks</span></span>  
 <span data-ttu-id="d37e5-115">Se l'offset è 0, viene scritto alcun offset.</span><span class="sxs-lookup"><span data-stu-id="d37e5-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="d37e5-116">Se non è presente nessun codice gestito sul thread attualmente in contesto, la funzione restituisce HRESULT SOS_E_NOMANAGEDCODE con un valore funzionalità 0xa0 e un codice di errore di 0x1000.</span><span class="sxs-lookup"><span data-stu-id="d37e5-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d37e5-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d37e5-117">Requirements</span></span>  
 <span data-ttu-id="d37e5-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d37e5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d37e5-119">**Intestazione:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="d37e5-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="d37e5-120">**Versione di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d37e5-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d37e5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d37e5-121">See Also</span></span>  
 [<span data-ttu-id="d37e5-122">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="d37e5-122">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
