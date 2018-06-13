---
title: Metodo ISymUnmanagedAsyncMethod::GetKickoffMethod
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2f055dc19bf7f40036283102d8cc4549555b992
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424768"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="1bbad-102">Metodo ISymUnmanagedAsyncMethod::GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="1bbad-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="1bbad-103">Vedere [metodo DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="1bbad-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bbad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1bbad-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1bbad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1bbad-105">Parameters</span></span>  
  
|<span data-ttu-id="1bbad-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="1bbad-106">Parameter</span></span>|<span data-ttu-id="1bbad-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bbad-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="1bbad-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1bbad-108">Return Value</span></span>  
 <span data-ttu-id="1bbad-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="1bbad-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bbad-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1bbad-110">Requirements</span></span>  
 <span data-ttu-id="1bbad-111">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1bbad-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bbad-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bbad-112">See Also</span></span>  
 [<span data-ttu-id="1bbad-113">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="1bbad-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
