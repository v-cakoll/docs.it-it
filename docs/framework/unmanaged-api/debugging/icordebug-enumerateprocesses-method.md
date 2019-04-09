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
ms.openlocfilehash: 7bc82c506cf7e223e672a62ca74b215cac870e50
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123838"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="da84e-102">Metodo ICorDebug::EnumerateProcesses</span><span class="sxs-lookup"><span data-stu-id="da84e-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="da84e-103">Ottiene un enumeratore per i processi sottoposti a debug.</span><span class="sxs-lookup"><span data-stu-id="da84e-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da84e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da84e-104">Syntax</span></span>  
  
```  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da84e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da84e-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="da84e-106">Un puntatore all'indirizzo di un oggetto ICorDebugProcessEnum che è l'enumeratore per i processi in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="da84e-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da84e-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da84e-107">Requirements</span></span>  
 <span data-ttu-id="da84e-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da84e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da84e-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da84e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da84e-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da84e-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="da84e-111">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="da84e-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da84e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da84e-112">See also</span></span>

- [<span data-ttu-id="da84e-113">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="da84e-113">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
