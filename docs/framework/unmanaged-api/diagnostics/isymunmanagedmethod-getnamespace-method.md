---
title: Metodo ISymUnmanagedMethod::GetNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
ms.openlocfilehash: cda30f3c73bf75c37ff79fc415e02382b053807e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614487"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="8847c-102">Metodo ISymUnmanagedMethod::GetNamespace</span><span class="sxs-lookup"><span data-stu-id="8847c-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="8847c-103">Ottiene lo spazio dei nomi in cui è definito il metodo.</span><span class="sxs-lookup"><span data-stu-id="8847c-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8847c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8847c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8847c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8847c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8847c-106">out Puntatore impostato sull'interfaccia [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) restituita.</span><span class="sxs-lookup"><span data-stu-id="8847c-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8847c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8847c-107">Return Value</span></span>  
 <span data-ttu-id="8847c-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="8847c-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8847c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8847c-109">Requirements</span></span>  
 <span data-ttu-id="8847c-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8847c-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8847c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8847c-111">See also</span></span>

- [<span data-ttu-id="8847c-112">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="8847c-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
