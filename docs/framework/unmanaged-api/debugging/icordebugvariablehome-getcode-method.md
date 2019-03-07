---
title: Metodo ICorDebugVariableHome::GetCode
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c9b334535f8f6652f30a4b5c9de64bde435c3bd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496222"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="3178b-102">Metodo ICorDebugVariableHome::GetCode</span><span class="sxs-lookup"><span data-stu-id="3178b-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="3178b-103">Ottiene l'istanza "ICorDebugCode" che contiene questo [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="3178b-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3178b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3178b-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3178b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3178b-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="3178b-106">[out] Un puntatore all'indirizzo dell'istanza "ICorDebugCode" che contiene questo [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="3178b-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3178b-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3178b-107">Requirements</span></span>  
 <span data-ttu-id="3178b-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3178b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3178b-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3178b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3178b-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3178b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3178b-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3178b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3178b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3178b-112">See also</span></span>
- [<span data-ttu-id="3178b-113">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="3178b-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)

