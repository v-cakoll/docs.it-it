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
ms.openlocfilehash: bdf027f94c8416d052cb807d04be76a39868ccf7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212932"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="b1e70-102">Metodo ICorDebugModule::EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="b1e70-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="b1e70-103">Controlla se il compilatore JIT (just-in-Time) conserva le informazioni di debug per i metodi all'interno di questo modulo.</span><span class="sxs-lookup"><span data-stu-id="b1e70-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1e70-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1e70-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1e70-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b1e70-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="b1e70-106">in Impostare questo valore su `true` per consentire al compilatore JIT di mantenere le informazioni di mapping tra la versione Microsoft Intermediate Language (MSIL) e la versione compilata tramite JIT di ogni metodo in questo modulo.</span><span class="sxs-lookup"><span data-stu-id="b1e70-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="b1e70-107">in Impostare questo valore su `true` per consentire al compilatore JIT di generare codice con determinate ottimizzazioni specifiche di JIT per il debug.</span><span class="sxs-lookup"><span data-stu-id="b1e70-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1e70-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b1e70-108">Remarks</span></span>  
 <span data-ttu-id="b1e70-109">Il debug JIT è abilitato per impostazione predefinita per tutti i moduli caricati quando il debugger è attivo.</span><span class="sxs-lookup"><span data-stu-id="b1e70-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="b1e70-110">L'abilitazione o la disabilitazione delle impostazioni a livello di codice sostituisce le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="b1e70-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1e70-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1e70-111">Requirements</span></span>  
 <span data-ttu-id="b1e70-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1e70-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1e70-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1e70-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1e70-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1e70-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1e70-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1e70-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
