---
title: Metodo ISymUnmanagedAsyncMethod::GetKickoffMethod
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84aef2b26e008d1a3c6d95d7ec1e130ab0594a11
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484550"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="31410-102">Metodo ISymUnmanagedAsyncMethod::GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="31410-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="31410-103">Visualizzare [metodo DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="31410-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31410-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31410-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31410-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="31410-105">Parameters</span></span>  
  
|<span data-ttu-id="31410-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="31410-106">Parameter</span></span>|<span data-ttu-id="31410-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31410-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="31410-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="31410-108">Return Value</span></span>  
 <span data-ttu-id="31410-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="31410-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31410-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31410-110">Requirements</span></span>  
 <span data-ttu-id="31410-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="31410-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31410-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31410-112">See also</span></span>
- [<span data-ttu-id="31410-113">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="31410-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
