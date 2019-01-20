---
title: Metodo IXCLRDataMethodDefinition::StartEnumInstances
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::StartEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::StartEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 208d6c46f18834b23e642efa82df0a365013a410
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416570"
---
# <a name="ixclrdatamethoddefinitionstartenuminstances-method"></a><span data-ttu-id="bd6e0-102">Metodo IXCLRDataMethodDefinition::StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="bd6e0-102">IXCLRDataMethodDefinition::StartEnumInstances Method</span></span>

<span data-ttu-id="bd6e0-103">Fornisce un handle per l'enumerazione delle istanze di metodo per un determinato `IXCLRDataAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="bd6e0-103">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="bd6e0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd6e0-104">Syntax</span></span>

```
HRESULT StartEnumInstances(
    [in] IXCLRDataAppDomain* appDomain,
    [out] CLRDATA_ENUM *handle
);
```

### <a name="parameters"></a><span data-ttu-id="bd6e0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bd6e0-105">Parameters</span></span>

<span data-ttu-id="bd6e0-106">`appDomain` [in] Un dominio di applicazione per l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="bd6e0-106">`appDomain` [in] An AppDomain for the enumeration.</span></span>

<span data-ttu-id="bd6e0-107">`handle` [out] Handle per l'enumerazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="bd6e0-107">`handle` [out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd6e0-108">Note</span><span class="sxs-lookup"><span data-stu-id="bd6e0-108">Remarks</span></span>

<span data-ttu-id="bd6e0-109">Il metodo specificato fa parte di `IXCLRDataMethodDefinition` interfaccia e corrisponde al terzo slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="bd6e0-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the third slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="bd6e0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bd6e0-110">Requirements</span></span>

<span data-ttu-id="bd6e0-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd6e0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="bd6e0-112">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="bd6e0-112">**Header:** None</span></span>  
<span data-ttu-id="bd6e0-113">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="bd6e0-113">**Library:** None</span></span>  
<span data-ttu-id="bd6e0-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bd6e0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="bd6e0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd6e0-115">See Also</span></span>

- [<span data-ttu-id="bd6e0-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="bd6e0-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="bd6e0-117">Debug</span><span class="sxs-lookup"><span data-stu-id="bd6e0-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="bd6e0-118">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="bd6e0-118">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
