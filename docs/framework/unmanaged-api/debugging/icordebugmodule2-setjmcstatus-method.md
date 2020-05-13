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
ms.openlocfilehash: d5109043a8601d7997f52e88ea472644f1b9ca03
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208785"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="ea4cb-102">Metodo ICorDebugModule2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="ea4cb-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="ea4cb-103">Imposta lo stato del Just My Code (JMC) di tutti i metodi di tutte le classi di questo ICorDebugModule2 sul valore specificato, ad eccezione di quelli nella `pTokens` matrice, che imposta sul valore opposto.</span><span class="sxs-lookup"><span data-stu-id="ea4cb-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea4cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ea4cb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea4cb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ea4cb-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="ea4cb-106">in Impostare su `true` se è necessario eseguire il debug del codice; in caso contrario, impostare su `false` .</span><span class="sxs-lookup"><span data-stu-id="ea4cb-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="ea4cb-107">[in] Dimensione della matrice `pTokens`.</span><span class="sxs-lookup"><span data-stu-id="ea4cb-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="ea4cb-108">in Matrice di `mdToken` valori, ognuno dei quali fa riferimento a un metodo che avrà lo stato JMC impostato su! `bIsJustMycode` .</span><span class="sxs-lookup"><span data-stu-id="ea4cb-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea4cb-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ea4cb-109">Remarks</span></span>  
 <span data-ttu-id="ea4cb-110">Lo stato JMC di ogni metodo specificato nella `pTokens` matrice è impostato sull'opposto del `bIsJustMycode` valore.</span><span class="sxs-lookup"><span data-stu-id="ea4cb-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="ea4cb-111">Lo stato di tutti gli altri metodi in questo modulo è impostato sul `bIsJustMycode` valore.</span><span class="sxs-lookup"><span data-stu-id="ea4cb-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="ea4cb-112">Il `SetJMCStatus` metodo cancella tutte le impostazioni JMC precedenti in questo modulo.</span><span class="sxs-lookup"><span data-stu-id="ea4cb-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="ea4cb-113">Il `SetJMCStatus` metodo restituisce un S_OK HRESULT se tutte le funzioni sono state impostate correttamente.</span><span class="sxs-lookup"><span data-stu-id="ea4cb-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="ea4cb-114">Restituisce un CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT se alcune funzioni contrassegnate non sono sottoponibili a `true` debug.</span><span class="sxs-lookup"><span data-stu-id="ea4cb-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea4cb-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea4cb-115">Requirements</span></span>  
 <span data-ttu-id="ea4cb-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea4cb-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea4cb-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea4cb-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea4cb-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea4cb-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea4cb-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea4cb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
