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
ms.openlocfilehash: cea18fefa2d356cbb5857db5133b1086c38ac6ff
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449175"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="0a04a-102">Metodo ISymUnmanagedDocument::GetLanguage</span><span class="sxs-lookup"><span data-stu-id="0a04a-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="0a04a-103">Gets the language identifier of this document</span><span class="sxs-lookup"><span data-stu-id="0a04a-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a04a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0a04a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a04a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0a04a-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="0a04a-106">[out] A pointer to a variable that receives the language identifier.</span><span class="sxs-lookup"><span data-stu-id="0a04a-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a04a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0a04a-107">Return Value</span></span>  
 <span data-ttu-id="0a04a-108">S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="0a04a-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a04a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a04a-109">See also</span></span>

- [<span data-ttu-id="0a04a-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="0a04a-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
