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
ms.openlocfilehash: 07ad83da2bc608e3c5925664a68eec4a548860e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739224"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="86366-102">Metodo DacpGetModuleAddress::Request</span><span class="sxs-lookup"><span data-stu-id="86366-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="86366-103">Esegue una richiesta per popolare la struttura della struttura di runtime specificato.</span><span class="sxs-lookup"><span data-stu-id="86366-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="86366-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86366-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="86366-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="86366-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="86366-106">[in] Puntatore al modulo del valore di inizializzazione di dati.</span><span class="sxs-lookup"><span data-stu-id="86366-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="86366-107">Note</span><span class="sxs-lookup"><span data-stu-id="86366-107">Remarks</span></span>

<span data-ttu-id="86366-108">Questa struttura si trova all'interno del runtime e non viene esposto tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="86366-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="86366-109">Per utilizzarlo, il modo più semplice è simulare l'implementazione:</span><span class="sxs-lookup"><span data-stu-id="86366-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="86366-110">Restituisce il valore ottenuto dalla chiamata di `Request` metodo sul `IXCLRDataModule*` parametro con i parametri seguenti: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="86366-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="86366-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86366-111">Requirements</span></span>

<span data-ttu-id="86366-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86366-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="86366-113">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="86366-113">**Header:** None</span></span>     
<span data-ttu-id="86366-114">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="86366-114">**Library:** None</span></span>  
<span data-ttu-id="86366-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="86366-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="86366-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86366-116">See also</span></span>

- [<span data-ttu-id="86366-117">Debug</span><span class="sxs-lookup"><span data-stu-id="86366-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="86366-118">Interfaccia DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="86366-118">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)
