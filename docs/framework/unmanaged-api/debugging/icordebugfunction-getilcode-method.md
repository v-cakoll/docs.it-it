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
ms.openlocfilehash: 8c7be2d48a30a9f649c6d86e4edbc10085195b68
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213621"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="6e6cd-102">Metodo ICorDebugFunction::GetILCode</span><span class="sxs-lookup"><span data-stu-id="6e6cd-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="6e6cd-103">Ottiene l'istanza di ICorDebugCode che rappresenta il codice MSIL (Microsoft Intermediate Language) associato a questo oggetto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="6e6cd-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e6cd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e6cd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e6cd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6e6cd-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="6e6cd-106">out Puntatore all' `ICorDebugCode` istanza o null se la funzione non è stata compilata in MSIL.</span><span class="sxs-lookup"><span data-stu-id="6e6cd-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e6cd-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6e6cd-107">Remarks</span></span>  
 <span data-ttu-id="6e6cd-108">Se in questa funzione è consentita l'autorizzazione Modifica e continuazione, il `GetILCode` metodo otterrà il codice MSIL corrispondente alla versione modificata del codice di questa funzione nel Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6e6cd-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e6cd-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e6cd-109">Requirements</span></span>  
 <span data-ttu-id="6e6cd-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e6cd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e6cd-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6e6cd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6e6cd-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e6cd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e6cd-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e6cd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
