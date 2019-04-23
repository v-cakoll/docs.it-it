---
title: Metodo ISymUnmanagedAsyncMethod::GetKickoffMethod
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4599d41336778db8ce8dcf3ac567e4e2cc8833e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174941"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="673db-102">Metodo ISymUnmanagedAsyncMethod::GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="673db-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="673db-103">Visualizzare [metodo DefineKickoffMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="673db-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="673db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="673db-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="673db-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="673db-105">Parameters</span></span>  
  
|<span data-ttu-id="673db-106">Parametro</span><span class="sxs-lookup"><span data-stu-id="673db-106">Parameter</span></span>|<span data-ttu-id="673db-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="673db-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="673db-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="673db-108">Return Value</span></span>  
 <span data-ttu-id="673db-109">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="673db-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="673db-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="673db-110">Requirements</span></span>  
 <span data-ttu-id="673db-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="673db-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="673db-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="673db-112">See also</span></span>

- [<span data-ttu-id="673db-113">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="673db-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
