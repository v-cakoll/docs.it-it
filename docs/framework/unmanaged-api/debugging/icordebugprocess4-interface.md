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
ms.openlocfilehash: fcf725ea98fa4351e72cf592f92968ee2233ecb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213582"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="3302f-102">Interfaccia ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="3302f-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="3302f-103">Fornisce supporto per il controllo dell'esecuzione out-of-process.</span><span class="sxs-lookup"><span data-stu-id="3302f-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="3302f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3302f-104">Methods</span></span>

| <span data-ttu-id="3302f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3302f-105">Method</span></span>                                                                 | <span data-ttu-id="3302f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3302f-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="3302f-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="3302f-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="3302f-108">Notifica alla pipeline ICorDebug che il debugger out-of-process sta continuando l'esecuzione del debug.</span><span class="sxs-lookup"><span data-stu-id="3302f-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="3302f-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3302f-109">Remarks</span></span>

<span data-ttu-id="3302f-110">Questa interfaccia si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="3302f-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="3302f-111">Tuttavia, si tratta di un'interfaccia COM che deriva da `IUnknown` con GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` che è possibile ottenere tramite i normali meccanismi com.</span><span class="sxs-lookup"><span data-stu-id="3302f-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="3302f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3302f-112">Requirements</span></span>

<span data-ttu-id="3302f-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3302f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3302f-114">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="3302f-114">**Header:** None</span></span>

<span data-ttu-id="3302f-115">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="3302f-115">**Library:** None</span></span>

<span data-ttu-id="3302f-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3302f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3302f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3302f-117">See also</span></span>

- [<span data-ttu-id="3302f-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3302f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3302f-119">Debug</span><span class="sxs-lookup"><span data-stu-id="3302f-119">Debugging</span></span>](index.md)
