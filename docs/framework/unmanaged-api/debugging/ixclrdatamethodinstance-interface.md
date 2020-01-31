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
ms.openlocfilehash: c51825433bbc86c897c097475d5c15c855f6ec8b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790414"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="eae34-102">Interfaccia IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="eae34-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="eae34-103">Fornisce metodi per l'esecuzione di query sulle informazioni relative a un'istanza di metodo.</span><span class="sxs-lookup"><span data-stu-id="eae34-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="eae34-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="eae34-104">Methods</span></span>

| <span data-ttu-id="eae34-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="eae34-105">Method</span></span>                                                                                                                  | <span data-ttu-id="eae34-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eae34-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="eae34-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="eae34-107">GetILAddressMap</span></span>](ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="eae34-108">Ottiene l'oggetto per l'indirizzamento delle informazioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="eae34-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="eae34-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="eae34-109">GetRepresentativeEntryAddress</span></span>](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="eae34-110">Ottiene l'indirizzo del punto di ingresso più rappresentativo per la compilazione nativa di tutti i punti di ingresso possibili per un metodo.</span><span class="sxs-lookup"><span data-stu-id="eae34-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method.</span></span> |

## <a name="remarks"></a><span data-ttu-id="eae34-111">Note</span><span class="sxs-lookup"><span data-stu-id="eae34-111">Remarks</span></span>

<span data-ttu-id="eae34-112">Questa interfaccia si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="eae34-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="eae34-113">Tuttavia, si tratta di un'interfaccia COM che deriva da `IUnknown` con GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` che possono essere ottenuti tramite i normali meccanismi COM.</span><span class="sxs-lookup"><span data-stu-id="eae34-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="eae34-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="eae34-114">Requirements</span></span>

<span data-ttu-id="eae34-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eae34-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="eae34-116">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="eae34-116">**Header:** None</span></span>  
<span data-ttu-id="eae34-117">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="eae34-117">**Library:** None</span></span>  
<span data-ttu-id="eae34-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="eae34-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="eae34-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eae34-119">See also</span></span>

- [<span data-ttu-id="eae34-120">Debug</span><span class="sxs-lookup"><span data-stu-id="eae34-120">Debugging</span></span>](index.md)
- [<span data-ttu-id="eae34-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="eae34-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
