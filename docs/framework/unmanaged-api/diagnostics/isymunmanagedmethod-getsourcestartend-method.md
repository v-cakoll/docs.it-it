---
title: Metodo ISymUnmanagedMethod::GetSourceStartEnd
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2bdc044d4560b616bd6eeb8d642567add1f659f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="cc158-102">Metodo ISymUnmanagedMethod::GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="cc158-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="cc158-103">Ottiene le posizioni di documento di inizio e di fine per l'origine di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="cc158-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="cc158-104">La prima posizione di matrice è l'inizio e la seconda è la fine.</span><span class="sxs-lookup"><span data-stu-id="cc158-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc158-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc158-105">Syntax</span></span>  
  
```  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc158-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="cc158-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="cc158-107">[in] Avvio e chiusura di documenti di origine.</span><span class="sxs-lookup"><span data-stu-id="cc158-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="cc158-108">[in] Documenti di origine iniziali e finali righe corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="cc158-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="cc158-109">[in] Documenti di origine iniziali e finali di colonne corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="cc158-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="cc158-110">[out] `true` Se posizioni sono definite in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="cc158-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc158-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cc158-111">Return Value</span></span>  
 <span data-ttu-id="cc158-112">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="cc158-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc158-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cc158-113">Requirements</span></span>  
 <span data-ttu-id="cc158-114">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cc158-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc158-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc158-115">See Also</span></span>  
 [<span data-ttu-id="cc158-116">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="cc158-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
