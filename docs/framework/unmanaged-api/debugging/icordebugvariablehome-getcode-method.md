---
title: 'Metodo ICorDebugVariableHome:: GetCode'
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
ms.openlocfilehash: 4770eb3e93104dd3862eb2163faf1dc7fe9008ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125132"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="84070-102">Metodo ICorDebugVariableHome:: GetCode</span><span class="sxs-lookup"><span data-stu-id="84070-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="84070-103">Ottiene l'istanza "ICorDebugCode" che contiene questo oggetto [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="84070-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84070-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84070-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84070-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="84070-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="84070-106">out Puntatore all'indirizzo dell'istanza "ICorDebugCode" che contiene questo oggetto [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="84070-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84070-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84070-107">Requirements</span></span>  
 <span data-ttu-id="84070-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84070-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84070-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84070-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84070-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84070-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84070-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84070-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84070-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84070-112">See also</span></span>

- [<span data-ttu-id="84070-113">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="84070-113">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
