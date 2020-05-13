---
title: Metodo ICorDebugProcess2::GetDesiredNGENCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
ms.openlocfilehash: d2e54f0b16300673409eb2f5757338dfa3011e61
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212997"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="34368-102">Metodo ICorDebugProcess2::GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="34368-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="34368-103">Ottiene le impostazioni correnti del flag del compilatore utilizzate dal Common Language Runtime (CLR) per selezionare l'immagine precompilata (ovvero nativa) corretta da caricare in questo processo.</span><span class="sxs-lookup"><span data-stu-id="34368-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34368-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34368-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34368-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="34368-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="34368-106">out Puntatore a una combinazione bit per bit dei valori di enumerazione [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) usati per selezionare l'immagine precompilata corretta da caricare.</span><span class="sxs-lookup"><span data-stu-id="34368-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34368-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="34368-107">Remarks</span></span>  
 <span data-ttu-id="34368-108">Utilizzare il metodo [ICorDebugProcess2:: SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) per impostare i flag che CLR utilizzerà per selezionare l'immagine precompilata corretta da caricare.</span><span class="sxs-lookup"><span data-stu-id="34368-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34368-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34368-109">Requirements</span></span>  
 <span data-ttu-id="34368-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34368-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34368-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34368-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34368-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34368-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34368-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34368-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
