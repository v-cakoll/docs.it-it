---
title: Metodo ICorPublishProcess::IsManaged
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29c5f96bab374d6e2d43424370bff2a4a2ab6df3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218290"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="c7c56-102">Metodo ICorPublishProcess::IsManaged</span><span class="sxs-lookup"><span data-stu-id="c7c56-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="c7c56-103">Ottiene un valore che indica se il processo di cui viene fatto riferimento da questo [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) è noto al codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c7c56-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7c56-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7c56-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7c56-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c7c56-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="c7c56-106">[out] Un puntatore a un valore booleano che indica se il processo con codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c7c56-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="c7c56-107">Il valore è `true` se il processo dispone di codice gestito; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c7c56-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7c56-108">Note</span><span class="sxs-lookup"><span data-stu-id="c7c56-108">Remarks</span></span>  
 <span data-ttu-id="c7c56-109">Poiché la versione corrente di `ICorPublishProcess` consenta l'accesso solo ai processi con codice gestito, `IsManaged` restituisce sempre `true`.</span><span class="sxs-lookup"><span data-stu-id="c7c56-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7c56-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7c56-110">Requirements</span></span>  
 <span data-ttu-id="c7c56-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7c56-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7c56-112">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="c7c56-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c7c56-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7c56-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7c56-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7c56-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7c56-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7c56-115">See also</span></span>

- [<span data-ttu-id="c7c56-116">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="c7c56-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
