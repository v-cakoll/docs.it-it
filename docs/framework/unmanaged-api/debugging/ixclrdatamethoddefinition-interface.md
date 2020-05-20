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
ms.openlocfilehash: ebb689eee4a89a70e81d8f9d958e7826c3b3421b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420955"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="46448-102">Interfaccia IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="46448-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="46448-103">Fornisce metodi per eseguire query sulle informazioni relative a una definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="46448-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="46448-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="46448-104">Methods</span></span>

<span data-ttu-id="46448-105">Di seguito sono riportati alcuni dei metodi disponibili nell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="46448-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="46448-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="46448-106">Method</span></span>                                                                                                                          | <span data-ttu-id="46448-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46448-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="46448-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="46448-108">StartEnumInstances</span></span>](ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="46448-109">Fornisce un handle per l'enumerazione delle istanze del metodo per un oggetto specificato `IXCLRDataAppDomain` .</span><span class="sxs-lookup"><span data-stu-id="46448-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="46448-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="46448-110">EnumInstance</span></span>](ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="46448-111">Enumera le istanze di questa definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="46448-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="46448-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="46448-112">EndEnumInstances</span></span>](ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="46448-113">Rilascia le risorse utilizzate dagli iteratori interni utilizzati durante l'enumerazione dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="46448-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="46448-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="46448-114">Remarks</span></span>

<span data-ttu-id="46448-115">Questa interfaccia si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="46448-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="46448-116">Tuttavia, si tratta di un'interfaccia COM che deriva da `IUnknown` con GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` che è possibile ottenere tramite i normali meccanismi com.</span><span class="sxs-lookup"><span data-stu-id="46448-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="46448-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="46448-117">Requirements</span></span>

<span data-ttu-id="46448-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46448-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="46448-119">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="46448-119">**Header:** None</span></span>  
<span data-ttu-id="46448-120">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="46448-120">**Library:** None</span></span>  
<span data-ttu-id="46448-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="46448-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="46448-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46448-122">See also</span></span>

- [<span data-ttu-id="46448-123">Debug</span><span class="sxs-lookup"><span data-stu-id="46448-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="46448-124">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="46448-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
