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
ms.openlocfilehash: 1755526636bed6d78663112e4c2ad5ab7c3f731c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860846"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="0c5f2-102">Metodo DacpGetModuleAddress::Request</span><span class="sxs-lookup"><span data-stu-id="0c5f2-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="0c5f2-103">Esegue una richiesta per popolare la struttura dalla struttura di runtime specificata.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0c5f2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c5f2-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="0c5f2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c5f2-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="0c5f2-106">in Puntatore al modulo dati di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="0c5f2-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0c5f2-107">Remarks</span></span>

<span data-ttu-id="0c5f2-108">Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria.</span><span class="sxs-lookup"><span data-stu-id="0c5f2-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="0c5f2-109">Per usarlo, il modo più semplice consiste nel simulare l'implementazione:</span><span class="sxs-lookup"><span data-stu-id="0c5f2-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="0c5f2-110">Restituisce il valore ottenuto dalla chiamata al `Request` metodo sul `IXCLRDataModule*` parametro con i parametri seguenti:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="0c5f2-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="0c5f2-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c5f2-111">Requirements</span></span>

<span data-ttu-id="0c5f2-112">**Piattaforme:** Vedere i [requisiti di sistema](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="0c5f2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="0c5f2-113">**Intestazione:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="0c5f2-113">**Header:** None\</span></span>
<span data-ttu-id="0c5f2-114">**Libreria:** Nessuno</span><span class="sxs-lookup"><span data-stu-id="0c5f2-114">**Library:** None\</span></span>
<span data-ttu-id="0c5f2-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0c5f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0c5f2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c5f2-116">See also</span></span>

- [<span data-ttu-id="0c5f2-117">Debug</span><span class="sxs-lookup"><span data-stu-id="0c5f2-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="0c5f2-118">Struttura DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="0c5f2-118">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
