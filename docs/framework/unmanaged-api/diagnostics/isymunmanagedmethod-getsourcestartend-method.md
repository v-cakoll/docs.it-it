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
ms.openlocfilehash: a75fed4c46ea7e31177ac0446c8fae7805535323
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759431"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="f5cef-102">Metodo ISymUnmanagedMethod::GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="f5cef-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="f5cef-103">Ottiene le posizioni del documento iniziale e finale per l'origine di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="f5cef-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="f5cef-104">La prima posizione della matrice è l'inizio e la seconda posizione matrice corrisponde alla fine.</span><span class="sxs-lookup"><span data-stu-id="f5cef-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5cef-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5cef-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5cef-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f5cef-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="f5cef-107">[in] Le iniziali e finali documenti di origine.</span><span class="sxs-lookup"><span data-stu-id="f5cef-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="f5cef-108">[in] Le righe iniziali e finali nel corrispondente dei documenti di origine.</span><span class="sxs-lookup"><span data-stu-id="f5cef-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="f5cef-109">[in] Le colonne iniziali e finali nel corrispondente dei documenti di origine.</span><span class="sxs-lookup"><span data-stu-id="f5cef-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="f5cef-110">[out] `true` se le posizioni sono state definite; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f5cef-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5cef-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f5cef-111">Return Value</span></span>  
 <span data-ttu-id="f5cef-112">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f5cef-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5cef-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f5cef-113">Requirements</span></span>  
 <span data-ttu-id="f5cef-114">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f5cef-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5cef-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5cef-115">See also</span></span>

- [<span data-ttu-id="f5cef-116">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="f5cef-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
