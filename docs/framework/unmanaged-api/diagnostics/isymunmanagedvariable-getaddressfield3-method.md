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
ms.openlocfilehash: dd474c7f149b8eff542b674c2ba6527b6a0cbcb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426998"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="964dc-102">Metodo ISymUnmanagedVariable::GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="964dc-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="964dc-103">Ottiene il terzo campo indirizzo per la variabile.</span><span class="sxs-lookup"><span data-stu-id="964dc-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="964dc-104">Il significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="964dc-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="964dc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="964dc-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="964dc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="964dc-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="964dc-107">[out] Un puntatore a un `ULONG32` che riceve il terzo campo indirizzo.</span><span class="sxs-lookup"><span data-stu-id="964dc-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="964dc-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="964dc-108">Return Value</span></span>  
 <span data-ttu-id="964dc-109">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="964dc-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="964dc-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="964dc-110">Requirements</span></span>  
 <span data-ttu-id="964dc-111">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="964dc-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="964dc-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="964dc-112">See Also</span></span>  
 [<span data-ttu-id="964dc-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="964dc-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="964dc-114">Metodo GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="964dc-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)  
 [<span data-ttu-id="964dc-115">Metodo GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="964dc-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="964dc-116">Metodo GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="964dc-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
