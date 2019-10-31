---
title: Metodo ISymUnmanagedAsyncMethod::GetAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
ms.openlocfilehash: 5d3ee0d42773b70c8301260e5b4d6af1c7ceb938
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139860"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="47534-102">Metodo ISymUnmanagedAsyncMethod::GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="47534-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="47534-103">Vedere il [Metodo DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="47534-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47534-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47534-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47534-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="47534-105">Parameters</span></span>  
  
|<span data-ttu-id="47534-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="47534-106">Parameter</span></span>|<span data-ttu-id="47534-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47534-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="47534-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="47534-108">Return Value</span></span>  
 <span data-ttu-id="47534-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="47534-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47534-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47534-110">Requirements</span></span>  
 <span data-ttu-id="47534-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="47534-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47534-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47534-112">See also</span></span>

- [<span data-ttu-id="47534-113">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="47534-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
