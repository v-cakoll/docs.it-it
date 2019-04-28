---
title: Metodo ICLRDebuggingLibraryProvider::ProvideLibrary
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f5d44b6497e971e6d1ed030c043b91b88c070b6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697805"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="b2ee7-102">Metodo ICLRDebuggingLibraryProvider::ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="b2ee7-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>
<span data-ttu-id="b2ee7-103">Ottiene un provider di librerie di interfaccia di callback che consente a common language runtime (CLR) le librerie di debug specifiche della versione di individuare e caricare su richiesta.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2ee7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b2ee7-104">Syntax</span></span>  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2ee7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b2ee7-105">Parameters</span></span>  
 `pwszFilename`  
 <span data-ttu-id="b2ee7-106">[in] Nome del modulo richiesto.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-106">[in] The name of the module being requested.</span></span>  
  
 `dwTimestamp`  
 <span data-ttu-id="b2ee7-107">[in] Timestamp data archiviato nell'intestazione COFF dei file PE.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="b2ee7-108">[in] Il `SizeOfImage` campo archiviato nell'intestazione COFF file facoltativo del file PE.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>  
  
 `hModule`  
 <span data-ttu-id="b2ee7-109">[out] L'handle del modulo richiesto.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-109">[out] The handle to the requested module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2ee7-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b2ee7-110">Return Value</span></span>  
 <span data-ttu-id="b2ee7-111">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b2ee7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2ee7-112">HRESULT</span></span>|<span data-ttu-id="b2ee7-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2ee7-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2ee7-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2ee7-114">S_OK</span></span>|<span data-ttu-id="b2ee7-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-115">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="b2ee7-116">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="b2ee7-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2ee7-117">Note</span><span class="sxs-lookup"><span data-stu-id="b2ee7-117">Remarks</span></span>  
 <span data-ttu-id="b2ee7-118">`ProvideLibrary` consente al debugger fornire i moduli necessari per il debug di file specifici di CLR, ad esempio mscordbi. dll e mscordacwks.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="b2ee7-119">Gli handle del modulo devono rimanere validi fino a una chiamata per il [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) metodo indica che essi possono essere liberate, a questo punto è responsabilità del chiamante liberare l'handle.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>  
  
 <span data-ttu-id="b2ee7-120">Il debugger può usare qualsiasi strumento disponibile per individuare oppure ottenere il modulo di debug.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-120">The debugger may use any available means to locate or procure the debugging module.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b2ee7-121">Questa funzionalità consente al chiamante di API fornire i moduli che contengono codice eseguibile e potenzialmente dannoso.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="b2ee7-122">Come precauzione di sicurezza, il chiamante non deve utilizzare `ProvideLibrary` per distribuire qualsiasi codice che non è disposto da eseguire se stesso.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>  
>   
>  <span data-ttu-id="b2ee7-123">Se viene rilevato un problema serio di protezione in una libreria già rilasciata, ad esempio mscordbi. dll o mscordacwks, lo shim può essere corretto in modo che riconosca le versioni dei file non valide.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="b2ee7-124">Lo shim può quindi inviare le richieste per le versioni con patch dei file e rifiutare le versioni non sicure, se vengono forniti in risposta a tutte le richieste.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="b2ee7-125">Ciò può verificarsi solo se l'utente è applicata una patch a una nuova versione dello shim.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="b2ee7-126">Le versioni patch rimane vulnerabile.</span><span class="sxs-lookup"><span data-stu-id="b2ee7-126">Unpatched versions will remain vulnerable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2ee7-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b2ee7-127">Requirements</span></span>  
 <span data-ttu-id="b2ee7-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2ee7-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2ee7-129">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2ee7-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2ee7-130">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2ee7-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2ee7-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2ee7-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ee7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2ee7-132">See also</span></span>

- [<span data-ttu-id="b2ee7-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b2ee7-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b2ee7-134">Debug</span><span class="sxs-lookup"><span data-stu-id="b2ee7-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
