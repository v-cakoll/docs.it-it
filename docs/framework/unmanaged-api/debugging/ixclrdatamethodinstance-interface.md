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
ms.openlocfilehash: f62cbdc4b3e73f0c27492f7ed20b35378654d399
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775499"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="5fe00-102">Interfaccia IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="5fe00-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="5fe00-103">Fornisce metodi per la ricerca delle informazioni relative a un'istanza di metodo.</span><span class="sxs-lookup"><span data-stu-id="5fe00-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="5fe00-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5fe00-104">Methods</span></span>

| <span data-ttu-id="5fe00-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5fe00-105">Method</span></span>                                                                                                                  | <span data-ttu-id="5fe00-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5fe00-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="5fe00-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="5fe00-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="5fe00-108">Ottiene il livello di integrità per le informazioni di mapping di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="5fe00-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="5fe00-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="5fe00-109">GetRepresentativeEntryAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="5fe00-110">Ottiene l'indirizzo del punto di ingresso più significativo per la compilazione nativa di tutti i punti di ingresso possibili per un metodo.</span><span class="sxs-lookup"><span data-stu-id="5fe00-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="5fe00-111">Note</span><span class="sxs-lookup"><span data-stu-id="5fe00-111">Remarks</span></span>

<span data-ttu-id="5fe00-112">Questa interfaccia si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="5fe00-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="5fe00-113">Tuttavia, è un'interfaccia COM che deriva da `IUnknown` con GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` che può essere ottenuto tramite i normali meccanismi di COM.</span><span class="sxs-lookup"><span data-stu-id="5fe00-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="5fe00-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5fe00-114">Requirements</span></span>

<span data-ttu-id="5fe00-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fe00-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5fe00-116">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="5fe00-116">**Header:** None</span></span>  
<span data-ttu-id="5fe00-117">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="5fe00-117">**Library:** None</span></span>  
<span data-ttu-id="5fe00-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5fe00-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5fe00-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fe00-119">See also</span></span>

- [<span data-ttu-id="5fe00-120">Debug</span><span class="sxs-lookup"><span data-stu-id="5fe00-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="5fe00-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5fe00-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
