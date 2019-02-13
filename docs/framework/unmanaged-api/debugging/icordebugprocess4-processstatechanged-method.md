---
title: Metodo ICorDebugProcess4::ProcessStateChanged
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
ms.openlocfilehash: b434f30fc187af8b118ac926fec96d28182b0bfc
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221431"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="5328f-102">Metodo ICorDebugProcess4::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="5328f-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="5328f-103">Notifica la pipeline ICorDebug che il timeout del debugger di processo è in continua l'esecuzione dell'oggetto del debug.</span><span class="sxs-lookup"><span data-stu-id="5328f-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="5328f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5328f-104">Syntax</span></span>

```
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

#### <a name="parameters"></a><span data-ttu-id="5328f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5328f-105">Parameters</span></span>

 `eChange`

 <span data-ttu-id="5328f-106">[in] Un membro del [enumerazione CorDebugStateChange](cordebugstatechange-enumeration.md) che descrive una modifica nello stato di esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="5328f-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="5328f-107">Note</span><span class="sxs-lookup"><span data-stu-id="5328f-107">Remarks</span></span>

<span data-ttu-id="5328f-108">Il metodo specificato fa parte di `ICorDebugProcess4` interfaccia e corrisponde al quarto slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="5328f-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5328f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5328f-109">Requirements</span></span>

 <span data-ttu-id="5328f-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5328f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="5328f-111">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="5328f-111">**Header:** None</span></span>

 <span data-ttu-id="5328f-112">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="5328f-112">**Library:** None</span></span>
 
 <span data-ttu-id="5328f-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5328f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5328f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5328f-114">See also</span></span>

- [<span data-ttu-id="5328f-115">Interfaccia ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="5328f-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="5328f-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5328f-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5328f-117">Debug</span><span class="sxs-lookup"><span data-stu-id="5328f-117">Debugging</span></span>](index.md)
