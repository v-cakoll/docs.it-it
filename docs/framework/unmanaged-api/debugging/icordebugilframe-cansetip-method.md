---
title: Metodo ICorDebugILFrame::CanSetIP
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
ms.openlocfilehash: c6a02b080739d00667893008be4a19b4fa9a6ef2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788598"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="dce12-102">Metodo ICorDebugILFrame::CanSetIP</span><span class="sxs-lookup"><span data-stu-id="dce12-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="dce12-103">Ottiene un valore HRESULT che indica se è sicuro impostare il puntatore all'istruzione sul percorso di offset specificato nel codice MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="dce12-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dce12-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dce12-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dce12-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dce12-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="dce12-106">in Impostazione desiderata per il puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="dce12-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dce12-107">Note</span><span class="sxs-lookup"><span data-stu-id="dce12-107">Remarks</span></span>  
 <span data-ttu-id="dce12-108">Usare il metodo `CanSetIP` prima di chiamare il metodo [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dce12-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="dce12-109">Se `CanSetIP` restituisce un valore HRESULT diverso da S_OK, è comunque possibile richiamare `ICorDebugILFrame::SetIP`, ma non vi è alcuna garanzia che il debugger continuerà l'esecuzione sicura e corretta del codice sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="dce12-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dce12-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="dce12-110">Requirements</span></span>  
 <span data-ttu-id="dce12-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dce12-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dce12-112">**Intestazione:** CorDebug. idl, CorDebug, h</span><span class="sxs-lookup"><span data-stu-id="dce12-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="dce12-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dce12-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dce12-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dce12-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
