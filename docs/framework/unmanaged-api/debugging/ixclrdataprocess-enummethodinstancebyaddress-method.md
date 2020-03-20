---
title: Metodo IXCLRDataProcess::EnumMethodInstanceByAddressIXCLRDataProcess::EnumMethodInstanceByAddress Method
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: afc5fc377dd45d5e8d4d2d7b3385ca0524df69e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176656"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="4440f-102">Metodo IXCLRDataProcess::EnumMethodInstanceByAddressIXCLRDataProcess::EnumMethodInstanceByAddress Method</span><span class="sxs-lookup"><span data-stu-id="4440f-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="4440f-103">Enumera le istanze del metodo di questo processo a partire da un offset di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="4440f-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4440f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4440f-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="4440f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4440f-105">Parameters</span></span>

`handle`\
<span data-ttu-id="4440f-106">[in] Handle per l'enumerazione delle istanze del metodo.</span><span class="sxs-lookup"><span data-stu-id="4440f-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="4440f-107">[fuori] Istanza del metodo enumerato.</span><span class="sxs-lookup"><span data-stu-id="4440f-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="4440f-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4440f-108">Remarks</span></span>

<span data-ttu-id="4440f-109">Il metodo fornito fa `IXCLRDataProcess` parte dell'interfaccia e corrisponde al 28esimo slot della tabella dei metodi virtuali.</span><span class="sxs-lookup"><span data-stu-id="4440f-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="4440f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4440f-110">Requirements</span></span>

<span data-ttu-id="4440f-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4440f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="4440f-112">**Intestazione:** Nessuno **libreria:** nessuna versione di **.NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4440f-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4440f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4440f-113">See also</span></span>

- [<span data-ttu-id="4440f-114">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="4440f-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="4440f-115">Debug</span><span class="sxs-lookup"><span data-stu-id="4440f-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="4440f-116">Interfaccia IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="4440f-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
