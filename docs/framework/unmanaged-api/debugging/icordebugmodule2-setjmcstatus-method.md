---
title: Metodo ICorDebugModule2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: a0b70078dee88b270d8361aa9bddcb7d80df1db1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129465"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="e90b9-102">Metodo ICorDebugModule2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="e90b9-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="e90b9-103">Imposta lo stato del Just My Code (JMC) di tutti i metodi di tutte le classi di questo ICorDebugModule2 sul valore specificato, ad eccezione di quelli nella matrice `pTokens`, che imposta sul valore opposto.</span><span class="sxs-lookup"><span data-stu-id="e90b9-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e90b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e90b9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e90b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e90b9-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="e90b9-106">in Impostare su `true` se il codice deve essere sottoposto a debug; in caso contrario, impostare su `false`.</span><span class="sxs-lookup"><span data-stu-id="e90b9-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="e90b9-107">[in] Dimensione della matrice `pTokens`.</span><span class="sxs-lookup"><span data-stu-id="e90b9-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="e90b9-108">in Matrice di valori di `mdToken`, ciascuno dei quali fa riferimento a un metodo per il quale lo stato del JMC è impostato su.`bIsJustMycode`.</span><span class="sxs-lookup"><span data-stu-id="e90b9-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e90b9-109">Note</span><span class="sxs-lookup"><span data-stu-id="e90b9-109">Remarks</span></span>  
 <span data-ttu-id="e90b9-110">Lo stato JMC di ogni metodo specificato nella matrice `pTokens` viene impostato sull'opposto del valore `bIsJustMycode`.</span><span class="sxs-lookup"><span data-stu-id="e90b9-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="e90b9-111">Lo stato di tutti gli altri metodi in questo modulo è impostato sul valore `bIsJustMycode`.</span><span class="sxs-lookup"><span data-stu-id="e90b9-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="e90b9-112">Il metodo `SetJMCStatus` Cancella tutte le impostazioni JMC precedenti in questo modulo.</span><span class="sxs-lookup"><span data-stu-id="e90b9-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="e90b9-113">Il metodo `SetJMCStatus` restituisce un HRESULT S_OK se tutte le funzioni sono state impostate correttamente.</span><span class="sxs-lookup"><span data-stu-id="e90b9-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="e90b9-114">Restituisce un HRESULT CORDBG_E_FUNCTION_NOT_DEBUGGABLE se alcune funzioni contrassegnate come `true` non sono sottoponibili a debug.</span><span class="sxs-lookup"><span data-stu-id="e90b9-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e90b9-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e90b9-115">Requirements</span></span>  
 <span data-ttu-id="e90b9-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e90b9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e90b9-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e90b9-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e90b9-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e90b9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e90b9-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e90b9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
