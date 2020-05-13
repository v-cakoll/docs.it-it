---
title: ICorDebugProcess4::P metodo rocessStateChanged
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 910c411d2c63ce2c6cf262e28e08546657dc2a4c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213569"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="0b21e-102">ICorDebugProcess4::P metodo rocessStateChanged</span><span class="sxs-lookup"><span data-stu-id="0b21e-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="0b21e-103">Notifica alla pipeline ICorDebug che il debugger out-of-process sta continuando l'esecuzione del debug.</span><span class="sxs-lookup"><span data-stu-id="0b21e-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b21e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b21e-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="0b21e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0b21e-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="0b21e-106">in Membro dell' [enumerazione CorDebugStateChange](cordebugstatechange-enumeration.md) che descrive una modifica nello stato di esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="0b21e-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b21e-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0b21e-107">Remarks</span></span>

<span data-ttu-id="0b21e-108">Il metodo fornito fa parte dell' `ICorDebugProcess4` interfaccia e corrisponde al quarto slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="0b21e-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="0b21e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b21e-109">Requirements</span></span>

 <span data-ttu-id="0b21e-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b21e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="0b21e-111">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="0b21e-111">**Header:** None</span></span>

 <span data-ttu-id="0b21e-112">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="0b21e-112">**Library:** None</span></span>

 <span data-ttu-id="0b21e-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b21e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0b21e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b21e-114">See also</span></span>

- [<span data-ttu-id="0b21e-115">Interfaccia ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="0b21e-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="0b21e-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0b21e-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0b21e-117">Debug</span><span class="sxs-lookup"><span data-stu-id="0b21e-117">Debugging</span></span>](index.md)
