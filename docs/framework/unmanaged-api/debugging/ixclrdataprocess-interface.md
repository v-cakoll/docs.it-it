---
title: IXCLRDataProcess Interface
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ff74a7acb5cc84c177f083c19402cd78977aeab5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680374"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="97a21-102">IXCLRDataProcess Interface</span><span class="sxs-lookup"><span data-stu-id="97a21-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="97a21-103">Fornisce metodi per l'esecuzione di query informazioni sul processo.</span><span class="sxs-lookup"><span data-stu-id="97a21-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="97a21-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="97a21-104">Methods</span></span>

| <span data-ttu-id="97a21-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="97a21-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="97a21-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97a21-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="97a21-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="97a21-107">GetAppDomainByUniqueId</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="97a21-108">Ottiene un `AppDomain` in un processo tramite l'id univoco.</span><span class="sxs-lookup"><span data-stu-id="97a21-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="97a21-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="97a21-109">StartEnumModules</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="97a21-110">Fornisce un handle per enumerare i moduli di un processo.</span><span class="sxs-lookup"><span data-stu-id="97a21-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="97a21-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="97a21-111">EnumModule</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="97a21-112">Enumera i moduli di questo processo.</span><span class="sxs-lookup"><span data-stu-id="97a21-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="97a21-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="97a21-113">EndEnumModules</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="97a21-114">Rilascia le risorse usate dagli iteratori interni utilizzati durante l'enumerazione di modulo.</span><span class="sxs-lookup"><span data-stu-id="97a21-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="97a21-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="97a21-115">StartEnumMethodInstancesByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="97a21-116">Fornisce un handle per enumerare le istanze di metodo di `AppDomain` iniziando in corrispondenza di un determinato indirizzo.</span><span class="sxs-lookup"><span data-stu-id="97a21-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="97a21-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="97a21-117">EnumMethodInstanceByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="97a21-118">Enumera le istanze di metodo di questo processo iniziando in corrispondenza di un offset di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="97a21-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="97a21-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="97a21-119">EndEnumMethodInstancesByAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="97a21-120">Rilascia le risorse usate dagli iteratori interni utilizzati durante l'enumerazione di istanza.</span><span class="sxs-lookup"><span data-stu-id="97a21-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="97a21-121">Note</span><span class="sxs-lookup"><span data-stu-id="97a21-121">Remarks</span></span>

<span data-ttu-id="97a21-122">Questa interfaccia si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="97a21-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="97a21-123">Tuttavia, è un'interfaccia COM che deriva da `IUnknown` con GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` che può essere ottenuto tramite i normali meccanismi di COM.</span><span class="sxs-lookup"><span data-stu-id="97a21-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="97a21-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97a21-124">Requirements</span></span>

<span data-ttu-id="97a21-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97a21-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="97a21-126">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="97a21-126">**Header:** None</span></span>  
<span data-ttu-id="97a21-127">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="97a21-127">**Library:** None</span></span>  
<span data-ttu-id="97a21-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="97a21-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="97a21-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97a21-129">See also</span></span>

- [<span data-ttu-id="97a21-130">Debug</span><span class="sxs-lookup"><span data-stu-id="97a21-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="97a21-131">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="97a21-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
