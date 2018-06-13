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
ms.openlocfilehash: 18e83582a73ba3b2eb2538bcdf60984c46131768
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426955"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="45bcb-102">Metodo ISymUnmanagedVariable::GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="45bcb-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="45bcb-103">Ottiene il tipo di indirizzo della variabile.</span><span class="sxs-lookup"><span data-stu-id="45bcb-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45bcb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45bcb-104">Syntax</span></span>  
  
```  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45bcb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="45bcb-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="45bcb-106">[out] Un puntatore a un `ULONG32` che riceve il valore.</span><span class="sxs-lookup"><span data-stu-id="45bcb-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="45bcb-107">I valori possibili sono definiti nel [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="45bcb-107">The possible values are defined in the [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45bcb-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="45bcb-108">Return Value</span></span>  
 <span data-ttu-id="45bcb-109">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="45bcb-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45bcb-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45bcb-110">Requirements</span></span>  
 <span data-ttu-id="45bcb-111">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="45bcb-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45bcb-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45bcb-112">See Also</span></span>  
 [<span data-ttu-id="45bcb-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="45bcb-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
