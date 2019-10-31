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
ms.openlocfilehash: e419ebb6ffd404368baf32e591e08c4a70645127
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121114"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="dabde-102">Metodo ICorDebugCode2::GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="dabde-102">ICorDebugCode2::GetCodeChunks Method</span></span>

<span data-ttu-id="dabde-103">Ottiene i blocchi di codice di cui questo oggetto di codice è composto.</span><span class="sxs-lookup"><span data-stu-id="dabde-103">Gets the chunks of code that this code object is composed of.</span></span>

## <a name="syntax"></a><span data-ttu-id="dabde-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dabde-104">Syntax</span></span>

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a><span data-ttu-id="dabde-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dabde-105">Parameters</span></span>

`cbufSize`  
<span data-ttu-id="dabde-106">in Dimensioni della matrice di `chunks`.</span><span class="sxs-lookup"><span data-stu-id="dabde-106">[in] Size of the `chunks` array.</span></span>

`pcnumChunks`  
<span data-ttu-id="dabde-107">out Numero di blocchi restituiti nella matrice `chunks`.</span><span class="sxs-lookup"><span data-stu-id="dabde-107">[out] The number of chunks returned in the `chunks` array.</span></span>

`chunks`  
<span data-ttu-id="dabde-108">out Matrice di strutture "CodeChunkInfo", ognuna delle quali rappresenta un singolo blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="dabde-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="dabde-109">Se il valore di `cbufSize` è 0, questo parametro può essere null.</span><span class="sxs-lookup"><span data-stu-id="dabde-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>

## <a name="remarks"></a><span data-ttu-id="dabde-110">Note</span><span class="sxs-lookup"><span data-stu-id="dabde-110">Remarks</span></span>

<span data-ttu-id="dabde-111">I blocchi di codice non si sovrappongono mai e seguiranno l'ordine in cui sono stati concatenati da [ICorDebugCode:: GetCode](icordebugcode-getcode-method.md).</span><span class="sxs-lookup"><span data-stu-id="dabde-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="dabde-112">Un oggetto di codice MSIL (Microsoft Intermediate Language) in .NET Framework versione 2,0 costituirà un singolo blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="dabde-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>

## <a name="requirements"></a><span data-ttu-id="dabde-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dabde-113">Requirements</span></span>

<span data-ttu-id="dabde-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dabde-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="dabde-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dabde-115">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="dabde-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dabde-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="dabde-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dabde-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
