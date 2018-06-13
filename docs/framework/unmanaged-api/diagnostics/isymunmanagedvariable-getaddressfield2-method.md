---
title: Metodo ISymUnmanagedVariable::GetAddressField2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe360a50038f49fdea1528c8c520dc893b258057
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427086"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="6e165-102">Metodo ISymUnmanagedVariable::GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="6e165-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="6e165-103">Ottiene il secondo campo dell'indirizzo per la variabile.</span><span class="sxs-lookup"><span data-stu-id="6e165-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="6e165-104">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="6e165-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e165-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e165-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e165-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6e165-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="6e165-107">[out] Un puntatore a un `ULONG32` che riceve il secondo campo dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="6e165-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e165-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6e165-108">Return Value</span></span>  
 <span data-ttu-id="6e165-109">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="6e165-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e165-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e165-110">Requirements</span></span>  
 <span data-ttu-id="6e165-111">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6e165-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e165-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e165-112">See Also</span></span>  
 [<span data-ttu-id="6e165-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="6e165-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="6e165-114">Metodo GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="6e165-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)  
 [<span data-ttu-id="6e165-115">Metodo GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="6e165-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)  
 [<span data-ttu-id="6e165-116">Metodo GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="6e165-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
