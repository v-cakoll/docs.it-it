---
title: Metodo ISymUnmanagedVariable::GetAddressKind
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressKind
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f5b4cb07cbc1ea3f8f297b96a124b8f5a04f0fce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647270"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="d5ec8-102">Metodo ISymUnmanagedVariable::GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="d5ec8-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="d5ec8-103">Ottiene il tipo di indirizzo della variabile.</span><span class="sxs-lookup"><span data-stu-id="d5ec8-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5ec8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5ec8-104">Syntax</span></span>  
  
```  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5ec8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d5ec8-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d5ec8-106">[out] Un puntatore a un `ULONG32` che riceve il valore.</span><span class="sxs-lookup"><span data-stu-id="d5ec8-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="d5ec8-107">I possibili valori sono definiti nel [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="d5ec8-107">The possible values are defined in the [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5ec8-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d5ec8-108">Return Value</span></span>  
 <span data-ttu-id="d5ec8-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d5ec8-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5ec8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d5ec8-110">Requirements</span></span>  
 <span data-ttu-id="d5ec8-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d5ec8-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ec8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5ec8-112">See also</span></span>
- [<span data-ttu-id="d5ec8-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="d5ec8-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
