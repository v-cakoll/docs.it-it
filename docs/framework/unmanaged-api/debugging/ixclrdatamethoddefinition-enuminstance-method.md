---
title: Metodo IXCLRDataMethodDefinition::EnumInstance
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: dacf76582916ad50f51ae7c8818b496f31f9553e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353114"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="914c0-102">Metodo IXCLRDataMethodDefinition::EnumInstance</span><span class="sxs-lookup"><span data-stu-id="914c0-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="914c0-103">Enumera le istanze di questa definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="914c0-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="914c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="914c0-104">Syntax</span></span>

```
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="914c0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="914c0-105">Parameters</span></span>

`handle`\
<span data-ttu-id="914c0-106">[in, out] Handle per l'enumerazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="914c0-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="914c0-107">[out] L'istanza enumerata.</span><span class="sxs-lookup"><span data-stu-id="914c0-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="914c0-108">Note</span><span class="sxs-lookup"><span data-stu-id="914c0-108">Remarks</span></span>

<span data-ttu-id="914c0-109">Il metodo specificato fa parte di `IXCLRDataMethodDefinition` interfaccia e corrisponde al quarto slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="914c0-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="914c0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="914c0-110">Requirements</span></span>

<span data-ttu-id="914c0-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="914c0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="914c0-112">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="914c0-112">**Header:** None</span></span>  
<span data-ttu-id="914c0-113">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="914c0-113">**Library:** None</span></span>  
<span data-ttu-id="914c0-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="914c0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="914c0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="914c0-115">See also</span></span>

- [<span data-ttu-id="914c0-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="914c0-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="914c0-117">Debug</span><span class="sxs-lookup"><span data-stu-id="914c0-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="914c0-118">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="914c0-118">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="914c0-119">Interfaccia IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="914c0-119">IXCLRDataMethodInstance Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
