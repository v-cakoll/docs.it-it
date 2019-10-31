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
ms.openlocfilehash: da532ee1b5909a68bedbb9e6f6c96333e88002a8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109718"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="2e34a-102">Metodo ICorDebugModule::EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="2e34a-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="2e34a-103">Controlla se il compilatore JIT (just-in-Time) conserva le informazioni di debug per i metodi all'interno di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="2e34a-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e34a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e34a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e34a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2e34a-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="2e34a-106">in Impostare questo valore su `true` per consentire al compilatore JIT di mantenere le informazioni di mapping tra la versione Microsoft Intermediate Language (MSIL) e la versione compilata tramite JIT di ogni metodo in questo modulo.</span><span class="sxs-lookup"><span data-stu-id="2e34a-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="2e34a-107">in Impostare questo valore su `true` per consentire al compilatore JIT di generare codice con determinate ottimizzazioni specifiche di JIT per il debug.</span><span class="sxs-lookup"><span data-stu-id="2e34a-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e34a-108">Note</span><span class="sxs-lookup"><span data-stu-id="2e34a-108">Remarks</span></span>  
 <span data-ttu-id="2e34a-109">Il debug JIT è abilitato per impostazione predefinita per tutti i moduli caricati quando il debugger è attivo.</span><span class="sxs-lookup"><span data-stu-id="2e34a-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="2e34a-110">L'abilitazione o la disabilitazione delle impostazioni a livello di codice sostituisce le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="2e34a-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e34a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2e34a-111">Requirements</span></span>  
 <span data-ttu-id="2e34a-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e34a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e34a-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e34a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e34a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e34a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e34a-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e34a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
