---
title: Metodo ISymUnmanagedDocument::GetCheckSum
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a60bf279c143559e7410d8dfd8213d3da1d05a6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939906"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="05c23-102">Metodo ISymUnmanagedDocument::GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="05c23-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="05c23-103">Ottiene il checksum.</span><span class="sxs-lookup"><span data-stu-id="05c23-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05c23-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05c23-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05c23-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="05c23-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="05c23-106">[in] La lunghezza del buffer fornito dal `data` parametro</span><span class="sxs-lookup"><span data-stu-id="05c23-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="05c23-107">[out] Le dimensioni e lunghezza del checksum, in byte.</span><span class="sxs-lookup"><span data-stu-id="05c23-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="05c23-108">[out] Buffer che riceve il valore di checksum.</span><span class="sxs-lookup"><span data-stu-id="05c23-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05c23-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="05c23-109">Return Value</span></span>  
 <span data-ttu-id="05c23-110">S_OK se il metodo ha esito positivo; in caso contrario, un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="05c23-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c23-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05c23-111">See also</span></span>

- [<span data-ttu-id="05c23-112">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="05c23-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
