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
ms.openlocfilehash: 4a3a4e6ccb8a43f9bde5aa7a447e28c30f8d72f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965129"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="38cc0-102">Metodo ICLRDebuggingLibraryProvider::ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="38cc0-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>
<span data-ttu-id="38cc0-103">Ottiene un'interfaccia di callback del provider di librerie che consente di trovare e caricare su richiesta Common Language Runtime librerie di debug specifiche della versione di CLR.</span><span class="sxs-lookup"><span data-stu-id="38cc0-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38cc0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38cc0-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38cc0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="38cc0-105">Parameters</span></span>  
 `pwszFilename`  
 <span data-ttu-id="38cc0-106">in Nome del modulo richiesto.</span><span class="sxs-lookup"><span data-stu-id="38cc0-106">[in] The name of the module being requested.</span></span>  
  
 `dwTimestamp`  
 <span data-ttu-id="38cc0-107">in Indicatore di data e ora archiviato nell'intestazione del file COFF dei file PE.</span><span class="sxs-lookup"><span data-stu-id="38cc0-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="38cc0-108">in `SizeOfImage` Campo archiviato nell'intestazione file facoltativa COFF dei file PE.</span><span class="sxs-lookup"><span data-stu-id="38cc0-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>  
  
 `hModule`  
 <span data-ttu-id="38cc0-109">out Handle per il modulo richiesto.</span><span class="sxs-lookup"><span data-stu-id="38cc0-109">[out] The handle to the requested module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38cc0-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="38cc0-110">Return Value</span></span>  
 <span data-ttu-id="38cc0-111">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="38cc0-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="38cc0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="38cc0-112">HRESULT</span></span>|<span data-ttu-id="38cc0-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38cc0-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="38cc0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="38cc0-114">S_OK</span></span>|<span data-ttu-id="38cc0-115">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="38cc0-115">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="38cc0-116">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="38cc0-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38cc0-117">Note</span><span class="sxs-lookup"><span data-stu-id="38cc0-117">Remarks</span></span>  
 <span data-ttu-id="38cc0-118">`ProvideLibrary`consente al debugger di fornire i moduli necessari per il debug di file CLR specifici, ad esempio mscordbi. dll e mscordacwks. dll.</span><span class="sxs-lookup"><span data-stu-id="38cc0-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="38cc0-119">Gli handle del modulo devono rimanere validi fino a quando una chiamata al metodo [ICLRDebugging:: CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) non indica che possono essere liberati, a quel punto è responsabilità del chiamante liberare gli handle.</span><span class="sxs-lookup"><span data-stu-id="38cc0-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>  
  
 <span data-ttu-id="38cc0-120">Il debugger può utilizzare qualsiasi mezzo disponibile per individuare o procurare il modulo di debug.</span><span class="sxs-lookup"><span data-stu-id="38cc0-120">The debugger may use any available means to locate or procure the debugging module.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="38cc0-121">Questa funzionalità consente al chiamante dell'API di fornire moduli che contengono codice eseguibile e possibilmente dannoso.</span><span class="sxs-lookup"><span data-stu-id="38cc0-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="38cc0-122">Per motivi di sicurezza, il chiamante non deve usare `ProvideLibrary` per distribuire il codice che non è disposto a eseguire se stesso.</span><span class="sxs-lookup"><span data-stu-id="38cc0-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>  
>   
>  <span data-ttu-id="38cc0-123">Se viene individuato un problema di sicurezza grave in una libreria già rilasciata, ad esempio mscordbi. dll o mscordacwks. dll, è possibile applicare una patch allo shim per riconoscere le versioni non valide dei file.</span><span class="sxs-lookup"><span data-stu-id="38cc0-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="38cc0-124">Lo shim può quindi inviare richieste per le versioni con patch dei file e rifiutare le versioni non valide se vengono fornite in risposta a una richiesta.</span><span class="sxs-lookup"><span data-stu-id="38cc0-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="38cc0-125">Questa situazione può verificarsi solo se l'utente ha eseguito la correzione a una nuova versione dello shim.</span><span class="sxs-lookup"><span data-stu-id="38cc0-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="38cc0-126">Le versioni senza patch rimarranno vulnerabili.</span><span class="sxs-lookup"><span data-stu-id="38cc0-126">Unpatched versions will remain vulnerable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38cc0-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38cc0-127">Requirements</span></span>  
 <span data-ttu-id="38cc0-128">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38cc0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38cc0-129">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="38cc0-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38cc0-130">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38cc0-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38cc0-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38cc0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38cc0-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38cc0-132">See also</span></span>

- [<span data-ttu-id="38cc0-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="38cc0-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="38cc0-134">Debug</span><span class="sxs-lookup"><span data-stu-id="38cc0-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
