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
ms.openlocfilehash: 6850dc256a70e0c0343104b3904e9eda62d11e7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179205"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="208e9-102">Metodo DacpGetModuleAddress::Request</span><span class="sxs-lookup"><span data-stu-id="208e9-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="208e9-103">Esegue una richiesta per popolare la struttura dalla struttura di runtime specificata.</span><span class="sxs-lookup"><span data-stu-id="208e9-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="208e9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="208e9-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="208e9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="208e9-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="208e9-106">[in] Puntatore al modulo dati di serie.</span><span class="sxs-lookup"><span data-stu-id="208e9-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="208e9-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="208e9-107">Remarks</span></span>

<span data-ttu-id="208e9-108">Questa struttura si trova all'interno del runtime e non viene esposta tramite intestazioni o file di libreria.</span><span class="sxs-lookup"><span data-stu-id="208e9-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="208e9-109">Per usarlo, il modo più semplice è quello di imitare l'implementazione:</span><span class="sxs-lookup"><span data-stu-id="208e9-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="208e9-110">Restituire il valore ottenuto chiamando il `Request` metodo sul `IXCLRDataModule*` parametro con i seguenti parametri:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="208e9-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="208e9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="208e9-111">Requirements</span></span>

<span data-ttu-id="208e9-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="208e9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="208e9-113">**Intestazione:** **Nessuna libreria:** Nessuna</span><span class="sxs-lookup"><span data-stu-id="208e9-113">**Header:** None **Library:** None</span></span>  
<span data-ttu-id="208e9-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="208e9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="208e9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="208e9-115">See also</span></span>

- [<span data-ttu-id="208e9-116">Debug</span><span class="sxs-lookup"><span data-stu-id="208e9-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="208e9-117">Interfaccia DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="208e9-117">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)
