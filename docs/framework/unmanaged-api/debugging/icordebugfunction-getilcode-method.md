---
title: Metodo ICorDebugFunction::GetILCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e32ce10b708afa5741d83cbd05f14accb4b2014f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754674"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="fc3a3-102">Metodo ICorDebugFunction::GetILCode</span><span class="sxs-lookup"><span data-stu-id="fc3a3-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="fc3a3-103">Ottiene l'istanza ICorDebugCode che rappresenta il codice Microsoft intermediate language (MSIL) associato all'oggetto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="fc3a3-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc3a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc3a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc3a3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc3a3-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="fc3a3-106">[out] Un puntatore al `ICorDebugCode` istanza oppure null se la funzione non è stata compilata in MSIL.</span><span class="sxs-lookup"><span data-stu-id="fc3a3-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc3a3-107">Note</span><span class="sxs-lookup"><span data-stu-id="fc3a3-107">Remarks</span></span>  
 <span data-ttu-id="fc3a3-108">Se Modifica e continuazione è stata consentita su questa funzione, il `GetILCode` metodo verrà visualizzato il codice MSIL corrispondente alla versione modificata della funzione del codice in common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="fc3a3-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc3a3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc3a3-109">Requirements</span></span>  
 <span data-ttu-id="fc3a3-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc3a3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc3a3-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc3a3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc3a3-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc3a3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc3a3-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc3a3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
