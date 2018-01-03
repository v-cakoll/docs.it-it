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
ms.workload: dotnet
ms.openlocfilehash: 0e4f653ab7b2a1341af8917c6932ea8bdfd64d83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="0294f-102">Metodo ISymUnmanagedDocumentWriter::SetCheckSum</span><span class="sxs-lookup"><span data-stu-id="0294f-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="0294f-103">Imposta le informazioni di checksum.</span><span class="sxs-lookup"><span data-stu-id="0294f-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0294f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0294f-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0294f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0294f-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="0294f-106">[in] GUID che rappresenta l'identificatore dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="0294f-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="0294f-107">[in] Oggetto `ULONG32` che indica le dimensioni, in byte, del `checkSum` buffer.</span><span class="sxs-lookup"><span data-stu-id="0294f-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="0294f-108">[in] Buffer che archivia le informazioni di checksum.</span><span class="sxs-lookup"><span data-stu-id="0294f-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0294f-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0294f-109">Return Value</span></span>  
 <span data-ttu-id="0294f-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="0294f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0294f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0294f-111">Requirements</span></span>  
 <span data-ttu-id="0294f-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0294f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0294f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0294f-113">See Also</span></span>  
 [<span data-ttu-id="0294f-114">Interfaccia ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="0294f-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
