---
title: Metodo ICorDebugChain::EnumerateFrames
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
ms.openlocfilehash: 0b024d3396dfe1796fcb18afa122d4aee39c4ccc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132715"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="18aeb-102">Metodo ICorDebugChain::EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="18aeb-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="18aeb-103">Ottiene un enumeratore che contiene tutti gli stack frame gestiti nella catena, a partire dal frame più recente.</span><span class="sxs-lookup"><span data-stu-id="18aeb-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18aeb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18aeb-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18aeb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="18aeb-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="18aeb-106">out Puntatore all'indirizzo di un oggetto ICorDebugFrameEnum che rappresenta l'enumeratore per gli stack frame.</span><span class="sxs-lookup"><span data-stu-id="18aeb-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18aeb-107">Note</span><span class="sxs-lookup"><span data-stu-id="18aeb-107">Remarks</span></span>  
 <span data-ttu-id="18aeb-108">La catena rappresenta lo stack di chiamate fisico per il thread.</span><span class="sxs-lookup"><span data-stu-id="18aeb-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="18aeb-109">Il metodo di `EnumerateFrames` deve essere chiamato solo per le catene gestite.</span><span class="sxs-lookup"><span data-stu-id="18aeb-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="18aeb-110">L'API di debug non fornisce metodi per ottenere i frame contenuti nelle catene non gestite.</span><span class="sxs-lookup"><span data-stu-id="18aeb-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="18aeb-111">Per ottenere queste informazioni, il debugger deve utilizzare altri mezzi.</span><span class="sxs-lookup"><span data-stu-id="18aeb-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18aeb-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18aeb-112">Requirements</span></span>  
 <span data-ttu-id="18aeb-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18aeb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18aeb-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18aeb-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18aeb-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18aeb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18aeb-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18aeb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
