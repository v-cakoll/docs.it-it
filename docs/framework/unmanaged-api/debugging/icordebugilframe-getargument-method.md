---
title: Metodo ICorDebugILFrame::GetArgument
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
ms.openlocfilehash: 01c7cb2e4359a477c26f995602dbf29668e567c0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131016"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="782d4-102">Metodo ICorDebugILFrame::GetArgument</span><span class="sxs-lookup"><span data-stu-id="782d4-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="782d4-103">Ottiene il valore dell'argomento specificato in questo stack frame MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="782d4-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="782d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="782d4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="782d4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="782d4-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="782d4-106">in Indice dell'argomento in questo stack frame MSIL.</span><span class="sxs-lookup"><span data-stu-id="782d4-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="782d4-107">out Puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta il valore recuperato.</span><span class="sxs-lookup"><span data-stu-id="782d4-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="782d4-108">Note</span><span class="sxs-lookup"><span data-stu-id="782d4-108">Remarks</span></span>  
 <span data-ttu-id="782d4-109">Il metodo `GetArgument` può essere utilizzato in un stack frame MSIL o in un frame compilato JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="782d4-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="782d4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="782d4-110">Requirements</span></span>  
 <span data-ttu-id="782d4-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="782d4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="782d4-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="782d4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="782d4-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="782d4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="782d4-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="782d4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
