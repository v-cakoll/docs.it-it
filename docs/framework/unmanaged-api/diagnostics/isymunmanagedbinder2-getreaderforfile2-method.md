---
title: Metodo ISymUnmanagedBinder2::GetReaderForFile2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
ms.openlocfilehash: 97b9fa537fdd9147d6d9eda036013add5393e33c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441708"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="807b5-102">Metodo ISymUnmanagedBinder2::GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="807b5-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="807b5-103">Data un'interfaccia di metadati e un nome file, restituisce l'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) corretta che leggerà i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="807b5-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="807b5-104">Questo metodo fornisce una ricerca più completa del file del database di programma (PDB) rispetto al metodo [ISymUnmanagedBinder:: GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="807b5-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="807b5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="807b5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="807b5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="807b5-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="807b5-107">in Puntatore all'interfaccia di importazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="807b5-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="807b5-108">in Puntatore al nome del file.</span><span class="sxs-lookup"><span data-stu-id="807b5-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="807b5-109">in Puntatore al percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="807b5-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="807b5-110">in Valore dell'enumerazione [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md) che specifica i criteri da utilizzare durante la ricerca di un lettore di simboli.</span><span class="sxs-lookup"><span data-stu-id="807b5-110">[in] A value of the [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="807b5-111">out Puntatore impostato sull'interfaccia [ISymUnmanagedReader](isymunmanagedreader-interface.md) restituita.</span><span class="sxs-lookup"><span data-stu-id="807b5-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="807b5-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="807b5-112">Return Value</span></span>  
 <span data-ttu-id="807b5-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="807b5-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="807b5-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="807b5-114">Requirements</span></span>  
 <span data-ttu-id="807b5-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="807b5-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="807b5-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="807b5-116">Remarks</span></span>  
 <span data-ttu-id="807b5-117">Questa versione del metodo può cercare il file PDB in aree diverse da destra accanto al modulo.</span><span class="sxs-lookup"><span data-stu-id="807b5-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="807b5-118">I criteri di ricerca possono essere controllati combinando [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="807b5-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="807b5-119">Ad esempio, `AllowReferencePathAccess | AllowSymbolServerAccess` Cerca il PDB accanto al file eseguibile e in un server di simboli, ma non esegue una query sul Registro di sistema o usa il percorso nel file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="807b5-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="807b5-120">Se `searchPath` viene specificato il parametro, verrà sempre eseguita la ricerca di tali directory.</span><span class="sxs-lookup"><span data-stu-id="807b5-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="807b5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="807b5-121">See also</span></span>

- [<span data-ttu-id="807b5-122">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="807b5-122">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="807b5-123">Metodo GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="807b5-123">GetReaderForFile Method</span></span>](isymunmanagedbinder-getreaderforfile-method.md)
