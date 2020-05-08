---
title: Metodo ICorDebugClass::GetModule
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
ms.openlocfilehash: fd048b692ad05f60621a057024be22cb48b3abbe
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894204"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="b9fc7-102">Metodo ICorDebugClass::GetModule</span><span class="sxs-lookup"><span data-stu-id="b9fc7-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="b9fc7-103">Ottiene il modulo che definisce questa classe.</span><span class="sxs-lookup"><span data-stu-id="b9fc7-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9fc7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9fc7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9fc7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b9fc7-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="b9fc7-106">out Puntatore all'indirizzo di un oggetto ICorDebugModule che rappresenta il modulo in cui è definita la classe.</span><span class="sxs-lookup"><span data-stu-id="b9fc7-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9fc7-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9fc7-107">Requirements</span></span>  
 <span data-ttu-id="b9fc7-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9fc7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9fc7-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9fc7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9fc7-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9fc7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9fc7-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9fc7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
