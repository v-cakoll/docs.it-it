---
title: Interfaccia IXCLRDataMethodInstance
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 0b1c982b25af9edea76a038b4314b4bd608f07df
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420890"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="49e2a-102">Interfaccia IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="49e2a-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="49e2a-103">Fornisce metodi per l'esecuzione di query sulle informazioni relative a un'istanza di metodo.</span><span class="sxs-lookup"><span data-stu-id="49e2a-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="49e2a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="49e2a-104">Methods</span></span>

| <span data-ttu-id="49e2a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="49e2a-105">Method</span></span>                                                                                                                  | <span data-ttu-id="49e2a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49e2a-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="49e2a-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="49e2a-107">GetILAddressMap</span></span>](ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="49e2a-108">Ottiene l'oggetto per l'indirizzamento delle informazioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="49e2a-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="49e2a-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="49e2a-109">GetRepresentativeEntryAddress</span></span>](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="49e2a-110">Ottiene l'indirizzo del punto di ingresso più rappresentativo per la compilazione nativa di tutti i punti di ingresso possibili per un metodo.</span><span class="sxs-lookup"><span data-stu-id="49e2a-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="49e2a-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="49e2a-111">Remarks</span></span>

<span data-ttu-id="49e2a-112">Questa interfaccia si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="49e2a-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="49e2a-113">Tuttavia, si tratta di un'interfaccia COM che deriva da `IUnknown` con GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` che è possibile ottenere tramite i normali meccanismi com.</span><span class="sxs-lookup"><span data-stu-id="49e2a-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="49e2a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49e2a-114">Requirements</span></span>

<span data-ttu-id="49e2a-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49e2a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="49e2a-116">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="49e2a-116">**Header:** None</span></span>  
<span data-ttu-id="49e2a-117">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="49e2a-117">**Library:** None</span></span>  
<span data-ttu-id="49e2a-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="49e2a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="49e2a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49e2a-119">See also</span></span>

- [<span data-ttu-id="49e2a-120">Debug</span><span class="sxs-lookup"><span data-stu-id="49e2a-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="49e2a-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="49e2a-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
