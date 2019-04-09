---
title: Metodo DacpGetModuleAddress::Request
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 298620092c37b2c02332e9135f73584272e326bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111683"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="08d5c-102">Metodo DacpGetModuleAddress::Request</span><span class="sxs-lookup"><span data-stu-id="08d5c-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="08d5c-103">Esegue una richiesta per popolare la struttura della struttura di runtime specificato.</span><span class="sxs-lookup"><span data-stu-id="08d5c-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="08d5c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08d5c-104">Syntax</span></span>

```
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="08d5c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="08d5c-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="08d5c-106">[in] Puntatore al modulo del valore di inizializzazione di dati.</span><span class="sxs-lookup"><span data-stu-id="08d5c-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="08d5c-107">Note</span><span class="sxs-lookup"><span data-stu-id="08d5c-107">Remarks</span></span>

<span data-ttu-id="08d5c-108">Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="08d5c-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="08d5c-109">Per utilizzarlo, il modo più semplice è simulare l'implementazione:</span><span class="sxs-lookup"><span data-stu-id="08d5c-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="08d5c-110">Restituisce il valore ottenuto dalla chiamata di `Request` metodo sul `IXCLRDataModule*` parametro con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="08d5c-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters:</span></span> `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a><span data-ttu-id="08d5c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08d5c-111">Requirements</span></span>

<span data-ttu-id="08d5c-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08d5c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="08d5c-113">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="08d5c-113">**Header:** None</span></span>     
<span data-ttu-id="08d5c-114">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="08d5c-114">**Library:** None</span></span>  
**<span data-ttu-id="08d5c-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="08d5c-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="08d5c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08d5c-116">See also</span></span>

- [<span data-ttu-id="08d5c-117">Debug</span><span class="sxs-lookup"><span data-stu-id="08d5c-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="08d5c-118">DacpGetModuleAddress Interface</span><span class="sxs-lookup"><span data-stu-id="08d5c-118">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)