---
title: Metodo ISymUnmanagedReader::GetMethodByVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d4bc763d908156f3bbf8998c13073820686903f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132756"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="08fff-102">Metodo ISymUnmanagedReader::GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="08fff-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="08fff-103">Ottiene un metodo del lettore di simboli, dato un token di metodo e un numero di versione di modifica e copia.</span><span class="sxs-lookup"><span data-stu-id="08fff-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="08fff-104">I numeri di versione iniziano da 1 e vengano incrementati ogni volta che il metodo viene modificato in seguito a un'operazione di modifica e copia.</span><span class="sxs-lookup"><span data-stu-id="08fff-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08fff-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08fff-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08fff-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="08fff-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="08fff-107">[in] Il token del metodo.</span><span class="sxs-lookup"><span data-stu-id="08fff-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="08fff-108">[in] La versione del metodo.</span><span class="sxs-lookup"><span data-stu-id="08fff-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="08fff-109">[out] Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="08fff-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08fff-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="08fff-110">Return Value</span></span>  
 <span data-ttu-id="08fff-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="08fff-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08fff-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08fff-112">Requirements</span></span>  
 <span data-ttu-id="08fff-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="08fff-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08fff-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08fff-114">See also</span></span>

- [<span data-ttu-id="08fff-115">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="08fff-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
