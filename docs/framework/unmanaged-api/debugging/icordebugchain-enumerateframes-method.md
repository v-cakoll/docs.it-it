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
ms.openlocfilehash: c8a62d8b4a4db0f36d991c32dbfc5bad68780f1b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894687"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="ce1b9-102">Metodo ICorDebugChain::EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="ce1b9-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="ce1b9-103">Ottiene un enumeratore che contiene tutti gli stack frame gestiti nella catena, a partire dal frame più recente.</span><span class="sxs-lookup"><span data-stu-id="ce1b9-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce1b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce1b9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce1b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce1b9-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="ce1b9-106">out Puntatore all'indirizzo di un oggetto ICorDebugFrameEnum che rappresenta l'enumeratore per gli stack frame.</span><span class="sxs-lookup"><span data-stu-id="ce1b9-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce1b9-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ce1b9-107">Remarks</span></span>  
 <span data-ttu-id="ce1b9-108">La catena rappresenta lo stack di chiamate fisico per il thread.</span><span class="sxs-lookup"><span data-stu-id="ce1b9-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="ce1b9-109">Il `EnumerateFrames` metodo deve essere chiamato solo per le catene gestite.</span><span class="sxs-lookup"><span data-stu-id="ce1b9-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="ce1b9-110">L'API di debug non fornisce metodi per ottenere i frame contenuti nelle catene non gestite.</span><span class="sxs-lookup"><span data-stu-id="ce1b9-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="ce1b9-111">Per ottenere queste informazioni, il debugger deve utilizzare altri mezzi.</span><span class="sxs-lookup"><span data-stu-id="ce1b9-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce1b9-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce1b9-112">Requirements</span></span>  
 <span data-ttu-id="ce1b9-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce1b9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce1b9-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce1b9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce1b9-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce1b9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce1b9-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce1b9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
