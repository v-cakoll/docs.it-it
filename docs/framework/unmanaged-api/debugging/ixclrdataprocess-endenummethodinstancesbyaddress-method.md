---
title: Metodo IXCLRDataProcess::EndEnumMethodInstancesByAddress
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 072e775d11d44dfbca27f1616889e388ae61d467
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365997"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="1785b-102">Metodo IXCLRDataProcess::EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="1785b-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="1785b-103">Rilascia le risorse usate dagli iteratori interni utilizzati durante l'enumerazione di istanza.</span><span class="sxs-lookup"><span data-stu-id="1785b-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="1785b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1785b-104">Syntax</span></span>

```
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="1785b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1785b-105">Parameters</span></span>

`handle`\
<span data-ttu-id="1785b-106">[out] Handle per l'enumerazione delle istanze di metodo.</span><span class="sxs-lookup"><span data-stu-id="1785b-106">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="1785b-107">Note</span><span class="sxs-lookup"><span data-stu-id="1785b-107">Remarks</span></span>

<span data-ttu-id="1785b-108">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 29 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="1785b-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="1785b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1785b-109">Requirements</span></span>

<span data-ttu-id="1785b-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1785b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1785b-111">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="1785b-111">**Header:** None</span></span>  
<span data-ttu-id="1785b-112">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="1785b-112">**Library:** None</span></span>  
<span data-ttu-id="1785b-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1785b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="1785b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1785b-114">See also</span></span>

- [<span data-ttu-id="1785b-115">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="1785b-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="1785b-116">Debug</span><span class="sxs-lookup"><span data-stu-id="1785b-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="1785b-117">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="1785b-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
