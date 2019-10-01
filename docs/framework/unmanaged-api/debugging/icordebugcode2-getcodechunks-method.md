---
title: Metodo ICorDebugCode2::GetCodeChunks
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1bdaf6391ca5c19f073708d6258ad5775bec9824
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700733"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="6ecfe-102">Metodo ICorDebugCode2::GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="6ecfe-102">ICorDebugCode2::GetCodeChunks Method</span></span>

<span data-ttu-id="6ecfe-103">Ottiene i blocchi di codice di cui questo oggetto di codice è composto.</span><span class="sxs-lookup"><span data-stu-id="6ecfe-103">Gets the chunks of code that this code object is composed of.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ecfe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ecfe-104">Syntax</span></span>

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a><span data-ttu-id="6ecfe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ecfe-105">Parameters</span></span>

 `cbufSize`  
 <span data-ttu-id="6ecfe-106">in Dimensione della matrice `chunks`.</span><span class="sxs-lookup"><span data-stu-id="6ecfe-106">[in] Size of the `chunks` array.</span></span>

 `pcnumChunks`  
 <span data-ttu-id="6ecfe-107">out Numero di blocchi restituiti nella matrice `chunks`.</span><span class="sxs-lookup"><span data-stu-id="6ecfe-107">[out] The number of chunks returned in the `chunks` array.</span></span>

 `chunks`  
 <span data-ttu-id="6ecfe-108">out Matrice di strutture "CodeChunkInfo", ognuna delle quali rappresenta un singolo blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="6ecfe-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="6ecfe-109">Se il valore di `cbufSize` è 0, questo parametro può essere null.</span><span class="sxs-lookup"><span data-stu-id="6ecfe-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ecfe-110">Note</span><span class="sxs-lookup"><span data-stu-id="6ecfe-110">Remarks</span></span>

 <span data-ttu-id="6ecfe-111">I blocchi di codice non si sovrappongono mai e seguiranno l'ordine in cui sono stati concatenati da [ICorDebugCode:: GetCode](icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="6ecfe-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="6ecfe-112">Un oggetto di codice MSIL (Microsoft Intermediate Language) in .NET Framework versione 2,0 costituirà un singolo blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="6ecfe-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>

## <a name="requirements"></a><span data-ttu-id="6ecfe-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ecfe-113">Requirements</span></span>

 <span data-ttu-id="6ecfe-114">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ecfe-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="6ecfe-115">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="6ecfe-115">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="6ecfe-116">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ecfe-116">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="6ecfe-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ecfe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
 
