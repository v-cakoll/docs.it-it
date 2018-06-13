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
ms.openlocfilehash: ac34fbca56c8a0f00ee3a7e0f898b8ee03287b11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412285"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="ede75-102">Metodo ICorDebugFunction::GetILCode</span><span class="sxs-lookup"><span data-stu-id="ede75-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="ede75-103">Ottiene l'istanza di ICorDebugCode che rappresenta il codice di Microsoft intermediate language (MSIL) associato all'oggetto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="ede75-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ede75-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ede75-104">Syntax</span></span>  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ede75-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ede75-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="ede75-106">[out] Un puntatore al `ICorDebugCode` istanza oppure null se la funzione non è stata compilata in MSIL.</span><span class="sxs-lookup"><span data-stu-id="ede75-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ede75-107">Note</span><span class="sxs-lookup"><span data-stu-id="ede75-107">Remarks</span></span>  
 <span data-ttu-id="ede75-108">Se Modifica e continuazione è stata consentita in questa funzione, il `GetILCode` metodo verrà visualizzato il codice MSIL corrispondente versione modificata la funzione del codice in common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ede75-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ede75-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ede75-109">Requirements</span></span>  
 <span data-ttu-id="ede75-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ede75-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ede75-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ede75-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ede75-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ede75-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ede75-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ede75-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
