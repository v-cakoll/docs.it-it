---
title: Metodo ICorDebugValue::GetAddress
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
ms.openlocfilehash: 906ca2540e421953b3ce39300aa7b2376f789929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137106"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="f7f68-102">Metodo ICorDebugValue::GetAddress</span><span class="sxs-lookup"><span data-stu-id="f7f68-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="f7f68-103">Ottiene l'indirizzo di questo oggetto "ICorDebugValue", che è in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="f7f68-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7f68-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7f68-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7f68-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7f68-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="f7f68-106">out Puntatore a un oggetto `CORDB_ADDRESS` che specifica l'indirizzo di questo oggetto valore.</span><span class="sxs-lookup"><span data-stu-id="f7f68-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7f68-107">Note</span><span class="sxs-lookup"><span data-stu-id="f7f68-107">Remarks</span></span>  
 <span data-ttu-id="f7f68-108">Se il valore non è disponibile, viene restituito 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="f7f68-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="f7f68-109">Questo problema può verificarsi se il valore è almeno parzialmente in registri o archiviato in un handle di Garbage Collector (`GCHandle`).</span><span class="sxs-lookup"><span data-stu-id="f7f68-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7f68-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7f68-110">Requirements</span></span>  
 <span data-ttu-id="f7f68-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7f68-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7f68-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7f68-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7f68-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7f68-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7f68-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7f68-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f68-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7f68-115">See also</span></span>
