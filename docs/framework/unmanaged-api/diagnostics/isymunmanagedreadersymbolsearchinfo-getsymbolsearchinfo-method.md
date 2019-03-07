---
title: Metodo ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cbb290314328023c95d0028dd90687b1a6926ff5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501071"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="fa11a-102">Metodo ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="fa11a-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="fa11a-103">Ottiene informazioni sui simboli di ricerca.</span><span class="sxs-lookup"><span data-stu-id="fa11a-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa11a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa11a-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa11a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa11a-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="fa11a-106">[in] Oggetto `ULONG32` che indica le dimensioni di `rgpSearchInfo`.</span><span class="sxs-lookup"><span data-stu-id="fa11a-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="fa11a-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere le informazioni sulla ricerca.</span><span class="sxs-lookup"><span data-stu-id="fa11a-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="fa11a-108">[out] Un puntatore che viene impostato sull'oggetto restituito [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="fa11a-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa11a-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fa11a-109">Return Value</span></span>  
 <span data-ttu-id="fa11a-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="fa11a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa11a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fa11a-111">Requirements</span></span>  
 <span data-ttu-id="fa11a-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fa11a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa11a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa11a-113">See also</span></span>
- [<span data-ttu-id="fa11a-114">Interfaccia ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="fa11a-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
