---
title: Metodo ICorDebugNativeFrame::CanSetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
ms.openlocfilehash: 21890f8130ec677cb88f2f5d7ef648aa19e67e71
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213062"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="8ba10-102">Metodo ICorDebugNativeFrame::CanSetIP</span><span class="sxs-lookup"><span data-stu-id="8ba10-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="8ba10-103">Ottiene un HRESULT che indica se è sicuro impostare il puntatore all'istruzione (IP) sulla posizione di offset specificata nel codice nativo.</span><span class="sxs-lookup"><span data-stu-id="8ba10-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba10-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ba10-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ba10-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ba10-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="8ba10-106">in Impostazione desiderata per il puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="8ba10-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ba10-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8ba10-107">Remarks</span></span>  
 <span data-ttu-id="8ba10-108">Usare il `CanSetIP` metodo prima di chiamare il metodo [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8ba10-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="8ba10-109">Se `CanSetIP` restituisce un valore HRESULT diverso da S_OK, è comunque possibile richiamare `ICorDebugNativeFrame::SetIP` , ma non vi è alcuna garanzia che il debugger continuerà l'esecuzione sicura e corretta del codice sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="8ba10-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ba10-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ba10-110">Requirements</span></span>  
 <span data-ttu-id="8ba10-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ba10-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ba10-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ba10-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ba10-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ba10-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ba10-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ba10-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ba10-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ba10-115">See also</span></span>
