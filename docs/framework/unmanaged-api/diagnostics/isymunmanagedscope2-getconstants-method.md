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
ms.openlocfilehash: 45268929b6e9ad6ac6423aa0fa2b7b5022bc9179
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176617"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="34ad6-102">Metodo ISymUnmanagedScope2::GetConstants</span><span class="sxs-lookup"><span data-stu-id="34ad6-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="34ad6-103">Ottiene le costanti locali definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="34ad6-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34ad6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34ad6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34ad6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="34ad6-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="34ad6-106">[in] Lunghezza del buffer a `pcConstants` cui punta il parametro.</span><span class="sxs-lookup"><span data-stu-id="34ad6-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="34ad6-107">[fuori] Puntatore a `ULONG32` un che riceve la dimensione, in caratteri, del buffer necessario per contenere le costanti.</span><span class="sxs-lookup"><span data-stu-id="34ad6-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="34ad6-108">[fuori] Buffer in cui sono archiviate le costanti.</span><span class="sxs-lookup"><span data-stu-id="34ad6-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34ad6-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="34ad6-109">Return Value</span></span>  
 <span data-ttu-id="34ad6-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="34ad6-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34ad6-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34ad6-111">Requirements</span></span>  
 <span data-ttu-id="34ad6-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="34ad6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34ad6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34ad6-113">See also</span></span>

- [<span data-ttu-id="34ad6-114">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="34ad6-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
