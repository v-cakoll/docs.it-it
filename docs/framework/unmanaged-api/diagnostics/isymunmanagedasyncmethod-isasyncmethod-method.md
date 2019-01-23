---
title: Metodo ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 049f8e4d04498b70533134c01765af2d996d86dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499106"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="eb592-102">Metodo ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="eb592-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="eb592-103">Controlla se il metodo contiene le informazioni di async o meno.</span><span class="sxs-lookup"><span data-stu-id="eb592-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="eb592-104">Se questo metodo restituisce `FALSE` quindi non è consentito chiamare altri metodi in questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="eb592-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="eb592-105">Restituirà tutti `E_UNEXPECTED` in questo caso.</span><span class="sxs-lookup"><span data-stu-id="eb592-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb592-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="eb592-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb592-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="eb592-107">Parameters</span></span>  
  
|<span data-ttu-id="eb592-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="eb592-108">Parameter</span></span>|<span data-ttu-id="eb592-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eb592-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="eb592-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="eb592-110">Return Value</span></span>  
 <span data-ttu-id="eb592-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="eb592-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb592-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eb592-112">Requirements</span></span>  
 <span data-ttu-id="eb592-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="eb592-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb592-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb592-114">See also</span></span>
- [<span data-ttu-id="eb592-115">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="eb592-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
