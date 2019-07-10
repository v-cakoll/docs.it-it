---
title: Metodo ISymUnmanagedDocument::GetLanguageVendor
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f5140462ae3c869d58187351d2e0ff11f7b6e179
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776685"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="fa60a-102">Metodo ISymUnmanagedDocument::GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="fa60a-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="fa60a-103">Ottiene il fornitore di linguaggio di questo documento.</span><span class="sxs-lookup"><span data-stu-id="fa60a-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa60a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa60a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa60a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fa60a-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="fa60a-106">[out] Puntatore a una variabile che riceve il fornitore del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="fa60a-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa60a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fa60a-107">Return Value</span></span>  
 <span data-ttu-id="fa60a-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fa60a-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa60a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa60a-109">See also</span></span>

- [<span data-ttu-id="fa60a-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="fa60a-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
