---
title: Metodo ISymUnmanagedBinder3::GetReaderFromCallback
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f44d50f6736e0698fd876eedab78dbf41434af4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426316"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="daebe-102">Metodo ISymUnmanagedBinder3::GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="daebe-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="daebe-103">Consente di implementare o fornire mediante callback un `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` per ottenere le informazioni di directory debug dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="daebe-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daebe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="daebe-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="daebe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="daebe-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="daebe-106">[in] Un puntatore all'interfaccia di importazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="daebe-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="daebe-107">[in] Puntatore al nome del file.</span><span class="sxs-lookup"><span data-stu-id="daebe-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="daebe-108">[in] Puntatore al percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="daebe-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="daebe-109">[in] Il valore di [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumerazione che specifica i criteri da utilizzare quando si esegue una ricerca di un lettore di simboli.</span><span class="sxs-lookup"><span data-stu-id="daebe-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="daebe-110">[in] Puntatore alla funzione di callback.</span><span class="sxs-lookup"><span data-stu-id="daebe-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="daebe-111">[out] Un puntatore che viene impostato sull'oggetto restituito [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="daebe-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="daebe-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="daebe-112">Return Value</span></span>  
 <span data-ttu-id="daebe-113">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="daebe-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daebe-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="daebe-114">Requirements</span></span>  
 <span data-ttu-id="daebe-115">**Intestazione:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="daebe-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daebe-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="daebe-116">See Also</span></span>  
 [<span data-ttu-id="daebe-117">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="daebe-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
