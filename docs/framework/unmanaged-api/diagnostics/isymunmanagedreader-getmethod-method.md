---
title: Metodo ISymUnmanagedReader::GetMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 94c40555ee62bac99cf7cb34378c5b0fcca5104f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="41b37-102">Metodo ISymUnmanagedReader::GetMethod</span><span class="sxs-lookup"><span data-stu-id="41b37-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="41b37-103">Ottiene un metodo del lettore di simboli, dato un token di metodo.</span><span class="sxs-lookup"><span data-stu-id="41b37-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41b37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41b37-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41b37-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="41b37-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="41b37-106">[in] Il token del metodo.</span><span class="sxs-lookup"><span data-stu-id="41b37-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="41b37-107">[out] Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="41b37-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41b37-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="41b37-108">Return Value</span></span>  
 <span data-ttu-id="41b37-109">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="41b37-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41b37-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41b37-110">Requirements</span></span>  
 <span data-ttu-id="41b37-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="41b37-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41b37-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41b37-112">See Also</span></span>  
 [<span data-ttu-id="41b37-113">ISymUnmanagedReader (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="41b37-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
