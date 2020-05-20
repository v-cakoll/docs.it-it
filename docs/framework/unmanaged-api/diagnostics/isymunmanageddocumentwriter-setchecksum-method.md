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
ms.openlocfilehash: 06a331e24622e0a155d974ca869818a6532baa1f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615540"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="42ba4-102">Metodo ISymUnmanagedDocumentWriter::SetCheckSum</span><span class="sxs-lookup"><span data-stu-id="42ba4-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="42ba4-103">Imposta le informazioni di checksum.</span><span class="sxs-lookup"><span data-stu-id="42ba4-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42ba4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42ba4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42ba4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="42ba4-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="42ba4-106">in GUID che rappresenta l'identificatore dell'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="42ba4-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="42ba4-107">in Oggetto `ULONG32` che indica la dimensione, in byte, del `checkSum` buffer.</span><span class="sxs-lookup"><span data-stu-id="42ba4-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="42ba4-108">in Buffer che archivia le informazioni di checksum.</span><span class="sxs-lookup"><span data-stu-id="42ba4-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42ba4-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="42ba4-109">Return Value</span></span>  
 <span data-ttu-id="42ba4-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="42ba4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42ba4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42ba4-111">Requirements</span></span>  
 <span data-ttu-id="42ba4-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="42ba4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42ba4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42ba4-113">See also</span></span>

- [<span data-ttu-id="42ba4-114">Interfaccia ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="42ba4-114">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)
