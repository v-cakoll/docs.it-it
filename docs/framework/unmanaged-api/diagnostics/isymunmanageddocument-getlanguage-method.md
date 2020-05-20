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
ms.openlocfilehash: 084f3ae12d906f5e80fdb86e65b09d2371fd246b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614591"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="b2a0b-102">Metodo ISymUnmanagedDocument::GetLanguage</span><span class="sxs-lookup"><span data-stu-id="b2a0b-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="b2a0b-103">Ottiene l'identificatore di lingua di questo documento.</span><span class="sxs-lookup"><span data-stu-id="b2a0b-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2a0b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2a0b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2a0b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b2a0b-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b2a0b-106">out Puntatore a una variabile che riceve l'identificatore della lingua.</span><span class="sxs-lookup"><span data-stu-id="b2a0b-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2a0b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b2a0b-107">Return Value</span></span>  
 <span data-ttu-id="b2a0b-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b2a0b-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a0b-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2a0b-109">See also</span></span>

- [<span data-ttu-id="b2a0b-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="b2a0b-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
