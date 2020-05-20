---
title: Metodo ISymUnmanagedDocument::GetSourceLength
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
ms.openlocfilehash: e84639c1d63e6935b9b363f01c12bf0fbd3390e3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615618"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="9872f-102">Metodo ISymUnmanagedDocument::GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="9872f-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="9872f-103">Recupera la lunghezza, in byte, dell'origine incorporata.</span><span class="sxs-lookup"><span data-stu-id="9872f-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9872f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9872f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9872f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9872f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="9872f-106">out Puntatore a una variabile che indica la lunghezza, in byte, dell'origine incorporata.</span><span class="sxs-lookup"><span data-stu-id="9872f-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9872f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9872f-107">Return Value</span></span>  
 <span data-ttu-id="9872f-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9872f-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9872f-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9872f-109">See also</span></span>

- [<span data-ttu-id="9872f-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="9872f-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
