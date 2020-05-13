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
ms.openlocfilehash: f70a88df00d15729a6bde06b49417b6439f7c0ec
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212464"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="b63b1-102">Metodo ICorDebugManagedCallback::Break</span><span class="sxs-lookup"><span data-stu-id="b63b1-102">ICorDebugManagedCallback::Break Method</span></span>

<span data-ttu-id="b63b1-103">Notifica al debugger quando <xref:System.Reflection.Emit.OpCodes.Break> viene eseguita un'istruzione nel flusso di codice.</span><span class="sxs-lookup"><span data-stu-id="b63b1-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="b63b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b63b1-104">Syntax</span></span>

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a><span data-ttu-id="b63b1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b63b1-105">Parameters</span></span>

`pAppDomain`\
<span data-ttu-id="b63b1-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene l'istruzione break.</span><span class="sxs-lookup"><span data-stu-id="b63b1-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>

`thread`\
<span data-ttu-id="b63b1-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread che contiene l'istruzione break.</span><span class="sxs-lookup"><span data-stu-id="b63b1-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>

## <a name="requirements"></a><span data-ttu-id="b63b1-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b63b1-108">Requirements</span></span>

<span data-ttu-id="b63b1-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b63b1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b63b1-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b63b1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="b63b1-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b63b1-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b63b1-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b63b1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b63b1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b63b1-113">See also</span></span>

- [<span data-ttu-id="b63b1-114">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="b63b1-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
