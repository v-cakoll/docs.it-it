---
title: Metodo ICorDebugStepper2::SetJMC
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugStepper2.SetJMC
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7fbbe0d3e42df073a5718ca037b44f6f2f31ec23
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="3eadd-102">Metodo ICorDebugStepper2::SetJMC</span><span class="sxs-lookup"><span data-stu-id="3eadd-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="3eadd-103">Imposta un valore che specifica se ICorDebugStepper passo solo nel codice creato dallo sviluppatore di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3eadd-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="3eadd-104">Questo processo è noto anche come my (JMC) il debug del codice.</span><span class="sxs-lookup"><span data-stu-id="3eadd-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eadd-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3eadd-105">Syntax</span></span>  
  
```  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3eadd-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3eadd-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="3eadd-107">[in] Impostare su `true` al passaggio solo tramite codice che viene creato dallo sviluppatore dell'applicazione; in caso contrario, impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="3eadd-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eadd-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3eadd-108">Requirements</span></span>  
 <span data-ttu-id="3eadd-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eadd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eadd-110">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3eadd-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3eadd-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3eadd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3eadd-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eadd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
