---
title: Metodo ICorDebugILFrame::GetLocalVariable
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
ms.openlocfilehash: 85f06b49aab1f1d1745bd7e359ed311c2ba1e44d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130972"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="c701f-102">Metodo ICorDebugILFrame::GetLocalVariable</span><span class="sxs-lookup"><span data-stu-id="c701f-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="c701f-103">Ottiene il valore della variabile locale specificata in questo stack frame MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="c701f-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c701f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c701f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c701f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c701f-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="c701f-106">in Indice della variabile locale in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="c701f-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="c701f-107">out Puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore recuperato.</span><span class="sxs-lookup"><span data-stu-id="c701f-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c701f-108">Note</span><span class="sxs-lookup"><span data-stu-id="c701f-108">Remarks</span></span>  
 <span data-ttu-id="c701f-109">Il metodo `GetLocalVariable` può essere utilizzato in un stack frame MSIL o in un frame compilato JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="c701f-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c701f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c701f-110">Requirements</span></span>  
 <span data-ttu-id="c701f-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c701f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c701f-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c701f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c701f-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c701f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c701f-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c701f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
