---
title: Metodo ISymUnmanagedReader::GetMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab6228866434b35525b16e97b8cba718b849dea1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213207"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="de29e-102">Metodo ISymUnmanagedReader::GetMethod</span><span class="sxs-lookup"><span data-stu-id="de29e-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="de29e-103">Ottiene un metodo del lettore di simboli, dato un token del metodo.</span><span class="sxs-lookup"><span data-stu-id="de29e-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de29e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="de29e-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de29e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="de29e-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="de29e-106">[in] Il token del metodo.</span><span class="sxs-lookup"><span data-stu-id="de29e-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="de29e-107">[out] Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="de29e-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de29e-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="de29e-108">Return Value</span></span>  
 <span data-ttu-id="de29e-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="de29e-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de29e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="de29e-110">Requirements</span></span>  
 <span data-ttu-id="de29e-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="de29e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de29e-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de29e-112">See also</span></span>

- [<span data-ttu-id="de29e-113">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="de29e-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
