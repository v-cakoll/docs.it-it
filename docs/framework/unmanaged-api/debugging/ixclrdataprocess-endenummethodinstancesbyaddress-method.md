---
title: 'Metodo IXCLRDataProcess:: EndEnumMethodInstancesByAddress'
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
ms.openlocfilehash: 04ce8f44b0c9f532951666de7bfb9de475c14746
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395250"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="d7b03-102">Metodo IXCLRDataProcess:: EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="d7b03-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="d7b03-103">Rilascia le risorse utilizzate dagli iteratori interni utilizzati durante l'enumerazione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="d7b03-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d7b03-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7b03-104">Syntax</span></span>

```cpp
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="d7b03-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d7b03-105">Parameters</span></span>

`handle`\
<span data-ttu-id="d7b03-106">out Handle per l'enumerazione delle istanze del metodo.</span><span class="sxs-lookup"><span data-stu-id="d7b03-106">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="d7b03-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="d7b03-107">Remarks</span></span>

<span data-ttu-id="d7b03-108">Il metodo fornito fa parte dell' `IXCLRDataProcess` interfaccia e corrisponde al trentesimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="d7b03-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 30th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="d7b03-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7b03-109">Requirements</span></span>

<span data-ttu-id="d7b03-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7b03-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d7b03-111">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="d7b03-111">**Header:** None</span></span>  
<span data-ttu-id="d7b03-112">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="d7b03-112">**Library:** None</span></span>  
<span data-ttu-id="d7b03-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d7b03-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d7b03-114">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="d7b03-114">See also</span></span>

- [<span data-ttu-id="d7b03-115">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="d7b03-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="d7b03-116">Debug</span><span class="sxs-lookup"><span data-stu-id="d7b03-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="d7b03-117">Interfaccia IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="d7b03-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
