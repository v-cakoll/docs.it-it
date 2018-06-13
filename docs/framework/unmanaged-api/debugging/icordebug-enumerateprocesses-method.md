---
title: Metodo ICorDebug::EnumerateProcesses
ms.date: 03/30/2017
api_name:
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53d40c198b53370733009c76fd3d49f14df93e6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402096"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="2cea4-102">Metodo ICorDebug::EnumerateProcesses</span><span class="sxs-lookup"><span data-stu-id="2cea4-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="2cea4-103">Ottiene un enumeratore per i processi sottoposti a debug.</span><span class="sxs-lookup"><span data-stu-id="2cea4-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cea4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2cea4-104">Syntax</span></span>  
  
```  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2cea4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2cea4-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="2cea4-106">Un puntatore all'indirizzo di un oggetto ICorDebugProcessEnum che è l'enumeratore per i processi in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="2cea4-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cea4-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2cea4-107">Requirements</span></span>  
 <span data-ttu-id="2cea4-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cea4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cea4-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="2cea4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cea4-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2cea4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cea4-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cea4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cea4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cea4-112">See Also</span></span>  
 [<span data-ttu-id="2cea4-113">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="2cea4-113">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
