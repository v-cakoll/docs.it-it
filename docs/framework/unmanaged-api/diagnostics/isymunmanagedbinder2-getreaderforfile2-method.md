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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cea8a322fab6ef76873e668c622ac63e3a3f2862
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428225"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="65640-102">Metodo ISymUnmanagedBinder2::GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="65640-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="65640-103">Dato un'interfaccia di metadati e un nome di file, restituisce la corretta <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaccia che verrà letti i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="65640-103">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="65640-104">Questo metodo esegue una ricerca più completa per il file di programma (PDB) di database più di [ISymUnmanagedBinder::](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="65640-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65640-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65640-105">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65640-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="65640-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="65640-107">[in] Un puntatore all'interfaccia di importazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="65640-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="65640-108">[in] Puntatore al nome del file.</span><span class="sxs-lookup"><span data-stu-id="65640-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="65640-109">[in] Puntatore al percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="65640-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="65640-110">[in] Il valore di [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumerazione che specifica i criteri da utilizzare quando si esegue una ricerca di un lettore di simboli.</span><span class="sxs-lookup"><span data-stu-id="65640-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="65640-111">[out] Un puntatore che viene impostato sull'oggetto restituito <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="65640-111">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65640-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="65640-112">Return Value</span></span>  
 <span data-ttu-id="65640-113">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="65640-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65640-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65640-114">Requirements</span></span>  
 <span data-ttu-id="65640-115">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="65640-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65640-116">Note</span><span class="sxs-lookup"><span data-stu-id="65640-116">Remarks</span></span>  
 <span data-ttu-id="65640-117">Questa versione del metodo possibile cercare il file PDB in aree diverse da subito dopo il modulo.</span><span class="sxs-lookup"><span data-stu-id="65640-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="65640-118">I criteri della ricerca possono essere controllati combinando [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="65640-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="65640-119">Ad esempio, `AllowReferencePathAccess | AllowSymbolServerAccess` Cerca il file PDB accanto al file eseguibile e su un server di simboli, ma non eseguire una query del Registro di sistema o utilizzare il percorso del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="65640-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="65640-120">Se il `searchPath` parametro viene specificato, verranno cercate sempre tali directory.</span><span class="sxs-lookup"><span data-stu-id="65640-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65640-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65640-121">See Also</span></span>  
 [<span data-ttu-id="65640-122">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="65640-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="65640-123">Metodo GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="65640-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
