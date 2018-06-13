---
title: Metodo ISymUnmanagedAsyncMethod::GetAsyncStepInfo
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a26ff1e0b1bb4d0de662f0186dc2f7958b9707f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425379"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="9ab1b-102">Metodo ISymUnmanagedAsyncMethod::GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="9ab1b-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="9ab1b-103">Vedere [metodo DefineAsyncStepInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="9ab1b-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ab1b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ab1b-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ab1b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9ab1b-105">Parameters</span></span>  
  
|<span data-ttu-id="9ab1b-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="9ab1b-106">Parameter</span></span>|<span data-ttu-id="9ab1b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ab1b-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="9ab1b-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9ab1b-108">Return Value</span></span>  
 <span data-ttu-id="9ab1b-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="9ab1b-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ab1b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9ab1b-110">Requirements</span></span>  
 <span data-ttu-id="9ab1b-111">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9ab1b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab1b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ab1b-112">See Also</span></span>  
 [<span data-ttu-id="9ab1b-113">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="9ab1b-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
