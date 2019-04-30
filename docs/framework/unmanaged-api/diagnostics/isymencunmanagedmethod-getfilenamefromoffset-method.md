---
title: Metodo ISymENCUnmanagedMethod::GetFileNameFromOffset
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 494f39855132bc4a9551b78f746517862d285034
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940270"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="4e687-102">Metodo ISymENCUnmanagedMethod::GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="4e687-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="4e687-103">Ottiene il nome del file per la riga associata a un offset.</span><span class="sxs-lookup"><span data-stu-id="4e687-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e687-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e687-104">Syntax</span></span>  
  
```  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e687-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4e687-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="4e687-106">[in] Oggetto `ULONG32` che contiene l'offset.</span><span class="sxs-lookup"><span data-stu-id="4e687-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4e687-107">[in] Oggetto `ULONG32` che indica le dimensioni del `szName` buffer.</span><span class="sxs-lookup"><span data-stu-id="4e687-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4e687-108">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere i nomi dei file.</span><span class="sxs-lookup"><span data-stu-id="4e687-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="4e687-109">[out] Buffer che contiene i nomi dei file.</span><span class="sxs-lookup"><span data-stu-id="4e687-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e687-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4e687-110">Return Value</span></span>  
 <span data-ttu-id="4e687-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="4e687-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e687-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e687-112">Requirements</span></span>  
 <span data-ttu-id="4e687-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4e687-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e687-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e687-114">See also</span></span>

- [<span data-ttu-id="4e687-115">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="4e687-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
