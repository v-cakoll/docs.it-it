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
ms.openlocfilehash: 72560de9777b2d826418e63b4a4fcccf1e4fa8b9
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396473"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="68271-102">Metodo IXCLRDataMethodDefinition:: EnumInstance</span><span class="sxs-lookup"><span data-stu-id="68271-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="68271-103">Enumera le istanze di questa definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="68271-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="68271-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="68271-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="68271-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="68271-105">Parameters</span></span>

`handle`\
<span data-ttu-id="68271-106">[in, out] Handle per l'enumerazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="68271-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="68271-107">out Istanza enumerata.</span><span class="sxs-lookup"><span data-stu-id="68271-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="68271-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="68271-108">Remarks</span></span>

<span data-ttu-id="68271-109">Il metodo fornito fa parte dell' `IXCLRDataMethodDefinition` interfaccia e corrisponde al sesto slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="68271-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the 6th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="68271-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="68271-110">Requirements</span></span>

<span data-ttu-id="68271-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68271-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="68271-112">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="68271-112">**Header:** None</span></span>  
<span data-ttu-id="68271-113">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="68271-113">**Library:** None</span></span>  
<span data-ttu-id="68271-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="68271-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="68271-115">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="68271-115">See also</span></span>

- [<span data-ttu-id="68271-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="68271-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="68271-117">Debug</span><span class="sxs-lookup"><span data-stu-id="68271-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="68271-118">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="68271-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="68271-119">Interfaccia IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="68271-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
