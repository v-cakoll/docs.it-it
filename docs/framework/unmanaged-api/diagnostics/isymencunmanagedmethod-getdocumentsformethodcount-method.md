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
ms.openlocfilehash: ef1b8dce5c84382a9039787d2205f1ac8ccbc5bc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166465"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="7b944-102">Metodo ISymENCUnmanagedMethod::GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="7b944-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="7b944-103">Ottiene il numero di documenti che questo metodo è incluse righe.</span><span class="sxs-lookup"><span data-stu-id="7b944-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b944-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b944-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b944-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b944-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7b944-106">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere i documenti.</span><span class="sxs-lookup"><span data-stu-id="7b944-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b944-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7b944-107">Return Value</span></span>  
 <span data-ttu-id="7b944-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="7b944-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b944-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b944-109">Requirements</span></span>  
 <span data-ttu-id="7b944-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7b944-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b944-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b944-111">See also</span></span>

- [<span data-ttu-id="7b944-112">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="7b944-112">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
