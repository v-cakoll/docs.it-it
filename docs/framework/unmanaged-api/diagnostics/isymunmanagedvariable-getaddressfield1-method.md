---
title: Metodo ISymUnmanagedVariable::GetAddressField1
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
ms.openlocfilehash: 253fd17178c03bc0c4d8ea031888a404ad56f876
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615280"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="db4d0-102">Metodo ISymUnmanagedVariable::GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="db4d0-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="db4d0-103">Ottiene il primo campo dell'indirizzo per questa variabile.</span><span class="sxs-lookup"><span data-stu-id="db4d0-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="db4d0-104">Il suo significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="db4d0-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db4d0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db4d0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db4d0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="db4d0-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="db4d0-107">out Puntatore a un oggetto `ULONG32` che riceve il primo campo dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="db4d0-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db4d0-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="db4d0-108">Return Value</span></span>  
 <span data-ttu-id="db4d0-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="db4d0-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db4d0-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db4d0-110">Requirements</span></span>  
 <span data-ttu-id="db4d0-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="db4d0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db4d0-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db4d0-112">See also</span></span>

- [<span data-ttu-id="db4d0-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="db4d0-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="db4d0-114">Metodo GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="db4d0-114">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="db4d0-115">Metodo GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="db4d0-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="db4d0-116">Metodo GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="db4d0-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
