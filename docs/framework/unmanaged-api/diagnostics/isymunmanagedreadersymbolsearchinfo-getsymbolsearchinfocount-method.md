---
title: Metodo ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfoCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount
helpviewer_keywords:
- GetSymbolSearchInfoCount method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount method [.NET Framework debugging]
ms.assetid: 4068b6ec-525f-4446-8818-0296178cbd19
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6764fe1472052e2657fd32078abe987b68cf9643
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465894"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="99d93-102">Metodo ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount</span><span class="sxs-lookup"><span data-stu-id="99d93-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="99d93-103">Ottiene un conteggio di informazioni sui simboli di ricerca.</span><span class="sxs-lookup"><span data-stu-id="99d93-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99d93-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99d93-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99d93-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="99d93-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="99d93-106">] out] puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere le informazioni sulla ricerca.</span><span class="sxs-lookup"><span data-stu-id="99d93-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99d93-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="99d93-107">Return Value</span></span>  
 <span data-ttu-id="99d93-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="99d93-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99d93-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="99d93-109">Requirements</span></span>  
 <span data-ttu-id="99d93-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="99d93-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d93-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99d93-111">See also</span></span>
- [<span data-ttu-id="99d93-112">Interfaccia ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="99d93-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
