---
title: Metodo ISymENCUnmanagedMethod::GetDocumentsForMethodCount
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethodCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount
helpviewer_keywords:
- GetDocumentsForMethodCount method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethodCount method [.NET Framework debugging]
ms.assetid: cc1a823a-3ff3-4a33-b641-96edc93d2b17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3c7f7e06822f419282209ac39d4cbd46e600a66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424989"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="ab16e-102">Metodo ISymENCUnmanagedMethod::GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="ab16e-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="ab16e-103">Ottiene il numero di documenti che questo metodo è incluse righe.</span><span class="sxs-lookup"><span data-stu-id="ab16e-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab16e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab16e-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab16e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ab16e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ab16e-106">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere i documenti.</span><span class="sxs-lookup"><span data-stu-id="ab16e-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab16e-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ab16e-107">Return Value</span></span>  
 <span data-ttu-id="ab16e-108">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ab16e-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab16e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab16e-109">Requirements</span></span>  
 <span data-ttu-id="ab16e-110">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ab16e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab16e-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab16e-111">See Also</span></span>  
 [<span data-ttu-id="ab16e-112">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="ab16e-112">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
