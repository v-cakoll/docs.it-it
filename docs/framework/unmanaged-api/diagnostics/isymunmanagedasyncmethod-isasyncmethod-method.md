---
title: Metodo ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f5bf8252986ffa90ea5380d5342595cb91e5419
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424941"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="4a974-102">Metodo ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="4a974-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="4a974-103">Controlla se il metodo dispone di informazioni asincrono o meno.</span><span class="sxs-lookup"><span data-stu-id="4a974-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="4a974-104">Se questo metodo restituisce `FALSE` quindi non è possibile chiamare altri metodi in questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4a974-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="4a974-105">Avrà tutte restituito `E_UNEXPECTED` in questo caso.</span><span class="sxs-lookup"><span data-stu-id="4a974-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a974-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a974-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a974-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a974-107">Parameters</span></span>  
  
|<span data-ttu-id="4a974-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="4a974-108">Parameter</span></span>|<span data-ttu-id="4a974-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a974-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="4a974-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4a974-110">Return Value</span></span>  
 <span data-ttu-id="4a974-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="4a974-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a974-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a974-112">Requirements</span></span>  
 <span data-ttu-id="4a974-113">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4a974-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a974-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a974-114">See Also</span></span>  
 [<span data-ttu-id="4a974-115">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="4a974-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
