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
ms.openlocfilehash: 3c2bc771c0a131329b9403c99a33ca7b79023771
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420851"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="550ca-102">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="550ca-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="550ca-103">Fornisce metodi per eseguire query sulle informazioni relative a un modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="550ca-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="550ca-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="550ca-104">Methods</span></span>

| <span data-ttu-id="550ca-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="550ca-105">Method</span></span>                                                                                                                                | <span data-ttu-id="550ca-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="550ca-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="550ca-107">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="550ca-107">GetMethodDefinitionByToken</span></span>](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="550ca-108">Ottiene la definizione del metodo corrispondente a un token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="550ca-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="550ca-109">Richiesta</span><span class="sxs-lookup"><span data-stu-id="550ca-109">Request</span></span>](ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="550ca-110">Richieste per popolare il buffer fornito con i dati del modulo.</span><span class="sxs-lookup"><span data-stu-id="550ca-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="550ca-111">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="550ca-111">GetVersionId</span></span>](ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="550ca-112">Ottiene l'ID versione del modulo.</span><span class="sxs-lookup"><span data-stu-id="550ca-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="550ca-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="550ca-113">Remarks</span></span>

<span data-ttu-id="550ca-114">Questa interfaccia si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="550ca-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="550ca-115">Tuttavia, si tratta di un'interfaccia COM che deriva da `IUnknown` con GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` che è possibile ottenere tramite i normali meccanismi com.</span><span class="sxs-lookup"><span data-stu-id="550ca-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="550ca-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="550ca-116">Requirements</span></span>

<span data-ttu-id="550ca-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="550ca-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="550ca-118">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="550ca-118">**Header:** None</span></span>  
<span data-ttu-id="550ca-119">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="550ca-119">**Library:** None</span></span>  
<span data-ttu-id="550ca-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="550ca-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="550ca-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="550ca-121">See also</span></span>

- [<span data-ttu-id="550ca-122">Debug</span><span class="sxs-lookup"><span data-stu-id="550ca-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="550ca-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="550ca-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
