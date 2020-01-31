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
ms.openlocfilehash: 015735e1c6c3b6c146f2fca3a9bdc28baeca2f92
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792513"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="ab04e-102">Metodo ICorDebugProcess2::GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="ab04e-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="ab04e-103">Ottiene le impostazioni correnti del flag del compilatore utilizzate dal Common Language Runtime (CLR) per selezionare l'immagine precompilata (ovvero nativa) corretta da caricare in questo processo.</span><span class="sxs-lookup"><span data-stu-id="ab04e-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab04e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab04e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab04e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ab04e-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="ab04e-106">out Puntatore a una combinazione bit per bit dei valori di enumerazione [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) usati per selezionare l'immagine precompilata corretta da caricare.</span><span class="sxs-lookup"><span data-stu-id="ab04e-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab04e-107">Note</span><span class="sxs-lookup"><span data-stu-id="ab04e-107">Remarks</span></span>  
 <span data-ttu-id="ab04e-108">Utilizzare il metodo [ICorDebugProcess2:: SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) per impostare i flag che CLR utilizzerà per selezionare l'immagine precompilata corretta da caricare.</span><span class="sxs-lookup"><span data-stu-id="ab04e-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab04e-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ab04e-109">Requirements</span></span>  
 <span data-ttu-id="ab04e-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab04e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab04e-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab04e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab04e-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab04e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab04e-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab04e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
