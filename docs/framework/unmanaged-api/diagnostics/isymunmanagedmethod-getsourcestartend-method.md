---
title: Metodo ISymUnmanagedMethod::GetSourceStartEnd
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d9a02ea338dd2c1366256434eacda51327b7d5f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479467"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="e7a30-102">Metodo ISymUnmanagedMethod::GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="e7a30-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="e7a30-103">Ottiene le posizioni del documento iniziale e finale per l'origine di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="e7a30-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="e7a30-104">La prima posizione della matrice è l'inizio e la seconda posizione matrice corrisponde alla fine.</span><span class="sxs-lookup"><span data-stu-id="e7a30-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7a30-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e7a30-105">Syntax</span></span>  
  
```  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7a30-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e7a30-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="e7a30-107">[in] Le iniziali e finali documenti di origine.</span><span class="sxs-lookup"><span data-stu-id="e7a30-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="e7a30-108">[in] Le righe iniziali e finali nel corrispondente dei documenti di origine.</span><span class="sxs-lookup"><span data-stu-id="e7a30-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="e7a30-109">[in] Le colonne iniziali e finali nel corrispondente dei documenti di origine.</span><span class="sxs-lookup"><span data-stu-id="e7a30-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e7a30-110">[out] `true` se le posizioni sono state definite; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e7a30-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7a30-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e7a30-111">Return Value</span></span>  
 <span data-ttu-id="e7a30-112">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e7a30-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7a30-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e7a30-113">Requirements</span></span>  
 <span data-ttu-id="e7a30-114">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e7a30-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a30-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7a30-115">See also</span></span>
- [<span data-ttu-id="e7a30-116">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="e7a30-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
