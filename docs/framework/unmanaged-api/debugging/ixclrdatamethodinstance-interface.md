---
title: Interfaccia IXCLRDataMethodInstance
ms.date: 01/16/2019
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
ms.openlocfilehash: 0eef69cea9f59911b5076f56579b0192be357431
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659111"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="87b13-102">Interfaccia IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="87b13-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="87b13-103">Fornisce metodi per la ricerca delle informazioni relative a un'istanza di metodo.</span><span class="sxs-lookup"><span data-stu-id="87b13-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="87b13-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="87b13-104">Methods</span></span>

| <span data-ttu-id="87b13-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="87b13-105">Method</span></span>                                                                                                                  | <span data-ttu-id="87b13-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87b13-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="87b13-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="87b13-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="87b13-108">Ottiene il livello di integrità per le informazioni di mapping di indirizzi.</span><span class="sxs-lookup"><span data-stu-id="87b13-108">Gets the IL to address mapping information.</span></span> |

## <a name="remarks"></a><span data-ttu-id="87b13-109">Note</span><span class="sxs-lookup"><span data-stu-id="87b13-109">Remarks</span></span>

<span data-ttu-id="87b13-110">Questa interfaccia si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="87b13-110">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="87b13-111">Tuttavia, è un'interfaccia COM che deriva da `IUnknown` con GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` che può essere ottenuto tramite i normali meccanismi di COM.</span><span class="sxs-lookup"><span data-stu-id="87b13-111">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="87b13-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87b13-112">Requirements</span></span>

<span data-ttu-id="87b13-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87b13-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="87b13-114">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="87b13-114">**Header:** None</span></span>  
<span data-ttu-id="87b13-115">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="87b13-115">**Library:** None</span></span>  
<span data-ttu-id="87b13-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="87b13-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="87b13-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87b13-117">See also</span></span>

- [<span data-ttu-id="87b13-118">Debug</span><span class="sxs-lookup"><span data-stu-id="87b13-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="87b13-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="87b13-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
