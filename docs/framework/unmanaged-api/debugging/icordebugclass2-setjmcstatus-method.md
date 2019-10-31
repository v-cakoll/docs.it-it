---
title: Metodo ICorDebugClass2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: a862dd3f6a9c10c6b3a5a0bb41208d351c4ca9f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125695"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="4f6aa-102">Metodo ICorDebugClass2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="4f6aa-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="4f6aa-103">Per ogni metodo della classe, imposta un valore che indica se il metodo è codice definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4f6aa-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f6aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f6aa-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f6aa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f6aa-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="4f6aa-106">in Impostare su `true` per indicare che il metodo è codice definito dall'utente; in caso contrario, impostare su `false`.</span><span class="sxs-lookup"><span data-stu-id="4f6aa-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f6aa-107">Note</span><span class="sxs-lookup"><span data-stu-id="4f6aa-107">Remarks</span></span>  
 <span data-ttu-id="4f6aa-108">Un stepper (Just-My-Code) ignorerà il codice non definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4f6aa-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="4f6aa-109">Il codice definito dall'utente deve essere un subset del codice di cui è possibile eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="4f6aa-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="4f6aa-110">`SetJMCStatus` restituisce un valore HRESULT di S_FALSE se non riesce a impostare il valore per qualsiasi metodo, anche se imposta correttamente il valore per tutti gli altri metodi.</span><span class="sxs-lookup"><span data-stu-id="4f6aa-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f6aa-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f6aa-111">Requirements</span></span>  
 <span data-ttu-id="4f6aa-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f6aa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f6aa-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f6aa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f6aa-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f6aa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f6aa-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f6aa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
