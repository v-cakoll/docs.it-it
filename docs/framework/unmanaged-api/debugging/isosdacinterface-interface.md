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
ms.openlocfilehash: 94349a3f7b18c8ce29bb3a71cb9d10ee4eac8036
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790471"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="ef346-102">Interfaccia ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="ef346-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="ef346-103">Fornisce metodi helper per accedere ai dati da `SOS`.</span><span class="sxs-lookup"><span data-stu-id="ef346-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="ef346-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ef346-104">Methods</span></span>

| <span data-ttu-id="ef346-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ef346-105">Method</span></span>                                                                                                               | <span data-ttu-id="ef346-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef346-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="ef346-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="ef346-107">GetMethodDescData</span></span>](isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="ef346-108">Ottiene i dati per il puntatore MethodDesc specificato.</span><span class="sxs-lookup"><span data-stu-id="ef346-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="ef346-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="ef346-109">GetMethodDescPtrFromIP</span></span>](isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="ef346-110">Recupera il puntatore di MethodDesc corrispondente al metodo che contiene l'indirizzo di istruzione nativo specificato.</span><span class="sxs-lookup"><span data-stu-id="ef346-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="ef346-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="ef346-111">GetModuleData</span></span>](isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="ef346-112">Recupera i dati corrispondenti al modulo caricato a un indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="ef346-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ef346-113">Note</span><span class="sxs-lookup"><span data-stu-id="ef346-113">Remarks</span></span>

<span data-ttu-id="ef346-114">Questa interfaccia si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="ef346-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ef346-115">Tuttavia, si tratta di un'interfaccia COM che deriva da `IUnknown` con GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` che possono essere ottenuti tramite i normali meccanismi COM.</span><span class="sxs-lookup"><span data-stu-id="ef346-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="ef346-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ef346-116">Requirements</span></span>

<span data-ttu-id="ef346-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef346-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ef346-118">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="ef346-118">**Header:** None</span></span>  
<span data-ttu-id="ef346-119">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="ef346-119">**Library:** None</span></span>  
<span data-ttu-id="ef346-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ef346-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ef346-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef346-121">See also</span></span>

- [<span data-ttu-id="ef346-122">Debug</span><span class="sxs-lookup"><span data-stu-id="ef346-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="ef346-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ef346-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
