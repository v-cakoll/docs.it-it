---
title: Interfaccia IXCLRDataModule
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c8d6e36687fd43bbc59304eee64dd42eb78101e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676523"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="6fae1-102">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="6fae1-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="6fae1-103">Fornisce metodi per la ricerca delle informazioni su un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="6fae1-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="6fae1-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6fae1-104">Methods</span></span>

| <span data-ttu-id="6fae1-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6fae1-105">Method</span></span>                                                                                                                                | <span data-ttu-id="6fae1-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6fae1-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="6fae1-107">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="6fae1-107">GetMethodDefinitionByToken</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="6fae1-108">Ottiene la definizione del metodo corrispondente a un token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="6fae1-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="6fae1-109">Richiesta</span><span class="sxs-lookup"><span data-stu-id="6fae1-109">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="6fae1-110">Richieste per popolare il buffer specificato con i dati del modulo.</span><span class="sxs-lookup"><span data-stu-id="6fae1-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="6fae1-111">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="6fae1-111">GetVersionId</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="6fae1-112">Ottiene l'ID della versione. del modulo</span><span class="sxs-lookup"><span data-stu-id="6fae1-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="6fae1-113">Note</span><span class="sxs-lookup"><span data-stu-id="6fae1-113">Remarks</span></span>

<span data-ttu-id="6fae1-114">Questa interfaccia si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="6fae1-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="6fae1-115">Tuttavia, è un'interfaccia COM che deriva da `IUnknown` con GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` che può essere ottenuto tramite i normali meccanismi di COM.</span><span class="sxs-lookup"><span data-stu-id="6fae1-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="6fae1-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6fae1-116">Requirements</span></span>

<span data-ttu-id="6fae1-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fae1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6fae1-118">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="6fae1-118">**Header:** None</span></span>  
<span data-ttu-id="6fae1-119">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="6fae1-119">**Library:** None</span></span>  
<span data-ttu-id="6fae1-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6fae1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6fae1-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fae1-121">See also</span></span>

- [<span data-ttu-id="6fae1-122">Debug</span><span class="sxs-lookup"><span data-stu-id="6fae1-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="6fae1-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6fae1-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
