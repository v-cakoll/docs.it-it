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
ms.openlocfilehash: 4a7cd8850778e9bbbc7d8d67f464c7787e40bc13
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566096"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="aa769-102">Metodo IXCLRDataMethodDefinition::EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="aa769-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="aa769-103">Rilascia le risorse usate dagli iteratori interni utilizzati durante l'enumerazione di istanza.</span><span class="sxs-lookup"><span data-stu-id="aa769-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="aa769-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa769-104">Syntax</span></span>

```
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="aa769-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aa769-105">Parameters</span></span>

<span data-ttu-id="aa769-106">`handle` [out] Handle per l'enumerazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="aa769-106">`handle` [out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa769-107">Note</span><span class="sxs-lookup"><span data-stu-id="aa769-107">Remarks</span></span>

<span data-ttu-id="aa769-108">Il metodo specificato fa parte di `IXCLRDataMethodDefinition` interfaccia e corrisponde al quinto slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="aa769-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fifth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="aa769-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa769-109">Requirements</span></span>

<span data-ttu-id="aa769-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa769-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="aa769-111">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="aa769-111">**Header:** None</span></span>  
<span data-ttu-id="aa769-112">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="aa769-112">**Library:** None</span></span>  
<span data-ttu-id="aa769-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="aa769-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="aa769-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa769-114">See also</span></span>

- [<span data-ttu-id="aa769-115">Debug</span><span class="sxs-lookup"><span data-stu-id="aa769-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="aa769-116">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="aa769-116">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
