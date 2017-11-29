---
title: Metodo ISymUnmanagedDocumentWriter::SetCheckSum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocumentWriter.SetCheckSum
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9693b21c2b3819096ec4aeb0a275fccf76307de0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="28e68-102">Metodo ISymUnmanagedDocumentWriter::SetCheckSum</span><span class="sxs-lookup"><span data-stu-id="28e68-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="28e68-103">Imposta le informazioni di checksum.</span><span class="sxs-lookup"><span data-stu-id="28e68-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28e68-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28e68-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28e68-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="28e68-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="28e68-106">[in] GUID che rappresenta l'identificatore dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="28e68-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="28e68-107">[in] Oggetto `ULONG32` che indica le dimensioni, in byte, del `checkSum` buffer.</span><span class="sxs-lookup"><span data-stu-id="28e68-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="28e68-108">[in] Buffer che archivia le informazioni di checksum.</span><span class="sxs-lookup"><span data-stu-id="28e68-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28e68-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="28e68-109">Return Value</span></span>  
 <span data-ttu-id="28e68-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="28e68-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28e68-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28e68-111">Requirements</span></span>  
 <span data-ttu-id="28e68-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="28e68-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e68-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28e68-113">See Also</span></span>  
 [<span data-ttu-id="28e68-114">ISymUnmanagedDocumentWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="28e68-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
