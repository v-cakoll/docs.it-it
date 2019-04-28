---
title: Interfaccia IXCLRDataMethodDefinition
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4b1e8cb1cf34bb1c5ade1353351aab953e2b734a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670105"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="79685-102">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="79685-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="79685-103">Fornisce metodi per l'esecuzione di query informazioni sulla definizione di un metodo.</span><span class="sxs-lookup"><span data-stu-id="79685-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="79685-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="79685-104">Methods</span></span>

<span data-ttu-id="79685-105">I metodi seguenti sono alcuni dei metodi disponibili nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="79685-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="79685-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="79685-106">Method</span></span>                                                                                                                          | <span data-ttu-id="79685-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="79685-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="79685-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="79685-108">StartEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="79685-109">Fornisce un handle per l'enumerazione delle istanze di metodo per un determinato `IXCLRDataAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="79685-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="79685-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="79685-110">EnumInstance</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="79685-111">Enumera le istanze di questa definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="79685-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="79685-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="79685-112">EndEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="79685-113">Rilascia le risorse usate dagli iteratori interni utilizzati durante l'enumerazione di istanza.</span><span class="sxs-lookup"><span data-stu-id="79685-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="79685-114">Note</span><span class="sxs-lookup"><span data-stu-id="79685-114">Remarks</span></span>

<span data-ttu-id="79685-115">Questa interfaccia si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="79685-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="79685-116">Tuttavia, è un'interfaccia COM che deriva da `IUnknown` con GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` che può essere ottenuto tramite i normali meccanismi di COM.</span><span class="sxs-lookup"><span data-stu-id="79685-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="79685-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79685-117">Requirements</span></span>

<span data-ttu-id="79685-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79685-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="79685-119">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="79685-119">**Header:** None</span></span>  
<span data-ttu-id="79685-120">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="79685-120">**Library:** None</span></span>  
<span data-ttu-id="79685-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="79685-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="79685-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79685-122">See also</span></span>

- [<span data-ttu-id="79685-123">Debug</span><span class="sxs-lookup"><span data-stu-id="79685-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="79685-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="79685-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
