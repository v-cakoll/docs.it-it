---
title: 'Metodo IXCLRDataMethodDefinition:: EnumInstance'
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
ms.openlocfilehash: ae1ef2a3c8cf9e042ab9ab233ed993f8e36b2fce
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420942"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="2c801-102">Metodo IXCLRDataMethodDefinition:: EnumInstance</span><span class="sxs-lookup"><span data-stu-id="2c801-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="2c801-103">Enumera le istanze di questa definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="2c801-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="2c801-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c801-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="2c801-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2c801-105">Parameters</span></span>

`handle`\
<span data-ttu-id="2c801-106">[in, out] Handle per l'enumerazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="2c801-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="2c801-107">out Istanza enumerata.</span><span class="sxs-lookup"><span data-stu-id="2c801-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="2c801-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2c801-108">Remarks</span></span>

<span data-ttu-id="2c801-109">Il metodo fornito fa parte dell' `IXCLRDataMethodDefinition` interfaccia e corrisponde al sesto slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="2c801-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 6th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="2c801-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c801-110">Requirements</span></span>

<span data-ttu-id="2c801-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c801-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2c801-112">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="2c801-112">**Header:** None</span></span>  
<span data-ttu-id="2c801-113">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="2c801-113">**Library:** None</span></span>  
<span data-ttu-id="2c801-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2c801-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="2c801-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c801-115">See also</span></span>

- [<span data-ttu-id="2c801-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="2c801-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="2c801-117">Debug</span><span class="sxs-lookup"><span data-stu-id="2c801-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="2c801-118">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="2c801-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="2c801-119">Interfaccia IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="2c801-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
