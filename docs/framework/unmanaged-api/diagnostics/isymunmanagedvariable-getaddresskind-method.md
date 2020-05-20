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
ms.openlocfilehash: 093c5e3e64395c8946acd9201990d132e8111fc7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610587"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="707a2-102">Metodo ISymUnmanagedVariable::GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="707a2-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="707a2-103">Ottiene il tipo di indirizzo della variabile.</span><span class="sxs-lookup"><span data-stu-id="707a2-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="707a2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="707a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="707a2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="707a2-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="707a2-106">out Puntatore a un oggetto `ULONG32` che riceve il valore.</span><span class="sxs-lookup"><span data-stu-id="707a2-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="707a2-107">I valori possibili sono definiti nell'enumerazione [CorSymAddrKind](corsymaddrkind-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="707a2-107">The possible values are defined in the [CorSymAddrKind](corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="707a2-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="707a2-108">Return Value</span></span>  
 <span data-ttu-id="707a2-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="707a2-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="707a2-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="707a2-110">Requirements</span></span>  
 <span data-ttu-id="707a2-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="707a2-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="707a2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="707a2-112">See also</span></span>

- [<span data-ttu-id="707a2-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="707a2-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
