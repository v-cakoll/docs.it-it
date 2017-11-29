---
title: Metodo ICorDebugNativeFrame::CanSetIP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.CanSetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33b5efe6352d3a0c30179990205315c76f3a704d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="c0ee2-102">Metodo ICorDebugNativeFrame::CanSetIP</span><span class="sxs-lookup"><span data-stu-id="c0ee2-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="c0ee2-103">Ottiene un valore HRESULT che indica se è possibile impostare il puntatore all'istruzione (IP) alla posizione di offset specificata in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="c0ee2-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0ee2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0ee2-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0ee2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c0ee2-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="c0ee2-106">[in] L'impostazione desiderata per il puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="c0ee2-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0ee2-107">Note</span><span class="sxs-lookup"><span data-stu-id="c0ee2-107">Remarks</span></span>  
 <span data-ttu-id="c0ee2-108">Utilizzare il `CanSetIP` metodo prima di chiamare il [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="c0ee2-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="c0ee2-109">Se `CanSetIP` restituisce qualsiasi valore HRESULT diverso da S_OK, sarà comunque possibile richiamare `ICorDebugNativeFrame::SetIP`, ma non c'è garanzia che il debugger continua l'esecuzione sicura e corretta del codice in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="c0ee2-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0ee2-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0ee2-110">Requirements</span></span>  
 <span data-ttu-id="c0ee2-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0ee2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0ee2-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c0ee2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0ee2-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0ee2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0ee2-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0ee2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ee2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0ee2-115">See Also</span></span>  
 
