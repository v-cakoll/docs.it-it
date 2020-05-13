---
title: Metodo ICorDebugFrame::GetCaller
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
ms.openlocfilehash: b29de0b70daa783197e78fe985d379d4124bc140
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205140"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="f9297-102">Metodo ICorDebugFrame::GetCaller</span><span class="sxs-lookup"><span data-stu-id="f9297-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="f9297-103">Ottiene un puntatore all'oggetto ICorDebugFrame nella catena corrente che ha chiamato questo frame.</span><span class="sxs-lookup"><span data-stu-id="f9297-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9297-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9297-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9297-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f9297-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="f9297-106">out Puntatore all'indirizzo di un `ICorDebugFrame` oggetto che rappresenta il frame chiamante.</span><span class="sxs-lookup"><span data-stu-id="f9297-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="f9297-107">Questo valore è null se il frame chiamato è il frame più esterno nella catena corrente.</span><span class="sxs-lookup"><span data-stu-id="f9297-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9297-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9297-108">Requirements</span></span>  
 <span data-ttu-id="f9297-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9297-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9297-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9297-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9297-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9297-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9297-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9297-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
