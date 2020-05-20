---
title: Metodo ISymUnmanagedVariable::GetSignature
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
ms.openlocfilehash: a3ec0af33f3f1201ce2f6b62291dfc67696fecab
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610444"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="cb055-102">Metodo ISymUnmanagedVariable::GetSignature</span><span class="sxs-lookup"><span data-stu-id="cb055-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="cb055-103">Ottiene la firma di questa variabile.</span><span class="sxs-lookup"><span data-stu-id="cb055-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb055-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb055-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb055-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cb055-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="cb055-106">in Lunghezza del buffer a cui punta il `sig` parametro.</span><span class="sxs-lookup"><span data-stu-id="cb055-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="cb055-107">out Puntatore a un oggetto `ULONG32` che riceve la dimensione, in caratteri, del buffer necessario per contenere la firma.</span><span class="sxs-lookup"><span data-stu-id="cb055-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="cb055-108">out Buffer in cui è archiviata la firma.</span><span class="sxs-lookup"><span data-stu-id="cb055-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb055-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cb055-109">Return Value</span></span>  
 <span data-ttu-id="cb055-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="cb055-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb055-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb055-111">Requirements</span></span>  
 <span data-ttu-id="cb055-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="cb055-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb055-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb055-113">See also</span></span>

- [<span data-ttu-id="cb055-114">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="cb055-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
