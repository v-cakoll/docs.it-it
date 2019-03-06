---
title: Metodo ISymUnmanagedVariable::GetAddressField3
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0838ac08ff69e33a0badef7c0f52cb6189be2b7f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469040"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="df80e-102">Metodo ISymUnmanagedVariable::GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="df80e-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="df80e-103">Ottiene il terzo campo dell'indirizzo di questa variabile.</span><span class="sxs-lookup"><span data-stu-id="df80e-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="df80e-104">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="df80e-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df80e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df80e-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df80e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="df80e-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="df80e-107">[out] Un puntatore a un `ULONG32` che riceve il terzo campo dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="df80e-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df80e-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="df80e-108">Return Value</span></span>  
 <span data-ttu-id="df80e-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="df80e-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df80e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="df80e-110">Requirements</span></span>  
 <span data-ttu-id="df80e-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="df80e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df80e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df80e-112">See also</span></span>
- [<span data-ttu-id="df80e-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="df80e-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="df80e-114">Metodo GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="df80e-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="df80e-115">Metodo GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="df80e-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="df80e-116">Metodo GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="df80e-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
