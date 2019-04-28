---
title: Metodo IXCLRDataProcess::StartEnumMethodInstancesByAddress
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
ms.openlocfilehash: 41b6ff0a3c44d3ad997c54b1c82590cc3583fe52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775232"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="ff152-102">Metodo IXCLRDataProcess::StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="ff152-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="ff152-103">Fornisce un handle per enumerare le istanze di metodo di `AppDomain` iniziando in corrispondenza di un determinato indirizzo.</span><span class="sxs-lookup"><span data-stu-id="ff152-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ff152-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff152-104">Syntax</span></span>

```
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

## <a name="parameters"></a><span data-ttu-id="ff152-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff152-105">Parameters</span></span>

`address`\
<span data-ttu-id="ff152-106">[in] L'indirizzo dell'istanza del primo metodo.</span><span class="sxs-lookup"><span data-stu-id="ff152-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="ff152-107">[in] Il dominio di applicazione delle istanze del metodo.</span><span class="sxs-lookup"><span data-stu-id="ff152-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="ff152-108">[out] Handle per l'enumerazione delle istanze di metodo.</span><span class="sxs-lookup"><span data-stu-id="ff152-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff152-109">Note</span><span class="sxs-lookup"><span data-stu-id="ff152-109">Remarks</span></span>

<span data-ttu-id="ff152-110">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 27 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="ff152-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 27th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ff152-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff152-111">Requirements</span></span>

<span data-ttu-id="ff152-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff152-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ff152-113">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="ff152-113">**Header:** None</span></span>  
<span data-ttu-id="ff152-114">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="ff152-114">**Library:** None</span></span>  
<span data-ttu-id="ff152-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ff152-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ff152-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff152-116">See also</span></span>

- [<span data-ttu-id="ff152-117">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="ff152-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="ff152-118">Debug</span><span class="sxs-lookup"><span data-stu-id="ff152-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="ff152-119">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="ff152-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
