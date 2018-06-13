---
title: Metodo ICorDebugILFrame::EnumerateArguments
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e4a727dcfbc80b131f526a08b00bd0ec91ca209
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415022"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="6fef3-102">Metodo ICorDebugILFrame::EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="6fef3-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="6fef3-103">Ottiene un enumeratore per gli argomenti nel frame.</span><span class="sxs-lookup"><span data-stu-id="6fef3-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fef3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fef3-104">Syntax</span></span>  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6fef3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6fef3-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="6fef3-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValueEnum che è l'enumeratore per gli argomenti nel frame.</span><span class="sxs-lookup"><span data-stu-id="6fef3-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fef3-107">Note</span><span class="sxs-lookup"><span data-stu-id="6fef3-107">Remarks</span></span>  
 <span data-ttu-id="6fef3-108">`EnumerateArguments` Ottiene un enumeratore in grado di elencare gli argomenti disponibili nel frame di chiamata che è rappresentato da questo oggetto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="6fef3-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="6fef3-109">L'elenco includerà gli argomenti devono essere [vararg](/cpp/windows/vararg) (ovvero, un numero variabile di argomenti) e argomenti che non sono `vararg`.</span><span class="sxs-lookup"><span data-stu-id="6fef3-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fef3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6fef3-110">Requirements</span></span>  
 <span data-ttu-id="6fef3-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fef3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fef3-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6fef3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fef3-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6fef3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fef3-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fef3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
