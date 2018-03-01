---
title: Metodo ISymUnmanagedVariable::GetAddressField3
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eb7bfa17729321df21dfc69c79d65baf2a92a44a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="fe15a-102">Metodo ISymUnmanagedVariable::GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="fe15a-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="fe15a-103">Ottiene il terzo campo indirizzo per la variabile.</span><span class="sxs-lookup"><span data-stu-id="fe15a-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="fe15a-104">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="fe15a-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe15a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe15a-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe15a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe15a-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="fe15a-107">[out] Un puntatore a un `ULONG32` che riceve il terzo campo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="fe15a-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe15a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fe15a-108">Return Value</span></span>  
 <span data-ttu-id="fe15a-109">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="fe15a-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe15a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe15a-110">Requirements</span></span>  
 <span data-ttu-id="fe15a-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fe15a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe15a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe15a-112">See Also</span></span>  
 [<span data-ttu-id="fe15a-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="fe15a-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="fe15a-114">Metodo GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="fe15a-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)  
 [<span data-ttu-id="fe15a-115">Metodo GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="fe15a-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="fe15a-116">Metodo GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="fe15a-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
