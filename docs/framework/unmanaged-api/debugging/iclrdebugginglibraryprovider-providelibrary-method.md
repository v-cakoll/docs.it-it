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
ms.openlocfilehash: d0c283232ff8eca1af9f3ff4448fb7f4c81d554f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789039"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="c507b-102">Metodo ICLRDebuggingLibraryProvider::ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="c507b-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>

<span data-ttu-id="c507b-103">Ottiene un'interfaccia di callback del provider di librerie che consente di trovare e caricare su richiesta Common Language Runtime librerie di debug specifiche della versione di CLR.</span><span class="sxs-lookup"><span data-stu-id="c507b-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>

## <a name="syntax"></a><span data-ttu-id="c507b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c507b-104">Syntax</span></span>

```cpp
HRESULT ProvideLibrary(
     [in] const WCHAR* pwszFileName,
     [in] DWORD dwTimestamp,
     [in] DWORD dwSizeOfImage,
     [out] HMODULE* hModule);
```

## <a name="parameters"></a><span data-ttu-id="c507b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c507b-105">Parameters</span></span>

`pwszFilename` \
<span data-ttu-id="c507b-106">in Nome del modulo richiesto.</span><span class="sxs-lookup"><span data-stu-id="c507b-106">[in] The name of the module being requested.</span></span>

`dwTimestamp` \
<span data-ttu-id="c507b-107">in Indicatore di data e ora archiviato nell'intestazione del file COFF dei file PE.</span><span class="sxs-lookup"><span data-stu-id="c507b-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>

`pLibraryProvider` \
<span data-ttu-id="c507b-108">in Il campo `SizeOfImage` archiviato nell'intestazione file facoltativa COFF dei file PE.</span><span class="sxs-lookup"><span data-stu-id="c507b-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>

`hModule` \
<span data-ttu-id="c507b-109">out Handle per il modulo richiesto.</span><span class="sxs-lookup"><span data-stu-id="c507b-109">[out] The handle to the requested module.</span></span>

## <a name="return-value"></a><span data-ttu-id="c507b-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c507b-110">Return Value</span></span>

<span data-ttu-id="c507b-111">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="c507b-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>

|<span data-ttu-id="c507b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c507b-112">HRESULT</span></span>|<span data-ttu-id="c507b-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c507b-113">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="c507b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c507b-114">S_OK</span></span>|<span data-ttu-id="c507b-115">Il metodo è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c507b-115">The method completed successfully.</span></span>|

## <a name="exceptions"></a><span data-ttu-id="c507b-116">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="c507b-116">Exceptions</span></span>

## <a name="remarks"></a><span data-ttu-id="c507b-117">Note</span><span class="sxs-lookup"><span data-stu-id="c507b-117">Remarks</span></span>

<span data-ttu-id="c507b-118">`ProvideLibrary` consente al debugger di fornire i moduli necessari per il debug di file CLR specifici, ad esempio mscordbi. dll e mscordacwks. dll.</span><span class="sxs-lookup"><span data-stu-id="c507b-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="c507b-119">Gli handle del modulo devono rimanere validi fino a quando una chiamata al metodo [ICLRDebugging:: CanUnloadNow](iclrdebugging-canunloadnow-method.md) non indica che possono essere liberati, a quel punto è responsabilità del chiamante liberare gli handle.</span><span class="sxs-lookup"><span data-stu-id="c507b-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>

<span data-ttu-id="c507b-120">Il debugger può utilizzare qualsiasi mezzo disponibile per individuare o procurare il modulo di debug.</span><span class="sxs-lookup"><span data-stu-id="c507b-120">The debugger may use any available means to locate or procure the debugging module.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c507b-121">Questa funzionalità consente al chiamante dell'API di fornire moduli che contengono codice eseguibile e possibilmente dannoso.</span><span class="sxs-lookup"><span data-stu-id="c507b-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="c507b-122">Per motivi di sicurezza, il chiamante non deve usare `ProvideLibrary` per distribuire il codice che non è disposto a eseguire se stesso.</span><span class="sxs-lookup"><span data-stu-id="c507b-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>
>
> <span data-ttu-id="c507b-123">Se viene individuato un problema di sicurezza grave in una libreria già rilasciata, ad esempio mscordbi. dll o mscordacwks. dll, è possibile applicare una patch allo shim per riconoscere le versioni non valide dei file.</span><span class="sxs-lookup"><span data-stu-id="c507b-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="c507b-124">Lo shim può quindi inviare richieste per le versioni con patch dei file e rifiutare le versioni non valide se vengono fornite in risposta a una richiesta.</span><span class="sxs-lookup"><span data-stu-id="c507b-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="c507b-125">Questa situazione può verificarsi solo se l'utente ha eseguito la correzione a una nuova versione dello shim.</span><span class="sxs-lookup"><span data-stu-id="c507b-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="c507b-126">Le versioni senza patch rimarranno vulnerabili.</span><span class="sxs-lookup"><span data-stu-id="c507b-126">Unpatched versions will remain vulnerable.</span></span>

## <a name="requirements"></a><span data-ttu-id="c507b-127">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="c507b-127">Requirements</span></span>

<span data-ttu-id="c507b-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c507b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c507b-129">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c507b-129">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="c507b-130">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c507b-130">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c507b-131">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c507b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c507b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c507b-132">See also</span></span>

- [<span data-ttu-id="c507b-133">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c507b-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c507b-134">Debug</span><span class="sxs-lookup"><span data-stu-id="c507b-134">Debugging</span></span>](index.md)
