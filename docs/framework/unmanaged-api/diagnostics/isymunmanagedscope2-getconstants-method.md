---
title: Metodo ISymUnmanagedScope2::GetConstants
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb3f5926677577bbc0bb14413c5d70150ef25152
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778049"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="e54d0-102">Metodo ISymUnmanagedScope2::GetConstants</span><span class="sxs-lookup"><span data-stu-id="e54d0-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="e54d0-103">Ottiene le costanti locali definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="e54d0-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e54d0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e54d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e54d0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e54d0-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="e54d0-106">[in] La lunghezza del buffer che il `pcConstants` punta il parametro.</span><span class="sxs-lookup"><span data-stu-id="e54d0-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="e54d0-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere le costanti.</span><span class="sxs-lookup"><span data-stu-id="e54d0-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="e54d0-108">[out] Buffer che archivia le costanti.</span><span class="sxs-lookup"><span data-stu-id="e54d0-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e54d0-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e54d0-109">Return Value</span></span>  
 <span data-ttu-id="e54d0-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e54d0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e54d0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e54d0-111">Requirements</span></span>  
 <span data-ttu-id="e54d0-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e54d0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e54d0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e54d0-113">See also</span></span>

- [<span data-ttu-id="e54d0-114">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="e54d0-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
