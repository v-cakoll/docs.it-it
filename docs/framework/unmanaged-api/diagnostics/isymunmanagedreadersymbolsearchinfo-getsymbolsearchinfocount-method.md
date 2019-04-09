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
ms.openlocfilehash: 0b59d85227f21bb230333456eda9130416563111
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180531"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="aa8f7-102">Metodo ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount</span><span class="sxs-lookup"><span data-stu-id="aa8f7-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="aa8f7-103">Ottiene un conteggio di informazioni sui simboli di ricerca.</span><span class="sxs-lookup"><span data-stu-id="aa8f7-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa8f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa8f7-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa8f7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aa8f7-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="aa8f7-106">] out] puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere le informazioni sulla ricerca.</span><span class="sxs-lookup"><span data-stu-id="aa8f7-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa8f7-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="aa8f7-107">Return Value</span></span>  
 <span data-ttu-id="aa8f7-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="aa8f7-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa8f7-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa8f7-109">Requirements</span></span>  
 <span data-ttu-id="aa8f7-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="aa8f7-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa8f7-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa8f7-111">See also</span></span>

- [<span data-ttu-id="aa8f7-112">Interfaccia ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="aa8f7-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
