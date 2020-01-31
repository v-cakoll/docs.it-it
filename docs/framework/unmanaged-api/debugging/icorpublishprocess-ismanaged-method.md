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
ms.openlocfilehash: 68931ba16ea1f8f61176c6d6ed8300e762b61690
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790532"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="6b653-102">Metodo ICorPublishProcess::IsManaged</span><span class="sxs-lookup"><span data-stu-id="6b653-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="6b653-103">Ottiene un valore che indica se il processo a cui fa riferimento questo [ICorPublishProcess](icorpublishprocess-interface.md) è noto come codice gestito.</span><span class="sxs-lookup"><span data-stu-id="6b653-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b653-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b653-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b653-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6b653-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="6b653-106">out Puntatore a un valore booleano che indica se il processo dispone di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="6b653-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="6b653-107">Il valore è `true` se il processo dispone di codice gestito; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="6b653-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b653-108">Note</span><span class="sxs-lookup"><span data-stu-id="6b653-108">Remarks</span></span>  
 <span data-ttu-id="6b653-109">Poiché la versione corrente di `ICorPublishProcess` consente l'accesso solo ai processi che dispongono di codice gestito, `IsManaged` restituisce sempre `true`.</span><span class="sxs-lookup"><span data-stu-id="6b653-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b653-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="6b653-110">Requirements</span></span>  
 <span data-ttu-id="6b653-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b653-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b653-112">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="6b653-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6b653-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b653-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b653-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b653-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b653-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b653-115">See also</span></span>

- [<span data-ttu-id="6b653-116">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="6b653-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
