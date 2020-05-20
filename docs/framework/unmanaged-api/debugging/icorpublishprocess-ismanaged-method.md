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
ms.openlocfilehash: 3eec84624866b2be7068d7875cd650828c283fd2
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421098"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="f8ad7-102">Metodo ICorPublishProcess::IsManaged</span><span class="sxs-lookup"><span data-stu-id="f8ad7-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="f8ad7-103">Ottiene un valore che indica se il processo a cui fa riferimento questo [ICorPublishProcess](icorpublishprocess-interface.md) è noto come codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f8ad7-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8ad7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8ad7-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8ad7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f8ad7-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="f8ad7-106">out Puntatore a un valore booleano che indica se il processo dispone di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f8ad7-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="f8ad7-107">Il valore è `true` se il processo dispone di codice gestito; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="f8ad7-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8ad7-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f8ad7-108">Remarks</span></span>  
 <span data-ttu-id="f8ad7-109">Poiché la versione corrente di `ICorPublishProcess` consente l'accesso solo ai processi che hanno codice gestito, `IsManaged` restituisce sempre `true` .</span><span class="sxs-lookup"><span data-stu-id="f8ad7-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8ad7-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8ad7-110">Requirements</span></span>  
 <span data-ttu-id="f8ad7-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8ad7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8ad7-112">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="f8ad7-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f8ad7-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8ad7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8ad7-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8ad7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ad7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8ad7-115">See also</span></span>

- [<span data-ttu-id="f8ad7-116">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="f8ad7-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
