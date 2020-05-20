---
title: Interfaccia IXCLRDataProcess
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
ms.openlocfilehash: 6a6def8fc10f04b89aa8d8c735025b01f9b6ddfb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420760"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="6511c-102">Interfaccia IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="6511c-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="6511c-103">Fornisce metodi per l'esecuzione di query sulle informazioni relative a un processo.</span><span class="sxs-lookup"><span data-stu-id="6511c-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="6511c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6511c-104">Methods</span></span>

| <span data-ttu-id="6511c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6511c-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="6511c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6511c-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="6511c-107">GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="6511c-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="6511c-108">Ottiene un oggetto `AppDomain` in un processo in base al relativo ID univoco.</span><span class="sxs-lookup"><span data-stu-id="6511c-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="6511c-109">StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="6511c-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="6511c-110">Fornisce un handle per enumerare i moduli di un processo.</span><span class="sxs-lookup"><span data-stu-id="6511c-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="6511c-111">EnumModule</span><span class="sxs-lookup"><span data-stu-id="6511c-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="6511c-112">Enumera i moduli di questo processo.</span><span class="sxs-lookup"><span data-stu-id="6511c-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="6511c-113">EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="6511c-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="6511c-114">Rilascia le risorse usate dagli iteratori interni usati durante l'enumerazione del modulo.</span><span class="sxs-lookup"><span data-stu-id="6511c-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="6511c-115">StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="6511c-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="6511c-116">Fornisce un handle per enumerare le istanze del metodo di a `AppDomain` partire da un indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="6511c-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="6511c-117">EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="6511c-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="6511c-118">Enumera le istanze del metodo di questo processo a partire da un offset di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="6511c-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="6511c-119">EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="6511c-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="6511c-120">Rilascia le risorse utilizzate dagli iteratori interni utilizzati durante l'enumerazione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="6511c-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="6511c-121">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6511c-121">Remarks</span></span>

<span data-ttu-id="6511c-122">Questa interfaccia si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="6511c-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="6511c-123">Tuttavia, si tratta di un'interfaccia COM che deriva da `IUnknown` con GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` che è possibile ottenere tramite i normali meccanismi com.</span><span class="sxs-lookup"><span data-stu-id="6511c-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="6511c-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6511c-124">Requirements</span></span>

<span data-ttu-id="6511c-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6511c-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="6511c-126">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="6511c-126">**Header:** None</span></span>  
<span data-ttu-id="6511c-127">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="6511c-127">**Library:** None</span></span>  
<span data-ttu-id="6511c-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6511c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6511c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6511c-129">See also</span></span>

- [<span data-ttu-id="6511c-130">Debug</span><span class="sxs-lookup"><span data-stu-id="6511c-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="6511c-131">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6511c-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
