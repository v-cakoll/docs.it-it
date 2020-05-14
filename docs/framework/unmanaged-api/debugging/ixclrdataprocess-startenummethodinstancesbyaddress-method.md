---
title: 'Metodo IXCLRDataProcess:: StartEnumMethodInstancesByAddress'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e28fa73300e147ac07a2d325fbf517480bb73797
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394941"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="67267-102">Metodo IXCLRDataProcess:: StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="67267-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="67267-103">Fornisce un handle per enumerare le istanze del metodo di a `AppDomain` partire da un indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="67267-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="67267-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67267-104">Syntax</span></span>

```cpp
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="67267-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="67267-105">Parameters</span></span>

`address`\
<span data-ttu-id="67267-106">in Indirizzo dell'istanza del primo metodo.</span><span class="sxs-lookup"><span data-stu-id="67267-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="67267-107">in AppDomain delle istanze del metodo.</span><span class="sxs-lookup"><span data-stu-id="67267-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="67267-108">out Handle per l'enumerazione delle istanze del metodo.</span><span class="sxs-lookup"><span data-stu-id="67267-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="67267-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="67267-109">Remarks</span></span>

<span data-ttu-id="67267-110">Il metodo fornito fa parte dell' `IXCLRDataProcess` interfaccia e corrisponde al ventottesimo slot della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="67267-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="67267-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67267-111">Requirements</span></span>

<span data-ttu-id="67267-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67267-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="67267-113">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="67267-113">**Header:** None</span></span>  
<span data-ttu-id="67267-114">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="67267-114">**Library:** None</span></span>  
<span data-ttu-id="67267-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="67267-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="67267-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="67267-116">See also</span></span>

- [<span data-ttu-id="67267-117">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="67267-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="67267-118">Debug</span><span class="sxs-lookup"><span data-stu-id="67267-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="67267-119">Interfaccia IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="67267-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
