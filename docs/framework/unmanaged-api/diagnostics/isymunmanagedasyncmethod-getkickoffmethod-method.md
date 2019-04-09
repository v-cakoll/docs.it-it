---
title: Metodo ISymUnmanagedAsyncMethod::GetKickoffMethod
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4599d41336778db8ce8dcf3ac567e4e2cc8833e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174941"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="da661-102">Metodo ISymUnmanagedAsyncMethod::GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="da661-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="da661-103">Visualizzare [metodo DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="da661-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da661-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da661-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da661-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da661-105">Parameters</span></span>  
  
|<span data-ttu-id="da661-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="da661-106">Parameter</span></span>|<span data-ttu-id="da661-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da661-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="da661-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="da661-108">Return Value</span></span>  
 <span data-ttu-id="da661-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="da661-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da661-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da661-110">Requirements</span></span>  
 <span data-ttu-id="da661-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="da661-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da661-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da661-112">See also</span></span>

- [<span data-ttu-id="da661-113">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="da661-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
