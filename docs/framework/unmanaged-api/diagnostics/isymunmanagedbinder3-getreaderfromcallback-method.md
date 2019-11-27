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
ms.openlocfilehash: a0cccc0adfc666cc8e373bc1f89c8f6f97068fde
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449308"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="97c00-102">Metodo ISymUnmanagedBinder3::GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="97c00-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="97c00-103">Consente all'utente di implementare o fornire tramite callback un `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` per ottenere le informazioni della directory di debug dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="97c00-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97c00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97c00-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97c00-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="97c00-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="97c00-106">in Puntatore all'interfaccia di importazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="97c00-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="97c00-107">in Puntatore al nome del file.</span><span class="sxs-lookup"><span data-stu-id="97c00-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="97c00-108">in Puntatore al percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="97c00-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="97c00-109">in Valore dell'enumerazione [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) che specifica i criteri da utilizzare durante la ricerca di un lettore di simboli.</span><span class="sxs-lookup"><span data-stu-id="97c00-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="97c00-110">in Puntatore alla funzione di callback.</span><span class="sxs-lookup"><span data-stu-id="97c00-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="97c00-111">out Puntatore impostato sull'interfaccia [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) restituita.</span><span class="sxs-lookup"><span data-stu-id="97c00-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97c00-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="97c00-112">Return Value</span></span>  
 <span data-ttu-id="97c00-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="97c00-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97c00-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97c00-114">Requirements</span></span>  
 <span data-ttu-id="97c00-115">**Intestazione:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="97c00-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97c00-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97c00-116">See also</span></span>

- [<span data-ttu-id="97c00-117">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="97c00-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
