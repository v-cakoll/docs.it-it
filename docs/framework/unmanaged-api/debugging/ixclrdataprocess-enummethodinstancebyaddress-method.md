---
title: Metodo IXCLRDataProcess::EnumMethodInstanceByAddress
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
ms.openlocfilehash: a51c709b0b331127b74d98c4dc42e2772fd7f2db
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166439"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="39551-102">Metodo IXCLRDataProcess::EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="39551-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="39551-103">Enumera le istanze di metodo di questo processo iniziando in corrispondenza di un offset di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="39551-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="39551-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39551-104">Syntax</span></span>

```
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="39551-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="39551-105">Parameters</span></span>

`handle`\
<span data-ttu-id="39551-106">[in] Handle per l'enumerazione delle istanze di metodo.</span><span class="sxs-lookup"><span data-stu-id="39551-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="39551-107">[out] L'istanza del metodo enumerate.</span><span class="sxs-lookup"><span data-stu-id="39551-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="39551-108">Note</span><span class="sxs-lookup"><span data-stu-id="39551-108">Remarks</span></span>

<span data-ttu-id="39551-109">Il metodo specificato fa parte di `IXCLRDataProcess` interfaccia e corrisponde al 28 slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="39551-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="39551-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39551-110">Requirements</span></span>

<span data-ttu-id="39551-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39551-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="39551-112">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="39551-112">**Header:** None</span></span>   
<span data-ttu-id="39551-113">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="39551-113">**Library:** None</span></span>   
**<span data-ttu-id="39551-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="39551-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]   
 
## <a name="see-also"></a><span data-ttu-id="39551-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39551-115">See also</span></span>

- [<span data-ttu-id="39551-116">Enumerazione CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="39551-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="39551-117">Debug</span><span class="sxs-lookup"><span data-stu-id="39551-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="39551-118">Interfaccia IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="39551-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
