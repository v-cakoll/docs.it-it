---
title: Metodo ICorDebugChain::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
ms.openlocfilehash: 40ecc183c32500ad9e88ceb1bfc0528d717430e8
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894460"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="e5b6c-102">Metodo ICorDebugChain::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="e5b6c-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="e5b6c-103">Ottiene l'intervallo di indirizzi del segmento dello stack per questa catena.</span><span class="sxs-lookup"><span data-stu-id="e5b6c-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5b6c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5b6c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5b6c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5b6c-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="e5b6c-106">out Puntatore a un `CORDB_ADDRESS` valore che rappresenta l'indirizzo iniziale del segmento dello stack.</span><span class="sxs-lookup"><span data-stu-id="e5b6c-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="e5b6c-107">out Puntatore a un `CORDB_ADDRESS` valore che rappresenta l'indirizzo finale del segmento dello stack.</span><span class="sxs-lookup"><span data-stu-id="e5b6c-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5b6c-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e5b6c-108">Remarks</span></span>  
 <span data-ttu-id="e5b6c-109">L'intervallo numerico è significativo solo per il confronto dei percorsi di stack frame.</span><span class="sxs-lookup"><span data-stu-id="e5b6c-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="e5b6c-110">Non è possibile creare presupposti sugli elementi effettivamente archiviati nello stack.</span><span class="sxs-lookup"><span data-stu-id="e5b6c-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5b6c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5b6c-111">Requirements</span></span>  
 <span data-ttu-id="e5b6c-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5b6c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5b6c-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5b6c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5b6c-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5b6c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5b6c-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5b6c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
