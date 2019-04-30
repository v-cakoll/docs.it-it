---
title: Metodo ICorDebugModule::EnableJITDebugging
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 642c4fd600d10ef89a08aa32bef5c8e7455552c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937176"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="427a3-102">Metodo ICorDebugModule::EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="427a3-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="427a3-103">Controlla se il compilatore JIT just-in-time mantiene le informazioni di debug per i metodi all'interno del modulo.</span><span class="sxs-lookup"><span data-stu-id="427a3-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="427a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="427a3-104">Syntax</span></span>  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="427a3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="427a3-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="427a3-106">[in] Impostare questo valore su `true` per consentire al compilatore JIT conservare le informazioni di mapping tra la versione di Microsoft intermediate language (MSIL) e la versione di ogni metodo in questo modulo compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="427a3-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="427a3-107">[in] Impostare questo valore su `true` per consentire al compilatore JIT generare il codice con alcune ottimizzazioni JIT specifiche per il debug.</span><span class="sxs-lookup"><span data-stu-id="427a3-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="427a3-108">Note</span><span class="sxs-lookup"><span data-stu-id="427a3-108">Remarks</span></span>  
 <span data-ttu-id="427a3-109">Debug JIT è abilitato per impostazione predefinita per tutti i moduli che vengono caricati quando il debugger è attivo.</span><span class="sxs-lookup"><span data-stu-id="427a3-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="427a3-110">A livello di programmazione abilitando o disabilitando le impostazioni di override delle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="427a3-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="427a3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="427a3-111">Requirements</span></span>  
 <span data-ttu-id="427a3-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="427a3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="427a3-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="427a3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="427a3-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="427a3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="427a3-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="427a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
