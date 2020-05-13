---
title: Metodo ICorDebugFrame::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
ms.openlocfilehash: cacdccf5c27cd1d115134d49e754b4ace2870b72
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205154"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="77222-102">Metodo ICorDebugFrame::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="77222-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="77222-103">Ottiene l'intervallo di indirizzi assoluto di questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="77222-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77222-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77222-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77222-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="77222-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="77222-106">out Puntatore a un oggetto `CORDB_ADDRESS` che specifica l'indirizzo iniziale del stack frame rappresentato da questo `ICorDebugFrame` oggetto.</span><span class="sxs-lookup"><span data-stu-id="77222-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="77222-107">out Puntatore a un `CORDB_ADDRESS` oggetto che specifica l'indirizzo finale della stack frame rappresentata da questo `ICorDebugFrame` oggetto.</span><span class="sxs-lookup"><span data-stu-id="77222-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77222-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="77222-108">Remarks</span></span>  
 <span data-ttu-id="77222-109">L'intervallo di indirizzi dello stack è utile per riunire tracce dello stack Interleaved raccolte da più motori di debug.</span><span class="sxs-lookup"><span data-stu-id="77222-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="77222-110">L'intervallo numerico non fornisce informazioni sul contenuto del stack frame.</span><span class="sxs-lookup"><span data-stu-id="77222-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="77222-111">È significativo solo per il confronto dei percorsi di stack frame.</span><span class="sxs-lookup"><span data-stu-id="77222-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77222-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="77222-112">Requirements</span></span>  
 <span data-ttu-id="77222-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77222-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77222-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77222-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77222-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77222-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77222-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77222-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
