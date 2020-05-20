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
ms.openlocfilehash: d096101189d52401c407a4108c9c81e201d3f30d
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441942"
---
# <a name="isymencunmanagedmethodgetdocumentsformethodcount-method"></a><span data-ttu-id="c043f-102">Metodo ISymENCUnmanagedMethod::GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="c043f-102">ISymENCUnmanagedMethod::GetDocumentsForMethodCount Method</span></span>
<span data-ttu-id="c043f-103">Ottiene il numero di documenti in cui questo metodo contiene righe.</span><span class="sxs-lookup"><span data-stu-id="c043f-103">Gets the number of documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c043f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c043f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethodCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c043f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c043f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c043f-106">out Puntatore a un oggetto `ULONG32` che riceve le dimensioni del buffer necessarie per contenere i documenti.</span><span class="sxs-lookup"><span data-stu-id="c043f-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c043f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c043f-107">Return Value</span></span>  
 <span data-ttu-id="c043f-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="c043f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c043f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c043f-109">Requirements</span></span>  
 <span data-ttu-id="c043f-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c043f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c043f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c043f-111">See also</span></span>

- [<span data-ttu-id="c043f-112">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="c043f-112">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
