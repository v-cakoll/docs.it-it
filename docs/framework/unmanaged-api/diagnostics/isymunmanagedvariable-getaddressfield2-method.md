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
ms.openlocfilehash: 6256d052780b1c610e61267be2517954d722a42d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610600"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="240f4-102">Metodo ISymUnmanagedVariable::GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="240f4-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="240f4-103">Ottiene il secondo campo dell'indirizzo per questa variabile.</span><span class="sxs-lookup"><span data-stu-id="240f4-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="240f4-104">Il suo significato dipende dal tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="240f4-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="240f4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="240f4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="240f4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="240f4-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="240f4-107">out Puntatore a un oggetto `ULONG32` che riceve il secondo campo dell'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="240f4-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="240f4-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="240f4-108">Return Value</span></span>  
 <span data-ttu-id="240f4-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="240f4-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="240f4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="240f4-110">Requirements</span></span>  
 <span data-ttu-id="240f4-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="240f4-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="240f4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="240f4-112">See also</span></span>

- [<span data-ttu-id="240f4-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="240f4-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="240f4-114">Metodo GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="240f4-114">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="240f4-115">Metodo GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="240f4-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="240f4-116">Metodo GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="240f4-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
