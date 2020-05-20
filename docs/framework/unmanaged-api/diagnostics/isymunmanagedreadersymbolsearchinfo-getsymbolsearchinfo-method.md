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
ms.openlocfilehash: 2b5a42c89e0e3efed61b1b471c227e0df85a51aa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614903"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="8a37b-102">Metodo ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="8a37b-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="8a37b-103">Ottiene le informazioni di ricerca sui simboli.</span><span class="sxs-lookup"><span data-stu-id="8a37b-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a37b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a37b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a37b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8a37b-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="8a37b-106">in Oggetto `ULONG32` che indica le dimensioni di `rgpSearchInfo` .</span><span class="sxs-lookup"><span data-stu-id="8a37b-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="8a37b-107">out Puntatore a un oggetto `ULONG32` che riceve le dimensioni del buffer necessarie per contenere le informazioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="8a37b-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="8a37b-108">out Puntatore impostato sull'interfaccia [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) restituita.</span><span class="sxs-lookup"><span data-stu-id="8a37b-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a37b-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8a37b-109">Return Value</span></span>  
 <span data-ttu-id="8a37b-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="8a37b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a37b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a37b-111">Requirements</span></span>  
 <span data-ttu-id="8a37b-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8a37b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a37b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a37b-113">See also</span></span>

- [<span data-ttu-id="8a37b-114">Interfaccia ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="8a37b-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)
