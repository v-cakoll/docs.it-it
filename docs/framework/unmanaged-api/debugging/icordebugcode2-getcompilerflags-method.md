---
title: Metodo ICorDebugCode2::GetCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
ms.openlocfilehash: 4ad1fb1bcb43dda9796b54cbf868f89c001995da
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777895"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="be2bb-102">Metodo ICorDebugCode2::GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="be2bb-102">ICorDebugCode2::GetCompilerFlags Method</span></span>

<span data-ttu-id="be2bb-103">Ottiene i flag che specificano le condizioni in base alle quali l'oggetto di codice è stato compilato o generato JIT usando il generatore di immagini native (Ngen. exe).</span><span class="sxs-lookup"><span data-stu-id="be2bb-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>

## <a name="syntax"></a><span data-ttu-id="be2bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be2bb-104">Syntax</span></span>

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a><span data-ttu-id="be2bb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="be2bb-105">Parameters</span></span>

`pdwFlags`  
<span data-ttu-id="be2bb-106">out Puntatore a un valore dell'enumerazione [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) che specifica il comportamento del compilatore JIT o del generatore di immagini native.</span><span class="sxs-lookup"><span data-stu-id="be2bb-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>

## <a name="requirements"></a><span data-ttu-id="be2bb-107">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="be2bb-107">Requirements</span></span>

<span data-ttu-id="be2bb-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be2bb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="be2bb-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be2bb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="be2bb-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be2bb-110">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="be2bb-111">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be2bb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
