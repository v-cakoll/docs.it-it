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
ms.openlocfilehash: 4dbe6a2c295e5afae1b6761f0c7b695fdb906428
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102907"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="94d26-102">Metodo DacpGetModuleAddress::Request</span><span class="sxs-lookup"><span data-stu-id="94d26-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="94d26-103">Esegue una richiesta per popolare la struttura dalla struttura di runtime specificata.</span><span class="sxs-lookup"><span data-stu-id="94d26-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="94d26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94d26-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="94d26-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="94d26-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="94d26-106">[in] Puntatore al modulo dati di serie.</span><span class="sxs-lookup"><span data-stu-id="94d26-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="94d26-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="94d26-107">Remarks</span></span>

<span data-ttu-id="94d26-108">Questa struttura si trova all'interno del runtime e non viene esposta tramite intestazioni o file di libreria.</span><span class="sxs-lookup"><span data-stu-id="94d26-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="94d26-109">Per usarlo, il modo più semplice è quello di imitare l'implementazione:</span><span class="sxs-lookup"><span data-stu-id="94d26-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="94d26-110">Restituire il valore ottenuto chiamando il `Request` metodo sul `IXCLRDataModule*` parametro con i seguenti parametri:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="94d26-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="94d26-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94d26-111">Requirements</span></span>

<span data-ttu-id="94d26-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="94d26-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md)</span></span>\
<span data-ttu-id="94d26-113">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="94d26-113">**Header:** None\</span></span>
<span data-ttu-id="94d26-114">**Biblioteca:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="94d26-114">**Library:** None\</span></span>
<span data-ttu-id="94d26-115">Versioni di **.NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="94d26-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="94d26-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94d26-116">See also</span></span>

- [<span data-ttu-id="94d26-117">Debug</span><span class="sxs-lookup"><span data-stu-id="94d26-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="94d26-118">DacpGetModuleAddress (struttura)</span><span class="sxs-lookup"><span data-stu-id="94d26-118">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
