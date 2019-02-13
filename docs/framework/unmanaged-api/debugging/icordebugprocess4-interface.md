---
title: Interfaccia ICorDebugProcess4
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4
helpviewer_keywords:
- ICorDebugProcess4 interface [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 1bdc958f2516bcd7c2eb74312fbf478e6d49535a
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221426"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="3a076-102">Interfaccia ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="3a076-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="3a076-103">Fornisce supporto per dal controllo l'esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="3a076-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="3a076-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3a076-104">Methods</span></span>

| <span data-ttu-id="3a076-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3a076-105">Method</span></span>                                                                 | <span data-ttu-id="3a076-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a076-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="3a076-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="3a076-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="3a076-108">Notifica la pipeline ICorDebug che il timeout del debugger di processo è in continua l'esecuzione dell'oggetto del debug.</span><span class="sxs-lookup"><span data-stu-id="3a076-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="3a076-109">Note</span><span class="sxs-lookup"><span data-stu-id="3a076-109">Remarks</span></span>

<span data-ttu-id="3a076-110">Questa interfaccia si trova all'interno del runtime e non è esposte tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="3a076-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="3a076-111">Tuttavia, è un'interfaccia COM che deriva da `IUnknown` con GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` che può essere ottenuto tramite i normali meccanismi di COM.</span><span class="sxs-lookup"><span data-stu-id="3a076-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="3a076-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a076-112">Requirements</span></span>

<span data-ttu-id="3a076-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a076-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="3a076-114">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="3a076-114">**Header:** None</span></span>

<span data-ttu-id="3a076-115">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="3a076-115">**Library:** None</span></span>

<span data-ttu-id="3a076-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a076-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3a076-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a076-117">See also</span></span>

- [<span data-ttu-id="3a076-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3a076-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3a076-119">Debug</span><span class="sxs-lookup"><span data-stu-id="3a076-119">Debugging</span></span>](index.md)
