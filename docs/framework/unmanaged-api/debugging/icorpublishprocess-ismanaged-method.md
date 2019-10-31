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
ms.openlocfilehash: ad3a357a98cb5ed28a34e4076b5e145903ceaf91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103494"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="f6a4e-102">Metodo ICorPublishProcess::IsManaged</span><span class="sxs-lookup"><span data-stu-id="f6a4e-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="f6a4e-103">Ottiene un valore che indica se il processo a cui fa riferimento questo [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) è noto come codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f6a4e-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6a4e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6a4e-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6a4e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f6a4e-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="f6a4e-106">out Puntatore a un valore booleano che indica se il processo dispone di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f6a4e-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="f6a4e-107">Il valore è `true` se il processo dispone di codice gestito; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f6a4e-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6a4e-108">Note</span><span class="sxs-lookup"><span data-stu-id="f6a4e-108">Remarks</span></span>  
 <span data-ttu-id="f6a4e-109">Poiché la versione corrente di `ICorPublishProcess` consente l'accesso solo ai processi che dispongono di codice gestito, `IsManaged` restituisce sempre `true`.</span><span class="sxs-lookup"><span data-stu-id="f6a4e-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6a4e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6a4e-110">Requirements</span></span>  
 <span data-ttu-id="f6a4e-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6a4e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6a4e-112">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="f6a4e-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f6a4e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6a4e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6a4e-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6a4e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6a4e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6a4e-115">See also</span></span>

- [<span data-ttu-id="f6a4e-116">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="f6a4e-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
