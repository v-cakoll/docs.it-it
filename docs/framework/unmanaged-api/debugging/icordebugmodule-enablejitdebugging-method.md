---
title: Metodo ICorDebugModule::EnableJITDebugging
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.EnableJITDebugging
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 31fc3b7c2b977dbfd6f10cc767f81748243dfce4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="091a9-102">Metodo ICorDebugModule::EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="091a9-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="091a9-103">Controlla se il compilatore di just-in-time (JIT) consente di mantenere le informazioni di debug per i metodi all'interno del modulo.</span><span class="sxs-lookup"><span data-stu-id="091a9-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="091a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="091a9-104">Syntax</span></span>  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="091a9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="091a9-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="091a9-106">[in] Impostare questo valore su `true` per consentire al compilatore JIT di mantenere le informazioni di mapping tra la versione di Microsoft intermediate language (MSIL) e la versione compilata tramite JIT di ogni metodo in questo modulo.</span><span class="sxs-lookup"><span data-stu-id="091a9-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="091a9-107">[in] Impostare questo valore su `true` per consentire al compilatore JIT generare il codice con alcune ottimizzazioni JIT specifiche per il debug.</span><span class="sxs-lookup"><span data-stu-id="091a9-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="091a9-108">Note</span><span class="sxs-lookup"><span data-stu-id="091a9-108">Remarks</span></span>  
 <span data-ttu-id="091a9-109">Debug JIT è abilitato per impostazione predefinita per tutti i moduli caricati quando è attivo il debugger.</span><span class="sxs-lookup"><span data-stu-id="091a9-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="091a9-110">A livello di programmazione abilitando o disabilitando le impostazioni di override delle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="091a9-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="091a9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="091a9-111">Requirements</span></span>  
 <span data-ttu-id="091a9-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="091a9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="091a9-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="091a9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="091a9-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="091a9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="091a9-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="091a9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
