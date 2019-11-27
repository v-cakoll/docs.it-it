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
ms.openlocfilehash: 048d784a55fd7c29c837a54fbd5adcdcf62a7a2c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448854"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="1b5f7-102">Metodo ISymUnmanagedMethod::GetToken</span><span class="sxs-lookup"><span data-stu-id="1b5f7-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="1b5f7-103">Restituisce il token di metadati per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="1b5f7-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b5f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b5f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b5f7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b5f7-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="1b5f7-106">out Puntatore a un `mdMethodDef` che riceve la dimensione, in caratteri, del buffer necessario per contenere i metadati.</span><span class="sxs-lookup"><span data-stu-id="1b5f7-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b5f7-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1b5f7-107">Return Value</span></span>  
 <span data-ttu-id="1b5f7-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1b5f7-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b5f7-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b5f7-109">Requirements</span></span>  
 <span data-ttu-id="1b5f7-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1b5f7-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b5f7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b5f7-111">See also</span></span>

- [<span data-ttu-id="1b5f7-112">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="1b5f7-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
