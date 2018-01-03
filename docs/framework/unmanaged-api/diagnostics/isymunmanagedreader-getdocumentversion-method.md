---
title: Metodo ISymUnmanagedReader::GetDocumentVersion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetDocumentVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2cb0abf887abaac4d7433b52a795beca509ec61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="0ba28-102">Metodo ISymUnmanagedReader::GetDocumentVersion</span><span class="sxs-lookup"><span data-stu-id="0ba28-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="0ba28-103">Ottiene la versione specificata del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="0ba28-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="0ba28-104">La versione del documento inizia da 1 e viene incrementata ogni volta che il documento viene aggiornato mediante la [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="0ba28-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="0ba28-105">Se il `pbCurrent` parametro `true`, si tratta della versione più recente del documento.</span><span class="sxs-lookup"><span data-stu-id="0ba28-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ba28-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ba28-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ba28-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ba28-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="0ba28-108">[in] Il documento specificato.</span><span class="sxs-lookup"><span data-stu-id="0ba28-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="0ba28-109">[out] Puntatore a una variabile che riceve la versione del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="0ba28-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="0ba28-110">[out] Un puntatore a una variabile che riceve `true` se si tratta della versione più recente del documento, o `false` se non è la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="0ba28-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ba28-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0ba28-111">Return Value</span></span>  
 <span data-ttu-id="0ba28-112">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="0ba28-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ba28-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ba28-113">Requirements</span></span>  
 <span data-ttu-id="0ba28-114">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0ba28-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ba28-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ba28-115">See Also</span></span>  
 [<span data-ttu-id="0ba28-116">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="0ba28-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
