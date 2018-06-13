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
ms.openlocfilehash: 103444e0b4b17b6384473eac714fba025cee9a55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426542"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="1df54-102">Metodo ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount</span><span class="sxs-lookup"><span data-stu-id="1df54-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="1df54-103">Ottiene un conteggio delle informazioni di ricerca di simboli.</span><span class="sxs-lookup"><span data-stu-id="1df54-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1df54-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1df54-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1df54-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1df54-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="1df54-106">] out] un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere le informazioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="1df54-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1df54-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1df54-107">Return Value</span></span>  
 <span data-ttu-id="1df54-108">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1df54-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1df54-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1df54-109">Requirements</span></span>  
 <span data-ttu-id="1df54-110">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1df54-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1df54-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1df54-111">See Also</span></span>  
 [<span data-ttu-id="1df54-112">Interfaccia ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="1df54-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
