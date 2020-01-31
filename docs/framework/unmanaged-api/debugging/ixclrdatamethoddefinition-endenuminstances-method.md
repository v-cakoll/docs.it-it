---
title: 'Metodo IXCLRDataMethodDefinition:: EndEnumInstances'
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
ms.openlocfilehash: 605a4244d20ef6c0b7af3c2b26b65ff2a63fa9dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790452"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="4d3d8-102">Metodo IXCLRDataMethodDefinition:: EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="4d3d8-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="4d3d8-103">Rilascia le risorse utilizzate dagli iteratori interni utilizzati durante l'enumerazione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4d3d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d3d8-104">Syntax</span></span>

```cpp
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="4d3d8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4d3d8-105">Parameters</span></span>

`handle`\
<span data-ttu-id="4d3d8-106">out Handle per l'enumerazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="4d3d8-107">Note</span><span class="sxs-lookup"><span data-stu-id="4d3d8-107">Remarks</span></span>

<span data-ttu-id="4d3d8-108">Il metodo fornito fa parte dell'interfaccia `IXCLRDataMethodDefinition` e corrisponde al quinto slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="4d3d8-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fifth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4d3d8-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="4d3d8-109">Requirements</span></span>

<span data-ttu-id="4d3d8-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d3d8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="4d3d8-111">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="4d3d8-111">**Header:** None</span></span>  
<span data-ttu-id="4d3d8-112">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="4d3d8-112">**Library:** None</span></span>  
<span data-ttu-id="4d3d8-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4d3d8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="4d3d8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d3d8-114">See also</span></span>

- [<span data-ttu-id="4d3d8-115">Debug</span><span class="sxs-lookup"><span data-stu-id="4d3d8-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="4d3d8-116">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="4d3d8-116">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
