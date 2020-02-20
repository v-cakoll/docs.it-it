---
title: ICorProfilerInfo10::SuspendRuntime
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.SuspendRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 8d00718579f44a164cd83e2b05d41f70f1c65785
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452149"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="4d104-102">Metodo ICorProfilerInfo10:: SuspendRuntime</span><span class="sxs-lookup"><span data-stu-id="4d104-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="4d104-103">Sospende il runtime senza eseguire un GC.</span><span class="sxs-lookup"><span data-stu-id="4d104-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="4d104-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d104-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="4d104-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d104-105">Requirements</span></span>

<span data-ttu-id="4d104-106">**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="4d104-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="4d104-107">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4d104-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="4d104-108">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d104-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="4d104-109">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d104-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4d104-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d104-110">See also</span></span>

- [<span data-ttu-id="4d104-111">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="4d104-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
