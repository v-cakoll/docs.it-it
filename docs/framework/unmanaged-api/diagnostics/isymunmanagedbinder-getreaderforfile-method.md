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
ms.openlocfilehash: c4416e8e4395c4e1967155310d12a1eb68c42d83
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441734"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="184a2-102">Metodo ISymUnmanagedBinder::GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="184a2-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="184a2-103">Data un'interfaccia di metadati e un nome file, restituisce l'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) corretta che leggerà i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="184a2-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="184a2-104">Questo metodo consente di aprire il file del database di programma (PDB) solo se è accanto al file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="184a2-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="184a2-105">Questa modifica è stata apportata per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="184a2-105">This change has been made for security purposes.</span></span> <span data-ttu-id="184a2-106">Se è necessaria una ricerca più completa per il file PDB, usare il metodo [ISymUnmanagedBinder2:: GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="184a2-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="184a2-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="184a2-107">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="184a2-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="184a2-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="184a2-109">in Puntatore all'interfaccia di importazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="184a2-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="184a2-110">in Puntatore al nome del file.</span><span class="sxs-lookup"><span data-stu-id="184a2-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="184a2-111">in Puntatore al percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="184a2-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="184a2-112">out Puntatore impostato sull'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) restituita.</span><span class="sxs-lookup"><span data-stu-id="184a2-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="184a2-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="184a2-113">Return Value</span></span>  
 <span data-ttu-id="184a2-114">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="184a2-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="184a2-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="184a2-115">Requirements</span></span>  
 <span data-ttu-id="184a2-116">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="184a2-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="184a2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="184a2-117">See also</span></span>

- [<span data-ttu-id="184a2-118">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="184a2-118">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="184a2-119">Metodo GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="184a2-119">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)
