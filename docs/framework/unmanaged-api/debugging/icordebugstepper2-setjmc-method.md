---
title: Metodo ICorDebugStepper2::SetJMC
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c6b53d23410dd310766dab44664c8cd865ee9ba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771690"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="da141-102">Metodo ICorDebugStepper2::SetJMC</span><span class="sxs-lookup"><span data-stu-id="da141-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="da141-103">Imposta un valore che specifica se i passaggi da ICorDebugStepper solo tramite il codice creato dallo sviluppatore di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="da141-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="da141-104">Questo processo è noto anche come just my code (JMC) il debug.</span><span class="sxs-lookup"><span data-stu-id="da141-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da141-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da141-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da141-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="da141-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="da141-107">[in] Impostare su `true` per eseguire solo codice che viene creato dallo sviluppatore dell'applicazione; in caso contrario, impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="da141-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da141-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da141-108">Requirements</span></span>  
 <span data-ttu-id="da141-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da141-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da141-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da141-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da141-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da141-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da141-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da141-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
