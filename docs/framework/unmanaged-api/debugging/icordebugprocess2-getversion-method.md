---
title: Metodo ICorDebugProcess2::GetVersion
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 interface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
ms.openlocfilehash: 391b848d3b3f66f6af6bf3adbefb6e94d526e748
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213504"
---
# <a name="icordebugprocess2getversion-method"></a><span data-ttu-id="42a5f-102">Metodo ICorDebugProcess2::GetVersion</span><span class="sxs-lookup"><span data-stu-id="42a5f-102">ICorDebugProcess2::GetVersion Method</span></span>

<span data-ttu-id="42a5f-103">Ottiene il numero di versione del Common Language Runtime (CLR) in esecuzione in questo processo.</span><span class="sxs-lookup"><span data-stu-id="42a5f-103">Gets the version number of the common language runtime (CLR) that is running in this process.</span></span>

## <a name="syntax"></a><span data-ttu-id="42a5f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42a5f-104">Syntax</span></span>

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a><span data-ttu-id="42a5f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="42a5f-105">Parameters</span></span>

`version`\
<span data-ttu-id="42a5f-106">out Puntatore a una struttura COR_VERSION che archivia il numero di versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="42a5f-106">[out] A pointer to a COR_VERSION structure that stores the version number of the runtime.</span></span>

## <a name="remarks"></a><span data-ttu-id="42a5f-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="42a5f-107">Remarks</span></span>

<span data-ttu-id="42a5f-108">Il `GetVersion` metodo restituisce un codice di errore se nessun Runtime è stato caricato nel processo.</span><span class="sxs-lookup"><span data-stu-id="42a5f-108">The `GetVersion` method returns an error code if no runtime has been loaded in the process.</span></span>

## <a name="requirements"></a><span data-ttu-id="42a5f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42a5f-109">Requirements</span></span>

<span data-ttu-id="42a5f-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42a5f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="42a5f-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42a5f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="42a5f-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42a5f-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="42a5f-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42a5f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
