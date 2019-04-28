---
title: Interfaccia ISOSDacInterface
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ccaf479fc4fb90007b4999e95ee03bdd0529321e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922148"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="2cbda-102">Interfaccia ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="2cbda-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="2cbda-103">Fornisce metodi helper per accedere ai dati da `SOS`.</span><span class="sxs-lookup"><span data-stu-id="2cbda-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="2cbda-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="2cbda-104">Methods</span></span>

| <span data-ttu-id="2cbda-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2cbda-105">Method</span></span>                                                                                                               | <span data-ttu-id="2cbda-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2cbda-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="2cbda-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="2cbda-107">GetMethodDescData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="2cbda-108">Ottiene i dati per il puntatore MethodDesc specificato.</span><span class="sxs-lookup"><span data-stu-id="2cbda-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="2cbda-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="2cbda-109">GetMethodDescPtrFromIP</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="2cbda-110">Recupera il puntatore del MethodDesc corrispondente metodo contenente l'indirizzo dell'istruzione nativo specificato.</span><span class="sxs-lookup"><span data-stu-id="2cbda-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="2cbda-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="2cbda-111">GetModuleData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="2cbda-112">Recupera i dati corrispondenti al modulo caricato in un determinato indirizzo.</span><span class="sxs-lookup"><span data-stu-id="2cbda-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="2cbda-113">Note</span><span class="sxs-lookup"><span data-stu-id="2cbda-113">Remarks</span></span>

<span data-ttu-id="2cbda-114">Questa interfaccia si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="2cbda-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="2cbda-115">Tuttavia, è un'interfaccia COM che deriva da `IUnknown` con GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` che può essere ottenuto tramite i normali meccanismi di COM.</span><span class="sxs-lookup"><span data-stu-id="2cbda-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="2cbda-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2cbda-116">Requirements</span></span>

<span data-ttu-id="2cbda-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cbda-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="2cbda-118">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="2cbda-118">**Header:** None</span></span>  
<span data-ttu-id="2cbda-119">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="2cbda-119">**Library:** None</span></span>  
<span data-ttu-id="2cbda-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2cbda-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2cbda-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cbda-121">See also</span></span>

- [<span data-ttu-id="2cbda-122">Debug</span><span class="sxs-lookup"><span data-stu-id="2cbda-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="2cbda-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2cbda-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
