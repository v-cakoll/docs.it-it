---
title: Metodo IXCLRDataProcess::EndEnumModules
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
ms.openlocfilehash: de30384b4c12c4fcac3eafe580484685f8a43fa4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775427"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="55f42-102">Metodo IXCLRDataProcess::EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="55f42-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="55f42-103">Rilascia le risorse usate dagli iteratori interni utilizzati durante l'enumerazione di modulo.</span><span class="sxs-lookup"><span data-stu-id="55f42-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="55f42-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55f42-104">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="55f42-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="55f42-105">Parameters</span></span>

`handle`\
<span data-ttu-id="55f42-106">[out] Handle per l'enumerazione dei moduli.</span><span class="sxs-lookup"><span data-stu-id="55f42-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="55f42-107">Note</span><span class="sxs-lookup"><span data-stu-id="55f42-107">Remarks</span></span>

<span data-ttu-id="55f42-108">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 26 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="55f42-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="55f42-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55f42-109">Requirements</span></span>

<span data-ttu-id="55f42-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55f42-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="55f42-111">**Intestazione:** Nessuno **libreria:** Nessuno **versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="55f42-111">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="55f42-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55f42-112">See also</span></span>

- [<span data-ttu-id="55f42-113">Debug</span><span class="sxs-lookup"><span data-stu-id="55f42-113">Debugging</span></span>](index.md)
- [<span data-ttu-id="55f42-114">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="55f42-114">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
