---
title: Metodo ICorPublishProcess::GetProcessID
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
ms.openlocfilehash: 95a4ef3ab77b33c67c63be2c22647075f2f95ce8
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421111"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="fd149-102">Metodo ICorPublishProcess::GetProcessID</span><span class="sxs-lookup"><span data-stu-id="fd149-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="fd149-103">Ottiene l'identificatore del sistema operativo per questo processo.</span><span class="sxs-lookup"><span data-stu-id="fd149-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd149-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd149-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd149-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fd149-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="fd149-106">out Puntatore all'identificatore del processo rappresentato da questo oggetto [ICorPublishProcess](icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="fd149-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd149-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd149-107">Requirements</span></span>  
 <span data-ttu-id="fd149-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd149-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd149-109">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="fd149-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="fd149-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd149-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd149-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd149-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd149-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd149-112">See also</span></span>

- [<span data-ttu-id="fd149-113">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="fd149-113">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
