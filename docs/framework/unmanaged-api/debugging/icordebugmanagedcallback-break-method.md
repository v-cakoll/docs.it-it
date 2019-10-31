---
title: Metodo ICorDebugManagedCallback::Break
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
ms.openlocfilehash: efc9de050e34867c14f8e85e091e2b959c30f213
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122590"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="2161a-102">Metodo ICorDebugManagedCallback::Break</span><span class="sxs-lookup"><span data-stu-id="2161a-102">ICorDebugManagedCallback::Break Method</span></span>

<span data-ttu-id="2161a-103">Notifica al debugger quando viene eseguita un'istruzione <xref:System.Reflection.Emit.OpCodes.Break> nel flusso di codice.</span><span class="sxs-lookup"><span data-stu-id="2161a-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="2161a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2161a-104">Syntax</span></span>

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a><span data-ttu-id="2161a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2161a-105">Parameters</span></span>

`pAppDomain`\
<span data-ttu-id="2161a-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene l'istruzione break.</span><span class="sxs-lookup"><span data-stu-id="2161a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>

`thread`\
<span data-ttu-id="2161a-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread che contiene l'istruzione break.</span><span class="sxs-lookup"><span data-stu-id="2161a-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>

## <a name="requirements"></a><span data-ttu-id="2161a-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2161a-108">Requirements</span></span>

<span data-ttu-id="2161a-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2161a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="2161a-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2161a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="2161a-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2161a-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="2161a-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2161a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2161a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2161a-113">See also</span></span>

- [<span data-ttu-id="2161a-114">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="2161a-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
