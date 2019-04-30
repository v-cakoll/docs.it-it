---
title: Metodo ISymUnmanagedDocument::GetCheckSumAlgorithmId
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSumAlgorithmId
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId method [.NET Framework debugging]
- GetCheckSumAlgorithmId method [.NET Framework debugging]
ms.assetid: c7f941cd-e25b-4b85-b1ce-5f77c9208fa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f2df98728eec28ffca05b2e246575fc5c882a078
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939881"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="01d0f-102">Metodo ISymUnmanagedDocument::GetCheckSumAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="01d0f-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="01d0f-103">Ottiene l'identificatore dell'algoritmo di checksum, o restituisce un GUID di tutti gli zeri se non sono presenti checksum.</span><span class="sxs-lookup"><span data-stu-id="01d0f-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01d0f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01d0f-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01d0f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="01d0f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="01d0f-106">[out] Puntatore a una variabile che riceve l'identificatore dell'algoritmo di checksum.</span><span class="sxs-lookup"><span data-stu-id="01d0f-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01d0f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="01d0f-107">Return Value</span></span>  
 <span data-ttu-id="01d0f-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="01d0f-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01d0f-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01d0f-109">See also</span></span>

- [<span data-ttu-id="01d0f-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="01d0f-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
