---
title: Metodo ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
ms.openlocfilehash: 0be7297fbb71302035e71fbbf2c8b5e2a7faa2da
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615293"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="c78a3-102">Metodo ISymUnmanagedSymbolSearchInfo::GetSearchPathLength</span><span class="sxs-lookup"><span data-stu-id="c78a3-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="c78a3-103">Ottiene la lunghezza del percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c78a3-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c78a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c78a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c78a3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c78a3-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="c78a3-106">out Puntatore a un oggetto `ULONG32` che riceve la dimensione, in caratteri, del buffer necessario per contenere la lunghezza del percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c78a3-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c78a3-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c78a3-107">Return Value</span></span>  
 <span data-ttu-id="c78a3-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="c78a3-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c78a3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c78a3-109">Requirements</span></span>  
 <span data-ttu-id="c78a3-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c78a3-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c78a3-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c78a3-111">See also</span></span>

- [<span data-ttu-id="c78a3-112">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="c78a3-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
