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
ms.openlocfilehash: 8757642db6c4375cf55d1f7288669c4c8a752a38
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790400"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="3e5da-102">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="3e5da-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="3e5da-103">Fornisce metodi per eseguire query sulle informazioni relative a un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="3e5da-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="3e5da-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3e5da-104">Methods</span></span>

| <span data-ttu-id="3e5da-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3e5da-105">Method</span></span>                                                                                                                                | <span data-ttu-id="3e5da-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e5da-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="3e5da-107">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="3e5da-107">GetMethodDefinitionByToken</span></span>](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="3e5da-108">Ottiene la definizione del metodo corrispondente a un token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="3e5da-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="3e5da-109">Richiesta</span><span class="sxs-lookup"><span data-stu-id="3e5da-109">Request</span></span>](ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="3e5da-110">Richieste per popolare il buffer fornito con i dati del modulo.</span><span class="sxs-lookup"><span data-stu-id="3e5da-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="3e5da-111">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="3e5da-111">GetVersionId</span></span>](ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="3e5da-112">Ottiene l'ID versione del modulo.</span><span class="sxs-lookup"><span data-stu-id="3e5da-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="3e5da-113">Note</span><span class="sxs-lookup"><span data-stu-id="3e5da-113">Remarks</span></span>

<span data-ttu-id="3e5da-114">Questa interfaccia si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="3e5da-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="3e5da-115">Tuttavia, si tratta di un'interfaccia COM che deriva da `IUnknown` con GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` che possono essere ottenuti tramite i normali meccanismi COM.</span><span class="sxs-lookup"><span data-stu-id="3e5da-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="3e5da-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3e5da-116">Requirements</span></span>

<span data-ttu-id="3e5da-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e5da-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3e5da-118">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="3e5da-118">**Header:** None</span></span>  
<span data-ttu-id="3e5da-119">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="3e5da-119">**Library:** None</span></span>  
<span data-ttu-id="3e5da-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3e5da-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3e5da-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e5da-121">See also</span></span>

- [<span data-ttu-id="3e5da-122">Debug</span><span class="sxs-lookup"><span data-stu-id="3e5da-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="3e5da-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3e5da-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
