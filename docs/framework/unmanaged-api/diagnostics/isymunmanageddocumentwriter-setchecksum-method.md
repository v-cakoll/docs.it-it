---
title: Metodo ISymUnmanagedDocumentWriter::SetCheckSum
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac3daccfade4f5ae10fe2ebbf83a7a11af34b89b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196983"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="ca2c4-102">Metodo ISymUnmanagedDocumentWriter::SetCheckSum</span><span class="sxs-lookup"><span data-stu-id="ca2c4-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="ca2c4-103">Imposta le informazioni di checksum.</span><span class="sxs-lookup"><span data-stu-id="ca2c4-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca2c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca2c4-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca2c4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ca2c4-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="ca2c4-106">[in] Il GUID che rappresenta l'identificatore dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="ca2c4-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="ca2c4-107">[in] Oggetto `ULONG32` che indica la dimensione, espressa in byte, del `checkSum` buffer.</span><span class="sxs-lookup"><span data-stu-id="ca2c4-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="ca2c4-108">[in] Buffer che archivia le informazioni di checksum.</span><span class="sxs-lookup"><span data-stu-id="ca2c4-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca2c4-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ca2c4-109">Return Value</span></span>  
 <span data-ttu-id="ca2c4-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ca2c4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca2c4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca2c4-111">Requirements</span></span>  
 <span data-ttu-id="ca2c4-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ca2c4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca2c4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca2c4-113">See also</span></span>

- [<span data-ttu-id="ca2c4-114">Interfaccia ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="ca2c4-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
