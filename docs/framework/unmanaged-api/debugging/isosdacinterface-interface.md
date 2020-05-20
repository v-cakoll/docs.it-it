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
ms.openlocfilehash: c9b4e6e5b36fe38b6c0ea78f6d1848d155008bcc
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420968"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="47b11-102">Interfaccia ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="47b11-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="47b11-103">Fornisce metodi helper per accedere ai dati da `SOS` .</span><span class="sxs-lookup"><span data-stu-id="47b11-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="47b11-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="47b11-104">Methods</span></span>

| <span data-ttu-id="47b11-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="47b11-105">Method</span></span>                                                                                                               | <span data-ttu-id="47b11-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47b11-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="47b11-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="47b11-107">GetMethodDescData</span></span>](isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="47b11-108">Ottiene i dati per il puntatore MethodDesc specificato.</span><span class="sxs-lookup"><span data-stu-id="47b11-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="47b11-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="47b11-109">GetMethodDescPtrFromIP</span></span>](isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="47b11-110">Recupera il puntatore di MethodDesc corrispondente al metodo che contiene l'indirizzo di istruzione nativo specificato.</span><span class="sxs-lookup"><span data-stu-id="47b11-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="47b11-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="47b11-111">GetModuleData</span></span>](isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="47b11-112">Recupera i dati corrispondenti al modulo caricato a un indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="47b11-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="47b11-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="47b11-113">Remarks</span></span>

<span data-ttu-id="47b11-114">Questa interfaccia si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="47b11-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="47b11-115">Tuttavia, si tratta di un'interfaccia COM che deriva da `IUnknown` con GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` che è possibile ottenere tramite i normali meccanismi com.</span><span class="sxs-lookup"><span data-stu-id="47b11-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="47b11-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47b11-116">Requirements</span></span>

<span data-ttu-id="47b11-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47b11-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="47b11-118">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="47b11-118">**Header:** None</span></span>  
<span data-ttu-id="47b11-119">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="47b11-119">**Library:** None</span></span>  
<span data-ttu-id="47b11-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="47b11-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="47b11-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47b11-121">See also</span></span>

- [<span data-ttu-id="47b11-122">Debug</span><span class="sxs-lookup"><span data-stu-id="47b11-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="47b11-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="47b11-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
