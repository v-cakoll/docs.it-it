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
ms.openlocfilehash: d9430c5a1f37a0507b383ea5437f7d7fed706c43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123855"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="d2f31-102">Metodo ICorDebugChain::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="d2f31-102">ICorDebugChain::GetStackRange Method</span></span>
<span data-ttu-id="d2f31-103">Ottiene l'intervallo di indirizzi del segmento dello stack per questa catena.</span><span class="sxs-lookup"><span data-stu-id="d2f31-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2f31-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d2f31-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2f31-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d2f31-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="d2f31-106">out Puntatore a un valore `CORDB_ADDRESS` che rappresenta l'indirizzo iniziale del segmento dello stack.</span><span class="sxs-lookup"><span data-stu-id="d2f31-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="d2f31-107">out Puntatore a un valore `CORDB_ADDRESS` che rappresenta l'indirizzo finale del segmento dello stack.</span><span class="sxs-lookup"><span data-stu-id="d2f31-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2f31-108">Note</span><span class="sxs-lookup"><span data-stu-id="d2f31-108">Remarks</span></span>  
 <span data-ttu-id="d2f31-109">L'intervallo numerico è significativo solo per il confronto dei percorsi di stack frame.</span><span class="sxs-lookup"><span data-stu-id="d2f31-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="d2f31-110">Non è possibile creare presupposti sugli elementi effettivamente archiviati nello stack.</span><span class="sxs-lookup"><span data-stu-id="d2f31-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2f31-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d2f31-111">Requirements</span></span>  
 <span data-ttu-id="d2f31-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2f31-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2f31-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2f31-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2f31-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2f31-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2f31-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2f31-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
