---
title: Metodo ISymUnmanagedBinder2::GetReaderForFile2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 270a154c40b85ad4774bececf12685393f4d6c58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="4f98d-102">Metodo ISymUnmanagedBinder2::GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="4f98d-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="4f98d-103">Dato un'interfaccia di metadati e un nome di file, restituisce la corretta <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaccia che verrà letti i simboli di debug associati al modulo.</span><span class="sxs-lookup"><span data-stu-id="4f98d-103">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="4f98d-104">Questo metodo esegue una ricerca più completa per il file di programma (PDB) di database più di [ISymUnmanagedBinder::](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="4f98d-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f98d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f98d-105">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f98d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f98d-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="4f98d-107">[in] Un puntatore all'interfaccia di importazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="4f98d-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="4f98d-108">[in] Puntatore al nome del file.</span><span class="sxs-lookup"><span data-stu-id="4f98d-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="4f98d-109">[in] Puntatore al percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="4f98d-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="4f98d-110">[in] Il valore di [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumerazione che specifica i criteri da utilizzare quando si esegue una ricerca di un lettore di simboli.</span><span class="sxs-lookup"><span data-stu-id="4f98d-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="4f98d-111">[out] Un puntatore che viene impostato sull'oggetto restituito <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4f98d-111">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f98d-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4f98d-112">Return Value</span></span>  
 <span data-ttu-id="4f98d-113">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="4f98d-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f98d-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f98d-114">Requirements</span></span>  
 <span data-ttu-id="4f98d-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4f98d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f98d-116">Note</span><span class="sxs-lookup"><span data-stu-id="4f98d-116">Remarks</span></span>  
 <span data-ttu-id="4f98d-117">Questa versione del metodo possibile cercare il file PDB in aree diverse da subito dopo il modulo.</span><span class="sxs-lookup"><span data-stu-id="4f98d-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="4f98d-118">I criteri della ricerca possono essere controllati combinando [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4f98d-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="4f98d-119">Ad esempio, `AllowReferencePathAccess | AllowSymbolServerAccess` Cerca il file PDB accanto al file eseguibile e su un server di simboli, ma non eseguire una query del Registro di sistema o utilizzare il percorso del file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="4f98d-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="4f98d-120">Se il `searchPath` parametro viene specificato, verranno cercate sempre tali directory.</span><span class="sxs-lookup"><span data-stu-id="4f98d-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f98d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f98d-121">See Also</span></span>  
 [<span data-ttu-id="4f98d-122">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="4f98d-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="4f98d-123">Metodo GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="4f98d-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
