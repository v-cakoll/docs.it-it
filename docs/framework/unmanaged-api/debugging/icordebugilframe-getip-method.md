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
ms.openlocfilehash: 3890cb4236f113bc6efc23bfb606d19a525ec234
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210267"
---
# <a name="icordebugilframegetip-method"></a><span data-ttu-id="b4340-102">Metodo ICorDebugILFrame::GetIP</span><span class="sxs-lookup"><span data-stu-id="b4340-102">ICorDebugILFrame::GetIP Method</span></span>
<span data-ttu-id="b4340-103">Ottiene il valore del puntatore all'istruzione e un valore di combinazione bit per bit che descrive il modo in cui è stato ottenuto il valore del puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="b4340-103">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4340-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4340-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4340-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b4340-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="b4340-106">out Valore del puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="b4340-106">[out] The value of the instruction pointer.</span></span>  
  
 `pMappingResult`  
 <span data-ttu-id="b4340-107">out Puntatore a una combinazione bit per bit dei valori di Enumerazione CorDebugMappingResult che descrivono come è stato ottenuto il valore del puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="b4340-107">[out] A pointer to a bitwise combination of the CorDebugMappingResult enumeration values that describe how the value of the instruction pointer was obtained.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4340-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b4340-108">Remarks</span></span>  
 <span data-ttu-id="b4340-109">Il valore del puntatore all'istruzione è l'offset del stack frame nel codice MSIL (Microsoft Intermediate Language) della funzione.</span><span class="sxs-lookup"><span data-stu-id="b4340-109">The value of the instruction pointer is the stack frame's offset into the function's Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="b4340-110">Se la stack frame è attiva, questo indirizzo è l'istruzione successiva da eseguire.</span><span class="sxs-lookup"><span data-stu-id="b4340-110">If the stack frame is active, this address is the next instruction to execute.</span></span> <span data-ttu-id="b4340-111">Se il stack frame non è attivo, questo indirizzo è l'istruzione successiva da eseguire quando viene riattivata la stack frame.</span><span class="sxs-lookup"><span data-stu-id="b4340-111">If the stack frame is not active, this address is the next instruction to execute when the stack frame is reactivated.</span></span>  
  
 <span data-ttu-id="b4340-112">Se questo frame è un frame compilato JIT (just-in-Time), il valore del puntatore all'istruzione verrà determinato eseguendo il mapping all'indietro rispetto al puntatore di istruzione nativo effettivo, quindi il valore può essere solo approssimativo.</span><span class="sxs-lookup"><span data-stu-id="b4340-112">If this frame is a just-in-time (JIT) compiled frame, the value of the instruction pointer will be determined by mapping backwards from the actual native instruction pointer, so the value may be only approximate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4340-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b4340-113">Requirements</span></span>  
 <span data-ttu-id="b4340-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4340-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4340-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4340-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4340-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4340-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4340-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4340-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
