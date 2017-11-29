---
title: Metodo ISymUnmanagedDocument::GetCheckSum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetCheckSum
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b0b2ce6facf99b44f54e8880d4436ab7fe96e50a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="b13a6-102">Metodo ISymUnmanagedDocument::GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="b13a6-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="b13a6-103">Ottiene il checksum.</span><span class="sxs-lookup"><span data-stu-id="b13a6-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b13a6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b13a6-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b13a6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b13a6-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="b13a6-106">[in] La lunghezza del buffer fornito per il `data` parametro</span><span class="sxs-lookup"><span data-stu-id="b13a6-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="b13a6-107">[out] Le dimensioni e la lunghezza del valore di checksum, in byte.</span><span class="sxs-lookup"><span data-stu-id="b13a6-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="b13a6-108">[out] Buffer che riceve il valore di checksum.</span><span class="sxs-lookup"><span data-stu-id="b13a6-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b13a6-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b13a6-109">Return Value</span></span>  
 <span data-ttu-id="b13a6-110">S_OK se il metodo ha esito positivo. in caso contrario, un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="b13a6-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b13a6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b13a6-111">See Also</span></span>  
 [<span data-ttu-id="b13a6-112">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="b13a6-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
