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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77ffb53e3a2b3802d3fcc1319397c8f51c5b127c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416111"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="fdbb2-102">Metodo ICorDebugProcess2::GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="fdbb2-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="fdbb2-103">Ottiene il compilatore corrente impostazioni del flag utilizzato common language runtime (CLR) per selezionare precompilata corretto (vale a dire native) immagine deve essere caricata in questo processo.</span><span class="sxs-lookup"><span data-stu-id="fdbb2-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdbb2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fdbb2-104">Syntax</span></span>  
  
```  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fdbb2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fdbb2-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="fdbb2-106">[out] Un puntatore a una combinazione bit per bit del [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) valori di enumerazione che consentono di selezionare l'immagine corretta precompilata da caricare.</span><span class="sxs-lookup"><span data-stu-id="fdbb2-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdbb2-107">Note</span><span class="sxs-lookup"><span data-stu-id="fdbb2-107">Remarks</span></span>  
 <span data-ttu-id="fdbb2-108">Utilizzare il [ICorDebugProcess2:: SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) per impostare i flag che verrà utilizzata dal CLR per selezionare l'immagine corretta pre-compilata da caricare.</span><span class="sxs-lookup"><span data-stu-id="fdbb2-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdbb2-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fdbb2-109">Requirements</span></span>  
 <span data-ttu-id="fdbb2-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdbb2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdbb2-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="fdbb2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdbb2-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="fdbb2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdbb2-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdbb2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
