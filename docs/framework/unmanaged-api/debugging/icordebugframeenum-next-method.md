---
title: Metodo ICorDebugFrameEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
ms.openlocfilehash: ff74a9849b74b8a8e6b8c03f1fc4e7c7eee1ec14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124052"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="c634b-102">Metodo ICorDebugFrameEnum::Next</span><span class="sxs-lookup"><span data-stu-id="c634b-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="c634b-103">Ottiene il numero specificato di istanze di ICorDebugFrame, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="c634b-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c634b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c634b-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c634b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c634b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c634b-106">in Numero di istanze di `ICorDebugFrame` da recuperare.</span><span class="sxs-lookup"><span data-stu-id="c634b-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="c634b-107">out Matrice di puntatori, ciascuno dei quali punta a un oggetto `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="c634b-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c634b-108">out Puntatore al numero di istanze di `ICorDebugFrame` restituite effettivamente.</span><span class="sxs-lookup"><span data-stu-id="c634b-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="c634b-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="c634b-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c634b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c634b-110">Requirements</span></span>  
 <span data-ttu-id="c634b-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c634b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c634b-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c634b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c634b-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c634b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c634b-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c634b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
