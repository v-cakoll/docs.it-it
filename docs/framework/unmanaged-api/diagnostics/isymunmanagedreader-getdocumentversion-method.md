---
title: Metodo ISymUnmanagedReader::GetDocumentVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf6a08b17819e3d3cdaa62b0e209fc2064de4a4a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688701"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="c8d1d-102">Metodo ISymUnmanagedReader::GetDocumentVersion</span><span class="sxs-lookup"><span data-stu-id="c8d1d-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="c8d1d-103">Ottiene la versione specificata del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="c8d1d-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="c8d1d-104">La versione del documento inizia da 1 e viene incrementata ogni volta che il documento viene aggiornato usando il [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="c8d1d-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="c8d1d-105">Se il `pbCurrent` parametro è `true`, questa è la versione più recente del documento.</span><span class="sxs-lookup"><span data-stu-id="c8d1d-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8d1d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8d1d-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8d1d-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8d1d-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="c8d1d-108">[in] Il documento specificato.</span><span class="sxs-lookup"><span data-stu-id="c8d1d-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="c8d1d-109">[out] Puntatore a una variabile che riceve la versione del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="c8d1d-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="c8d1d-110">[out] Un puntatore a una variabile che riceve `true` se si tratta della versione più recente del documento, o `false` se non è la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="c8d1d-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8d1d-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c8d1d-111">Return Value</span></span>  
 <span data-ttu-id="c8d1d-112">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="c8d1d-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8d1d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8d1d-113">Requirements</span></span>  
 <span data-ttu-id="c8d1d-114">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c8d1d-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d1d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8d1d-115">See also</span></span>
- [<span data-ttu-id="c8d1d-116">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="c8d1d-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
