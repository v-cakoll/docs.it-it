---
title: Metodo ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 0ea4c21e9e6a49d7bbbad5e1853598c440cd6410
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129206"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="8146e-102">Metodo ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="8146e-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="8146e-103">Verifica se il metodo contiene informazioni asincrone o meno.</span><span class="sxs-lookup"><span data-stu-id="8146e-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="8146e-104">Se questo metodo restituisce `FALSE` quindi non è valido per chiamare altri metodi in questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8146e-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="8146e-105">Verranno restituiti tutti `E_UNEXPECTED` in questo caso.</span><span class="sxs-lookup"><span data-stu-id="8146e-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8146e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8146e-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8146e-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="8146e-107">Parameters</span></span>  
  
|<span data-ttu-id="8146e-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="8146e-108">Parameter</span></span>|<span data-ttu-id="8146e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8146e-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="8146e-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8146e-110">Return Value</span></span>  
 <span data-ttu-id="8146e-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="8146e-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8146e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8146e-112">Requirements</span></span>  
 <span data-ttu-id="8146e-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8146e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8146e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8146e-114">See also</span></span>

- [<span data-ttu-id="8146e-115">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="8146e-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
