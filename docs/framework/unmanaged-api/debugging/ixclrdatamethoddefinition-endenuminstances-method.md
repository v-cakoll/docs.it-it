---
title: Metodo IXCLRDataMethodDefinition::EndEnumInstances
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3d9e3ca31eddff9d08607c4d6d37ca76139bf5d2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756301"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="680b8-102">Metodo IXCLRDataMethodDefinition::EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="680b8-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="680b8-103">Rilascia le risorse usate dagli iteratori interni utilizzati durante l'enumerazione di istanza.</span><span class="sxs-lookup"><span data-stu-id="680b8-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="680b8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="680b8-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="680b8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="680b8-105">Parameters</span></span>

`handle`\
<span data-ttu-id="680b8-106">[out] Handle per l'enumerazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="680b8-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="680b8-107">Note</span><span class="sxs-lookup"><span data-stu-id="680b8-107">Remarks</span></span>

<span data-ttu-id="680b8-108">Il metodo specificato fa parte di `IXCLRDataMethodDefinition` interfaccia e corrisponde al quinto slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="680b8-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fifth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="680b8-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="680b8-109">Requirements</span></span>

<span data-ttu-id="680b8-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="680b8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="680b8-111">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="680b8-111">**Header:** None</span></span>  
<span data-ttu-id="680b8-112">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="680b8-112">**Library:** None</span></span>  
<span data-ttu-id="680b8-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="680b8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="680b8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="680b8-114">See also</span></span>

- [<span data-ttu-id="680b8-115">Debug</span><span class="sxs-lookup"><span data-stu-id="680b8-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="680b8-116">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="680b8-116">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
