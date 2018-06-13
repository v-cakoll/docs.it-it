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
ms.openlocfilehash: db3e9cfa73672920ff70d9128541a8f513fca00f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432656"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="75b5c-102">Metodo ISymENCUnmanagedMethod::GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="75b5c-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="75b5c-103">Ottiene il nome del file per la riga associata a un offset.</span><span class="sxs-lookup"><span data-stu-id="75b5c-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75b5c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75b5c-104">Syntax</span></span>  
  
```  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75b5c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="75b5c-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="75b5c-106">[in] Oggetto `ULONG32` che contiene l'offset.</span><span class="sxs-lookup"><span data-stu-id="75b5c-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="75b5c-107">[in] Oggetto `ULONG32` che indica le dimensioni del `szName` buffer.</span><span class="sxs-lookup"><span data-stu-id="75b5c-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="75b5c-108">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere i nomi dei file.</span><span class="sxs-lookup"><span data-stu-id="75b5c-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="75b5c-109">[out] Buffer che contiene i nomi dei file.</span><span class="sxs-lookup"><span data-stu-id="75b5c-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75b5c-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="75b5c-110">Return Value</span></span>  
 <span data-ttu-id="75b5c-111">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="75b5c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75b5c-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75b5c-112">Requirements</span></span>  
 <span data-ttu-id="75b5c-113">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="75b5c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75b5c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75b5c-114">See Also</span></span>  
 [<span data-ttu-id="75b5c-115">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="75b5c-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
