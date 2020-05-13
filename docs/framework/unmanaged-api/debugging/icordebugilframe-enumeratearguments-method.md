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
ms.openlocfilehash: 3945b1dea62dc0616d669356faf60f0d09cfb084
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210306"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="e09a4-102">Metodo ICorDebugILFrame::EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="e09a4-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="e09a4-103">Ottiene un enumeratore per gli argomenti in questo frame.</span><span class="sxs-lookup"><span data-stu-id="e09a4-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e09a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e09a4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e09a4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e09a4-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="e09a4-106">out Puntatore all'indirizzo di un oggetto ICorDebugValueEnum che rappresenta l'enumeratore per gli argomenti in questo frame.</span><span class="sxs-lookup"><span data-stu-id="e09a4-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e09a4-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e09a4-107">Remarks</span></span>  
 <span data-ttu-id="e09a4-108">`EnumerateArguments`Ottiene un enumeratore in grado di elencare gli argomenti disponibili nel frame di chiamata rappresentato da questo oggetto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="e09a4-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="e09a4-109">L'elenco includerà gli argomenti [vararg](/cpp/windows/vararg) (ovvero un numero variabile di argomenti) e gli argomenti che non lo sono `vararg` .</span><span class="sxs-lookup"><span data-stu-id="e09a4-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e09a4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e09a4-110">Requirements</span></span>  
 <span data-ttu-id="e09a4-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e09a4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e09a4-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e09a4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e09a4-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e09a4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e09a4-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e09a4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
