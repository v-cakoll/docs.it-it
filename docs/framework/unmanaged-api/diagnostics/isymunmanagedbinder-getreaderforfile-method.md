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
ms.openlocfilehash: 94cda16466ea5a3d35a478a2ae80281e9414f719
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449354"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="b7b15-102">Metodo ISymUnmanagedBinder::GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="b7b15-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="b7b15-103">Data un'interfaccia di metadati e un nome file, restituisce l'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) corretta che leggerà i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="b7b15-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="b7b15-104">Questo metodo consente di aprire il file del database di programma (PDB) solo se è accanto al file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="b7b15-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="b7b15-105">Questa modifica è stata apportata per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b7b15-105">This change has been made for security purposes.</span></span> <span data-ttu-id="b7b15-106">Se è necessaria una ricerca più completa per il file PDB, usare il metodo [ISymUnmanagedBinder2:: GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b7b15-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7b15-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7b15-107">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7b15-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="b7b15-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="b7b15-109">in Puntatore all'interfaccia di importazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="b7b15-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="b7b15-110">in Puntatore al nome del file.</span><span class="sxs-lookup"><span data-stu-id="b7b15-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="b7b15-111">in Puntatore al percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="b7b15-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="b7b15-112">out Puntatore impostato sull'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) restituita.</span><span class="sxs-lookup"><span data-stu-id="b7b15-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7b15-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b7b15-113">Return Value</span></span>  
 <span data-ttu-id="b7b15-114">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="b7b15-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7b15-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b7b15-115">Requirements</span></span>  
 <span data-ttu-id="b7b15-116">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b7b15-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b15-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7b15-117">See also</span></span>

- [<span data-ttu-id="b7b15-118">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="b7b15-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="b7b15-119">Metodo GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="b7b15-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
