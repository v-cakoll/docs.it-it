---
title: Metodo ISymENCUnmanagedMethod::GetLineFromOffset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod.GetLineFromOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2f18357b3a58a5409da93d4d2491997e9ca1cc70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a><span data-ttu-id="09bc0-102">Metodo ISymENCUnmanagedMethod::GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="09bc0-102">ISymENCUnmanagedMethod::GetLineFromOffset Method</span></span>
<span data-ttu-id="09bc0-103">Ottiene le informazioni sulla riga associate a un offset.</span><span class="sxs-lookup"><span data-stu-id="09bc0-103">Gets the line information associated with an offset.</span></span> <span data-ttu-id="09bc0-104">Se il parametro di offset (`dwOffset`) non è un punto di sequenza, questo metodo ottiene le informazioni sulla riga associate all'offset precedente.</span><span class="sxs-lookup"><span data-stu-id="09bc0-104">If the offset parameter (`dwOffset`) is not a sequence point, this method gets the line information associated with the previous offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09bc0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09bc0-105">Syntax</span></span>  
  
```  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09bc0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="09bc0-106">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="09bc0-107">[in] Oggetto `ULONG32` che contiene l'offset.</span><span class="sxs-lookup"><span data-stu-id="09bc0-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `pline`  
 <span data-ttu-id="09bc0-108">[out] Un puntatore a un `ULONG32` che riceve la riga.</span><span class="sxs-lookup"><span data-stu-id="09bc0-108">[out] A pointer to a `ULONG32` that receives the line.</span></span>  
  
 `pcolumn`  
 <span data-ttu-id="09bc0-109">[out] Un puntatore a un `ULONG32` che riceve la colonna.</span><span class="sxs-lookup"><span data-stu-id="09bc0-109">[out] A pointer to a `ULONG32` that receives the column.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="09bc0-110">[out] Un puntatore a un `ULONG32` che riceve la riga finale.</span><span class="sxs-lookup"><span data-stu-id="09bc0-110">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
 `pendColumn`  
 <span data-ttu-id="09bc0-111">[out] Un puntatore a un `ULONG32` che riceve la colonna finale.</span><span class="sxs-lookup"><span data-stu-id="09bc0-111">[out] A pointer to a `ULONG32` that receives the end column.</span></span>  
  
 `pdwStartOffset`  
 <span data-ttu-id="09bc0-112">[out] Un puntatore a un `ULONG32` che riceve il punto di sequenza associato.</span><span class="sxs-lookup"><span data-stu-id="09bc0-112">[out] A pointer to a `ULONG32` that receives the associated sequence point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09bc0-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="09bc0-113">Return Value</span></span>  
 <span data-ttu-id="09bc0-114">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="09bc0-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09bc0-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09bc0-115">Requirements</span></span>  
 <span data-ttu-id="09bc0-116">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="09bc0-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09bc0-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09bc0-117">See Also</span></span>  
 [<span data-ttu-id="09bc0-118">ISymENCUnmanagedMethod (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="09bc0-118">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
