---
title: Metodo ISymUnmanagedWriter::Initialize2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71eeeefc594c450d5fb95ebae17e3c1316301278
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481378"
---
# <a name="isymunmanagedwriterinitialize2-method"></a><span data-ttu-id="ab1bc-102">Metodo ISymUnmanagedWriter::Initialize2</span><span class="sxs-lookup"><span data-stu-id="ab1bc-102">ISymUnmanagedWriter::Initialize2 Method</span></span>
<span data-ttu-id="ab1bc-103">Imposta l'interfaccia di emissione dei metadati con il quale verrà associato questo writer e imposta il nome del file di output in cui verranno scritti i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="ab1bc-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span> <span data-ttu-id="ab1bc-104">Questo metodo consente inoltre di impostare la posizione finale del file di database (PDB) del programma.</span><span class="sxs-lookup"><span data-stu-id="ab1bc-104">This method also lets you set the final location of the program database (PDB) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab1bc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab1bc-105">Syntax</span></span>  
  
```  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab1bc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ab1bc-106">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="ab1bc-107">[in] Un puntatore all'interfaccia di emissione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="ab1bc-107">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `tempfilename`  
 <span data-ttu-id="ab1bc-108">[in] Un puntatore a un `WCHAR` che contiene il nome del file in cui vengono scritti i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="ab1bc-108">[in] A pointer to a `WCHAR` that contains the file name to which the debugging symbols are written.</span></span> <span data-ttu-id="ab1bc-109">Se specificato per un writer che non usa i nomi file, il parametro sarà ignorato.</span><span class="sxs-lookup"><span data-stu-id="ab1bc-109">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="ab1bc-110">[in] Se specificato, il writer di simboli genera i simboli nel dato <xref:System.Runtime.InteropServices.ComTypes.IStream> invece che al file specificato nel `filename` parametro.</span><span class="sxs-lookup"><span data-stu-id="ab1bc-110">[in] If specified, the symbol writer emits the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="ab1bc-111">Il parametro `pIStream` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ab1bc-111">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="ab1bc-112">[in] `true` se si tratta di una ricompilazione completa. `false` se si tratta di una compilazione incrementale.</span><span class="sxs-lookup"><span data-stu-id="ab1bc-112">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
 `finalfilename`  
 <span data-ttu-id="ab1bc-113">[in] Un puntatore a un `WCHAR` vale a dire la stringa del percorso per la posizione finale del file PDB.</span><span class="sxs-lookup"><span data-stu-id="ab1bc-113">[in] A pointer to a `WCHAR` that is the path string to the final location of the PDB file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab1bc-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ab1bc-114">Return Value</span></span>  
 <span data-ttu-id="ab1bc-115">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ab1bc-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab1bc-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab1bc-116">Requirements</span></span>  
 <span data-ttu-id="ab1bc-117">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ab1bc-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab1bc-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab1bc-118">See also</span></span>
- [<span data-ttu-id="ab1bc-119">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="ab1bc-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="ab1bc-120">Metodo Initialize</span><span class="sxs-lookup"><span data-stu-id="ab1bc-120">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
