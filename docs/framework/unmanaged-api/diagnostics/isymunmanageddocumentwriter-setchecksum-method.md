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
ms.openlocfilehash: d7a3fcd34f8cab6fa3c2949a4ee3270189b3dc77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730035"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="13ba6-102">Metodo ISymUnmanagedDocumentWriter::SetCheckSum</span><span class="sxs-lookup"><span data-stu-id="13ba6-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="13ba6-103">Imposta le informazioni di checksum.</span><span class="sxs-lookup"><span data-stu-id="13ba6-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13ba6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13ba6-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13ba6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="13ba6-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="13ba6-106">[in] Il GUID che rappresenta l'identificatore dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="13ba6-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="13ba6-107">[in] Oggetto `ULONG32` che indica la dimensione, espressa in byte, del `checkSum` buffer.</span><span class="sxs-lookup"><span data-stu-id="13ba6-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="13ba6-108">[in] Buffer che archivia le informazioni di checksum.</span><span class="sxs-lookup"><span data-stu-id="13ba6-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13ba6-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="13ba6-109">Return Value</span></span>  
 <span data-ttu-id="13ba6-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="13ba6-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13ba6-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13ba6-111">Requirements</span></span>  
 <span data-ttu-id="13ba6-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="13ba6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ba6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13ba6-113">See also</span></span>
- [<span data-ttu-id="13ba6-114">Interfaccia ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="13ba6-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
