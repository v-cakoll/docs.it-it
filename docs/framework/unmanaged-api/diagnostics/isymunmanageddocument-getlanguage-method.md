---
title: Metodo ISymUnmanagedDocument::GetLanguage
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguage
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguage
helpviewer_keywords:
- ISymUnmanagedDocument::GetLanguage method [.NET Framework debugging]
- GetLanguage method [.NET Framework debugging]
ms.assetid: c6639418-e9f2-4a99-8ce2-ec9876e0bc79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 167eb9ae550454afee05cf1e724ba4afa4f95430
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776730"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="8c604-102">Metodo ISymUnmanagedDocument::GetLanguage</span><span class="sxs-lookup"><span data-stu-id="8c604-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="8c604-103">Ottiene l'identificatore di lingua di questo documento</span><span class="sxs-lookup"><span data-stu-id="8c604-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c604-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c604-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c604-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8c604-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8c604-106">[out] Puntatore a una variabile che riceve l'identificatore di lingua.</span><span class="sxs-lookup"><span data-stu-id="8c604-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c604-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8c604-107">Return Value</span></span>  
 <span data-ttu-id="8c604-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8c604-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c604-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c604-109">See also</span></span>

- [<span data-ttu-id="8c604-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="8c604-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
