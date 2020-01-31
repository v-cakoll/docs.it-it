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
ms.openlocfilehash: 4cc6bbde2c7367c1109ca73e66f2670a56b2cdbe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790551"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="64ddd-102">Metodo ICorPublishProcess::GetProcessID</span><span class="sxs-lookup"><span data-stu-id="64ddd-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="64ddd-103">Ottiene l'identificatore del sistema operativo per questo processo.</span><span class="sxs-lookup"><span data-stu-id="64ddd-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64ddd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64ddd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64ddd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="64ddd-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="64ddd-106">out Puntatore all'identificatore del processo rappresentato da questo oggetto [ICorPublishProcess](icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="64ddd-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64ddd-107">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="64ddd-107">Requirements</span></span>  
 <span data-ttu-id="64ddd-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64ddd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64ddd-109">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="64ddd-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="64ddd-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64ddd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64ddd-111">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64ddd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ddd-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64ddd-112">See also</span></span>

- [<span data-ttu-id="64ddd-113">Interfaccia ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="64ddd-113">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
