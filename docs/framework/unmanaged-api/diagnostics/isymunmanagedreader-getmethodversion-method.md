---
title: Metodo ISymUnmanagedReader::GetMethodVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 364742957d16f12508d2df6f4cd7f50d7956d4cb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479454"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="4bce0-102">Metodo ISymUnmanagedReader::GetMethodVersion</span><span class="sxs-lookup"><span data-stu-id="4bce0-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="4bce0-103">Ottiene la versione del metodo.</span><span class="sxs-lookup"><span data-stu-id="4bce0-103">Gets the method version.</span></span> <span data-ttu-id="4bce0-104">La versione del metodo inizia da 1 e viene incrementata ogni volta che il metodo viene ricompilato.</span><span class="sxs-lookup"><span data-stu-id="4bce0-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="4bce0-105">La ricompilazione può verificarsi senza modifiche al metodo.</span><span class="sxs-lookup"><span data-stu-id="4bce0-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bce0-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4bce0-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bce0-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="4bce0-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="4bce0-108">[in] Il metodo per cui ottenere la versione.</span><span class="sxs-lookup"><span data-stu-id="4bce0-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="4bce0-109">[out] Puntatore a una variabile che riceve la versione del metodo.</span><span class="sxs-lookup"><span data-stu-id="4bce0-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bce0-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4bce0-110">Return Value</span></span>  
 <span data-ttu-id="4bce0-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="4bce0-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bce0-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4bce0-112">Requirements</span></span>  
 <span data-ttu-id="4bce0-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4bce0-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bce0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bce0-114">See also</span></span>
- [<span data-ttu-id="4bce0-115">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="4bce0-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
