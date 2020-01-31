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
ms.openlocfilehash: b6393d7fa4853c230203521e665bbe89d7b228e2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790434"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="3b5a5-102">Metodo IXCLRDataMethodDefinition:: EnumInstance</span><span class="sxs-lookup"><span data-stu-id="3b5a5-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="3b5a5-103">Enumera le istanze di questa definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="3b5a5-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3b5a5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3b5a5-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="3b5a5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3b5a5-105">Parameters</span></span>

`handle`\
<span data-ttu-id="3b5a5-106">[in, out] Handle per l'enumerazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="3b5a5-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="3b5a5-107">out Istanza enumerata.</span><span class="sxs-lookup"><span data-stu-id="3b5a5-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b5a5-108">Note</span><span class="sxs-lookup"><span data-stu-id="3b5a5-108">Remarks</span></span>

<span data-ttu-id="3b5a5-109">Il metodo fornito fa parte dell'interfaccia `IXCLRDataMethodDefinition` e corrisponde al quarto slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="3b5a5-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="3b5a5-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3b5a5-110">Requirements</span></span>

<span data-ttu-id="3b5a5-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b5a5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3b5a5-112">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="3b5a5-112">**Header:** None</span></span>  
<span data-ttu-id="3b5a5-113">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="3b5a5-113">**Library:** None</span></span>  
<span data-ttu-id="3b5a5-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3b5a5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3b5a5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b5a5-115">See also</span></span>

- [<span data-ttu-id="3b5a5-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="3b5a5-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="3b5a5-117">Debug</span><span class="sxs-lookup"><span data-stu-id="3b5a5-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="3b5a5-118">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="3b5a5-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="3b5a5-119">Interfaccia IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="3b5a5-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
