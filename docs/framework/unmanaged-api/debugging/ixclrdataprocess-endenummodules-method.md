---
title: 'Metodo IXCLRDataProcess:: EndEnumModules'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 9a7a23e53f5c2bc7d643046830cf335fec780f11
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420838"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="3940d-102">Metodo IXCLRDataProcess:: EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="3940d-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="3940d-103">Rilascia le risorse usate dagli iteratori interni usati durante l'enumerazione del modulo.</span><span class="sxs-lookup"><span data-stu-id="3940d-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3940d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3940d-104">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="3940d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3940d-105">Parameters</span></span>

`handle`\
<span data-ttu-id="3940d-106">out Handle per l'enumerazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="3940d-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="3940d-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3940d-107">Remarks</span></span>

<span data-ttu-id="3940d-108">Il metodo fornito fa parte dell' `IXCLRDataProcess` interfaccia e corrisponde allo slot 26 della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="3940d-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="3940d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3940d-109">Requirements</span></span>

<span data-ttu-id="3940d-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3940d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="3940d-111">**Intestazione:** Nessuna **libreria:** nessuna **.NET Framework versioni:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3940d-111">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3940d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3940d-112">See also</span></span>

- [<span data-ttu-id="3940d-113">Debug</span><span class="sxs-lookup"><span data-stu-id="3940d-113">Debugging</span></span>](index.md)
- [<span data-ttu-id="3940d-114">Interfaccia IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="3940d-114">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
