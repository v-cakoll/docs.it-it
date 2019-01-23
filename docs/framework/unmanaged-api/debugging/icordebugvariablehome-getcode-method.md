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
ms.openlocfilehash: 216779ab03b426ceb8003accfbdd182f583b77cc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557344"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="bd916-102">Metodo ICorDebugVariableHome::GetCode</span><span class="sxs-lookup"><span data-stu-id="bd916-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="bd916-103">Ottiene l'istanza "ICorDebugCode" che contiene questo [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="bd916-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd916-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd916-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd916-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bd916-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="bd916-106">[out] Un puntatore all'indirizzo dell'istanza "ICorDebugCode" che contiene questo [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="bd916-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd916-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bd916-107">Requirements</span></span>  
 <span data-ttu-id="bd916-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd916-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd916-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd916-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd916-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd916-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd916-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd916-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd916-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd916-112">See also</span></span>
- [<span data-ttu-id="bd916-113">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="bd916-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)

