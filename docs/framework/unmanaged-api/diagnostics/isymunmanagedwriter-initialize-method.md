---
title: Metodo ISymUnmanagedWriter::Initialize
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1ea9424c000ad3ae4918181084c89038c2ec8d1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777283"
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="34a48-102">Metodo ISymUnmanagedWriter::Initialize</span><span class="sxs-lookup"><span data-stu-id="34a48-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="34a48-103">Imposta l'interfaccia di emissione dei metadati con il quale verrà associato questo writer e imposta il nome del file di output in cui verranno scritti i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="34a48-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="34a48-104">Questo metodo può essere chiamato una sola volta e deve essere chiamato prima di qualsiasi altro metodo di scrittura.</span><span class="sxs-lookup"><span data-stu-id="34a48-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="34a48-105">Per alcuni writer richiedano un nome di file.</span><span class="sxs-lookup"><span data-stu-id="34a48-105">Some writers may require a file name.</span></span> <span data-ttu-id="34a48-106">Tuttavia, è possibile passare sempre un nome di file a questo metodo senza alcun effetto negativo sul writer che non usano il nome del file.</span><span class="sxs-lookup"><span data-stu-id="34a48-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34a48-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34a48-107">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34a48-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="34a48-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="34a48-109">[in] Un puntatore all'interfaccia di emissione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="34a48-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="34a48-110">[in] Il nome di file in cui vengono scritti i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="34a48-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="34a48-111">Se specificato per un writer che non usa i nomi file, il parametro sarà ignorato.</span><span class="sxs-lookup"><span data-stu-id="34a48-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="34a48-112">[in] Se specificato, il writer di simboli genererà i simboli nel dato <xref:System.Runtime.InteropServices.ComTypes.IStream> invece che al file specificato nel `filename` parametro.</span><span class="sxs-lookup"><span data-stu-id="34a48-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="34a48-113">Il parametro `pIStream` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="34a48-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="34a48-114">[in] `true` se si tratta di una ricompilazione completa. `false` se si tratta di una compilazione incrementale.</span><span class="sxs-lookup"><span data-stu-id="34a48-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34a48-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="34a48-115">Return Value</span></span>  
 <span data-ttu-id="34a48-116">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="34a48-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34a48-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34a48-117">Requirements</span></span>  
 <span data-ttu-id="34a48-118">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="34a48-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a48-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34a48-119">See also</span></span>

- [<span data-ttu-id="34a48-120">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="34a48-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="34a48-121">Metodo Initialize2</span><span class="sxs-lookup"><span data-stu-id="34a48-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
