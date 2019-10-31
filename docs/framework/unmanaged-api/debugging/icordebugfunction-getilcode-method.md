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
ms.openlocfilehash: c2ce4b95de75bef3928e144656b565676568caa0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137905"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="3ad00-102">Metodo ICorDebugFunction::GetILCode</span><span class="sxs-lookup"><span data-stu-id="3ad00-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="3ad00-103">Ottiene l'istanza di ICorDebugCode che rappresenta il codice MSIL (Microsoft Intermediate Language) associato a questo oggetto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="3ad00-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ad00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ad00-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ad00-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3ad00-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="3ad00-106">out Puntatore all'istanza `ICorDebugCode` o null se la funzione non è stata compilata in MSIL.</span><span class="sxs-lookup"><span data-stu-id="3ad00-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ad00-107">Note</span><span class="sxs-lookup"><span data-stu-id="3ad00-107">Remarks</span></span>  
 <span data-ttu-id="3ad00-108">Se in questa funzione è consentita l'autorizzazione Modifica e continuazione, il metodo `GetILCode` otterrà il codice MSIL corrispondente alla versione modificata del codice di questa funzione nel Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3ad00-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ad00-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ad00-109">Requirements</span></span>  
 <span data-ttu-id="3ad00-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ad00-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ad00-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ad00-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ad00-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ad00-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ad00-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ad00-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
