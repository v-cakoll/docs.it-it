---
title: Metodo ISymUnmanagedBinder::GetReaderForFile
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderForFile
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53558e1b76d5bb22ff2af3b8d7d9e4006072775b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734284"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="d5b47-102">Metodo ISymUnmanagedBinder::GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="d5b47-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="d5b47-103">Data un'interfaccia di metadati e un nome di file, restituisce il valore corretto [ISymUnmanagedReader](isymunmanagedreader-interface.md) interfaccia che leggerà i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="d5b47-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="d5b47-104">Questo metodo verrà aperto il file di programma (PDB) del database solo se si trova accanto al file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="d5b47-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="d5b47-105">Per motivi di sicurezza è stata apportata questa modifica.</span><span class="sxs-lookup"><span data-stu-id="d5b47-105">This change has been made for security purposes.</span></span> <span data-ttu-id="d5b47-106">Se occorre una ricerca più completa per il file PDB, usare il [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d5b47-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5b47-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5b47-107">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5b47-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="d5b47-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="d5b47-109">[in] Un puntatore all'interfaccia di importazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="d5b47-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="d5b47-110">[in] Puntatore al nome del file.</span><span class="sxs-lookup"><span data-stu-id="d5b47-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="d5b47-111">[in] Puntatore al percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d5b47-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d5b47-112">[out] Un puntatore che viene impostato sull'oggetto restituito [ISymUnmanagedReader](isymunmanagedreader-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d5b47-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5b47-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d5b47-113">Return Value</span></span>  
 <span data-ttu-id="d5b47-114">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d5b47-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5b47-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d5b47-115">Requirements</span></span>  
 <span data-ttu-id="d5b47-116">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d5b47-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b47-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5b47-117">See also</span></span>
- [<span data-ttu-id="d5b47-118">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="d5b47-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="d5b47-119">Metodo GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="d5b47-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
