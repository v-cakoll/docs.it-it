---
title: Metodo ICorDebugILFrame::GetIP
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a7b8985e7580282d0e38205f9b1d6078f86cee6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988611"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="381bf-102">Metodo ICorDebugILFrame::GetIP</span><span class="sxs-lookup"><span data-stu-id="381bf-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="381bf-103">Ottiene il valore del puntatore dell'istruzione e un valore di combinazione bit per bit che descrive come è stato ottenuto il valore del puntatore dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="381bf-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="381bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="381bf-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,   
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="381bf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="381bf-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="381bf-106">[out] Il valore del puntatore dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="381bf-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="381bf-107">[out] Un puntatore a una combinazione bit per bit dei valori di enumerazione CorDebugMappingResult indicanti il modo in cui è stato ottenuto il valore del puntatore dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="381bf-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="381bf-108">Note</span><span class="sxs-lookup"><span data-stu-id="381bf-108">Remarks</span></span>  
 <span data-ttu-id="381bf-109">Il valore del puntatore dell'istruzione è l'offset del frame dello stack nel codice della funzione Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="381bf-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="381bf-110">Se lo stack frame è attivo, questo indirizzo è l'istruzione successiva da eseguire.</span><span class="sxs-lookup"><span data-stu-id="381bf-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="381bf-111">Se lo stack frame non è attivo, questo indirizzo è l'istruzione successiva da eseguire quando viene riattivato lo stack frame.</span><span class="sxs-lookup"><span data-stu-id="381bf-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="381bf-112">Se il frame è un frame compilato tramite just-in-time (JIT), il valore del puntatore dell'istruzione verrà determinato eseguendo il mapping con le versioni precedenti dal puntatore alle istruzioni native effettivo, pertanto il valore può essere solo approssimativo.</span><span class="sxs-lookup"><span data-stu-id="381bf-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="381bf-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="381bf-113">Requirements</span></span>  
 <span data-ttu-id="381bf-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="381bf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="381bf-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="381bf-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="381bf-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="381bf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="381bf-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="381bf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
