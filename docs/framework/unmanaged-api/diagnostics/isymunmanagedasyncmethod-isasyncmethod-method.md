---
title: Metodo ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 560690e95e7aa0aef37e3a708183641bd70ee97d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="e6418-102">Metodo ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="e6418-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="e6418-103">Controlla se il metodo dispone di informazioni asincrono o meno.</span><span class="sxs-lookup"><span data-stu-id="e6418-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="e6418-104">Se questo metodo restituisce `FALSE` quindi non è possibile chiamare altri metodi in questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e6418-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="e6418-105">Avrà tutte restituito `E_UNEXPECTED` in questo caso.</span><span class="sxs-lookup"><span data-stu-id="e6418-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6418-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6418-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6418-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="e6418-107">Parameters</span></span>  
  
|<span data-ttu-id="e6418-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="e6418-108">Parameter</span></span>|<span data-ttu-id="e6418-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6418-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="e6418-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e6418-110">Return Value</span></span>  
 <span data-ttu-id="e6418-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="e6418-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6418-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e6418-112">Requirements</span></span>  
 <span data-ttu-id="e6418-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e6418-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6418-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6418-114">See Also</span></span>  
 [<span data-ttu-id="e6418-115">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="e6418-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
