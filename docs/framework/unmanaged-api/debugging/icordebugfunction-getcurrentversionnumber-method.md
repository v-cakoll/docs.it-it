---
title: Metodo ICorDebugFunction::GetCurrentVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
ms.openlocfilehash: b47580022b98ea02584a94b3f74b3fd1c276f297
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212906"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="1f13e-102">Metodo ICorDebugFunction::GetCurrentVersionNumber</span><span class="sxs-lookup"><span data-stu-id="1f13e-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="1f13e-103">Ottiene il numero di versione dell'Ultima modifica apportata alla funzione rappresentata da questo oggetto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="1f13e-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f13e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f13e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f13e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1f13e-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="1f13e-106">out Puntatore a un valore integer che rappresenta il numero di versione dell'Ultima modifica apportata a questa funzione.</span><span class="sxs-lookup"><span data-stu-id="1f13e-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f13e-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1f13e-107">Remarks</span></span>  
 <span data-ttu-id="1f13e-108">Il numero di versione dell'Ultima modifica apportata a questa funzione potrebbe essere maggiore del numero di versione della funzione stessa.</span><span class="sxs-lookup"><span data-stu-id="1f13e-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="1f13e-109">Usare il metodo [ICorDebugFunction2:: GetVersionNumber](icordebugfunction2-getversionnumber-method.md) o [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) per recuperare il numero di versione della funzione.</span><span class="sxs-lookup"><span data-stu-id="1f13e-109">Use either the [ICorDebugFunction2::GetVersionNumber](icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f13e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1f13e-110">Requirements</span></span>  
 <span data-ttu-id="1f13e-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f13e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f13e-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f13e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f13e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f13e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f13e-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f13e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
