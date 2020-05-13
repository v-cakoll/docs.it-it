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
ms.openlocfilehash: 2bd4ab4a080461c56b0287d24aa288847445d803
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210319"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="f8a68-102">Metodo ICorDebugILFrame::CanSetIP</span><span class="sxs-lookup"><span data-stu-id="f8a68-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="f8a68-103">Ottiene un valore HRESULT che indica se è sicuro impostare il puntatore all'istruzione sul percorso di offset specificato nel codice MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="f8a68-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8a68-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8a68-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8a68-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f8a68-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="f8a68-106">in Impostazione desiderata per il puntatore all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="f8a68-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8a68-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f8a68-107">Remarks</span></span>  
 <span data-ttu-id="f8a68-108">Usare il `CanSetIP` metodo prima di chiamare il metodo [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f8a68-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="f8a68-109">Se `CanSetIP` restituisce un valore HRESULT diverso da S_OK, è comunque possibile richiamare `ICorDebugILFrame::SetIP` , ma non vi è alcuna garanzia che il debugger continuerà l'esecuzione sicura e corretta del codice sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="f8a68-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8a68-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8a68-110">Requirements</span></span>  
 <span data-ttu-id="f8a68-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8a68-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8a68-112">**Intestazione:** CorDebug. idl, CorDebug, h</span><span class="sxs-lookup"><span data-stu-id="f8a68-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="f8a68-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8a68-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8a68-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8a68-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
