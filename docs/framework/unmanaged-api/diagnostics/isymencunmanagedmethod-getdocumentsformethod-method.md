---
title: Metodo ISymENCUnmanagedMethod::GetDocumentsForMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
ms.openlocfilehash: 89be772ee3d8a6fc5acb74d5ebe6d3c691764f89
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441955"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="7e48b-102">Metodo ISymENCUnmanagedMethod::GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="7e48b-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="7e48b-103">Ottiene i documenti in cui questo metodo contiene righe.</span><span class="sxs-lookup"><span data-stu-id="7e48b-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e48b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e48b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e48b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7e48b-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="7e48b-106">in Lunghezza del buffer a cui punta `pcDocs` .</span><span class="sxs-lookup"><span data-stu-id="7e48b-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="7e48b-107">out Puntatore a un oggetto `ULONG32` che riceve la dimensione, in caratteri, del buffer necessario per contenere i documenti.</span><span class="sxs-lookup"><span data-stu-id="7e48b-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="7e48b-108">in Buffer che contiene i documenti.</span><span class="sxs-lookup"><span data-stu-id="7e48b-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e48b-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7e48b-109">Return Value</span></span>  
 <span data-ttu-id="7e48b-110">S_OK se il metodo ha esito positivo; in caso contrario, un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="7e48b-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e48b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e48b-111">Requirements</span></span>  
 <span data-ttu-id="7e48b-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7e48b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e48b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e48b-113">See also</span></span>

- [<span data-ttu-id="7e48b-114">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="7e48b-114">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
