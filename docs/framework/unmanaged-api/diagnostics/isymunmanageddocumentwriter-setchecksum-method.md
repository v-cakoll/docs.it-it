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
ms.openlocfilehash: 59ec4d9f39362f563312a9ed75bb1ab5cede799d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484030"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="d4e77-102">Metodo ISymUnmanagedDocumentWriter::SetCheckSum</span><span class="sxs-lookup"><span data-stu-id="d4e77-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="d4e77-103">Imposta le informazioni di checksum.</span><span class="sxs-lookup"><span data-stu-id="d4e77-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4e77-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4e77-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4e77-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4e77-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="d4e77-106">[in] Il GUID che rappresenta l'identificatore dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="d4e77-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="d4e77-107">[in] Oggetto `ULONG32` che indica la dimensione, espressa in byte, del `checkSum` buffer.</span><span class="sxs-lookup"><span data-stu-id="d4e77-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="d4e77-108">[in] Buffer che archivia le informazioni di checksum.</span><span class="sxs-lookup"><span data-stu-id="d4e77-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4e77-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d4e77-109">Return Value</span></span>  
 <span data-ttu-id="d4e77-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d4e77-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4e77-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4e77-111">Requirements</span></span>  
 <span data-ttu-id="d4e77-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d4e77-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4e77-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4e77-113">See also</span></span>
- [<span data-ttu-id="d4e77-114">Interfaccia ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="d4e77-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
