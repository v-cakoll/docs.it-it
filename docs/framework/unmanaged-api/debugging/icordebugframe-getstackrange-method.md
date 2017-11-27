---
title: Metodo ICorDebugFrame::GetStackRange
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetStackRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f1db7617d52e07489ade339b76023e21816835ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="63ef7-102">Metodo ICorDebugFrame::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="63ef7-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="63ef7-103">Ottiene l'intervallo di indirizzi assoluti dello stack frame corrente.</span><span class="sxs-lookup"><span data-stu-id="63ef7-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ef7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63ef7-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63ef7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="63ef7-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="63ef7-106">[out] Un puntatore a un `CORDB_ADDRESS` che specifica l'indirizzo iniziale dello stack frame rappresentato da questo `ICorDebugFrame` oggetto.</span><span class="sxs-lookup"><span data-stu-id="63ef7-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="63ef7-107">[out] Un puntatore a un `CORDB_ADDRESS` che specifica l'indirizzo finale dello stack frame rappresentato da questo `ICorDebugFrame` oggetto.</span><span class="sxs-lookup"><span data-stu-id="63ef7-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63ef7-108">Note</span><span class="sxs-lookup"><span data-stu-id="63ef7-108">Remarks</span></span>  
 <span data-ttu-id="63ef7-109">L'intervallo di indirizzi dello stack è utile per riunire le tracce dello stack con interfoliazione raccolte da più motori di debug.</span><span class="sxs-lookup"><span data-stu-id="63ef7-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="63ef7-110">L'intervallo numerico non fornisce informazioni sul contenuto del frame dello stack.</span><span class="sxs-lookup"><span data-stu-id="63ef7-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="63ef7-111">È significativo solo per il confronto di percorsi dello stack frame.</span><span class="sxs-lookup"><span data-stu-id="63ef7-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63ef7-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63ef7-112">Requirements</span></span>  
 <span data-ttu-id="63ef7-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63ef7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63ef7-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="63ef7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63ef7-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63ef7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63ef7-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63ef7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
