---
title: Metodo ISymUnmanagedMethod::GetToken
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
ms.openlocfilehash: 0803f0b55f19b779f5b6608a9f8200d2b085b504
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615157"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="1169a-102">Metodo ISymUnmanagedMethod::GetToken</span><span class="sxs-lookup"><span data-stu-id="1169a-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="1169a-103">Restituisce il token di metadati per il metodo.</span><span class="sxs-lookup"><span data-stu-id="1169a-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1169a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1169a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1169a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1169a-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="1169a-106">out Puntatore a un oggetto `mdMethodDef` che riceve la dimensione, in caratteri, del buffer necessario per contenere i metadati.</span><span class="sxs-lookup"><span data-stu-id="1169a-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1169a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1169a-107">Return Value</span></span>  
 <span data-ttu-id="1169a-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1169a-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1169a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1169a-109">Requirements</span></span>  
 <span data-ttu-id="1169a-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1169a-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1169a-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1169a-111">See also</span></span>

- [<span data-ttu-id="1169a-112">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="1169a-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
