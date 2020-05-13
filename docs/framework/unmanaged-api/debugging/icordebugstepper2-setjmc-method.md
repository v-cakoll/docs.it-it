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
ms.openlocfilehash: ab1351af042aba5042cc7a04614bc3cf14f7d7ae
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379466"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="dd9fe-102">Metodo ICorDebugStepper2::SetJMC</span><span class="sxs-lookup"><span data-stu-id="dd9fe-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="dd9fe-103">Imposta un valore che specifica se questo ICorDebugStepper passaggi solo tramite codice creato dallo sviluppatore di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dd9fe-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="dd9fe-104">Questo processo è noto anche come debug JMC (Just My Code).</span><span class="sxs-lookup"><span data-stu-id="dd9fe-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd9fe-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd9fe-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd9fe-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="dd9fe-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="dd9fe-107">in Impostare su `true` per eseguire l'istruzione solo tramite codice creato dallo sviluppatore di un'applicazione; in caso contrario, impostare su `false` .</span><span class="sxs-lookup"><span data-stu-id="dd9fe-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd9fe-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd9fe-108">Requirements</span></span>  
 <span data-ttu-id="dd9fe-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd9fe-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd9fe-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd9fe-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd9fe-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd9fe-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd9fe-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd9fe-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
