---
title: Metodo ICorDebugMetaDataLocator::GetMetaData
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator.GetMetaData
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator::GetMetaData
helpviewer_keywords:
- ICorDebugMetaDataLocator::GetMetaData method [.NET Framework debugging]
- GetMetaData method, ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: f9b0ff22-54db-45eb-9cc3-508000a3141d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c787a93ac98a086dfb6218d1b4891de87e0e107d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486992"
---
# <a name="icordebugmetadatalocatorgetmetadata-method"></a><span data-ttu-id="215bd-102">Metodo ICorDebugMetaDataLocator::GetMetaData</span><span class="sxs-lookup"><span data-stu-id="215bd-102">ICorDebugMetaDataLocator::GetMetaData Method</span></span>
<span data-ttu-id="215bd-103">Chiede al debugger di restituire il percorso completo di un modulo i cui metadati sono necessari per completare un'operazione richiesta dal debugger.</span><span class="sxs-lookup"><span data-stu-id="215bd-103">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="215bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="215bd-104">Syntax</span></span>  
  
```  
HRESULT GetMetaData(  
      [in] LPCWSTR wszImagePath,  
      [in] DWORD   dwImageTimeStamp,  
      [in] DWORD   dwImageSize,  
      [in] ULONG32 cchPathBuffer,  
      [out] ULONG32 * pcchPathBuffer,  
      [out, size_is(cchPathBuffer), length_is(*pcchPathBuffer)]  
               WCHAR wszPathBuffer[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="215bd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="215bd-105">Parameters</span></span>  
 `wszImagePath`  
 <span data-ttu-id="215bd-106">[in] Stringa con terminazione null che rappresenta il percorso completo del file.</span><span class="sxs-lookup"><span data-stu-id="215bd-106">[in] A null-terminated string that represents the full path to the file.</span></span> <span data-ttu-id="215bd-107">Se il percorso completo non è disponibile, il nome e l'estensione del file (*nomefile*. *estensione*).</span><span class="sxs-lookup"><span data-stu-id="215bd-107">If the full path is not available, the name and extension of the file (*filename*.*extension*).</span></span>  
  
 `dwImageTimeStamp`  
 <span data-ttu-id="215bd-108">[in] Timestamp dalle intestazioni del file PE dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="215bd-108">[in] The time stamp from the image's PE file headers.</span></span> <span data-ttu-id="215bd-109">Questo parametro può essere potenzialmente usato per un server di simboli ([SymSrv](/windows/desktop/debug/using-symsrv)) ricerca.</span><span class="sxs-lookup"><span data-stu-id="215bd-109">This parameter can potentially be used for a symbol server ([SymSrv](/windows/desktop/debug/using-symsrv)) lookup.</span></span>  
  
 `dwImageSize`  
 <span data-ttu-id="215bd-110">[in] Dimensioni dell'immagine dalle intestazioni del file PE.</span><span class="sxs-lookup"><span data-stu-id="215bd-110">[in] The image size from PE file headers.</span></span> <span data-ttu-id="215bd-111">Questo parametro può essere potenzialmente usato per una ricerca in SymSrv.</span><span class="sxs-lookup"><span data-stu-id="215bd-111">This parameter can potentially be used for a SymSrv lookup.</span></span>  
  
 `cchPathBuffer`  
 <span data-ttu-id="215bd-112">[in] Numero di caratteri in `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="215bd-112">[in] The character count in `wszPathBuffer`.</span></span>  
  
 `pcchPathBuffer`  
 <span data-ttu-id="215bd-113">[out] Numero di `WCHAR` scritto in `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="215bd-113">[out] The count of `WCHAR`s written to `wszPathBuffer`.</span></span>  
  
 <span data-ttu-id="215bd-114">Se il metodo restituisce E_NOT_SUFFICIENT_BUFFER, contiene il numero di `WCHAR` necessario per archiviare il percorso.</span><span class="sxs-lookup"><span data-stu-id="215bd-114">If the method returns E_NOT_SUFFICIENT_BUFFER, contains the count of `WCHAR`s needed to store the path.</span></span>  
  
 `wszPathBuffer`  
 <span data-ttu-id="215bd-115">[out] Puntatore a un buffer in cui il debugger copierà il percorso completo del file che contiene i metadati richiesti.</span><span class="sxs-lookup"><span data-stu-id="215bd-115">[out] Pointer to a buffer into which the debugger will copy the full path of the file that contains the requested metadata.</span></span>  
  
 <span data-ttu-id="215bd-116">Il `ofReadOnly` flag dal [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione viene utilizzata per richiedere l'accesso di sola lettura ai metadati in questo file.</span><span class="sxs-lookup"><span data-stu-id="215bd-116">The `ofReadOnly` flag from the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration is used to request read-only access to the metadata in this file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="215bd-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="215bd-117">Return Value</span></span>  
 <span data-ttu-id="215bd-118">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="215bd-118">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span> <span data-ttu-id="215bd-119">Tutti gli altri HRESULT di errore indicano che il file non è recuperabile.</span><span class="sxs-lookup"><span data-stu-id="215bd-119">All other failure HRESULTs indicate that the file is not retrievable.</span></span>  
  
|<span data-ttu-id="215bd-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="215bd-120">HRESULT</span></span>|<span data-ttu-id="215bd-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="215bd-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="215bd-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="215bd-122">S_OK</span></span>|<span data-ttu-id="215bd-123">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="215bd-123">The method completed successfully.</span></span> <span data-ttu-id="215bd-124">`wszPathBuffer` contiene il percorso completo del file ed è con terminazione null.</span><span class="sxs-lookup"><span data-stu-id="215bd-124">`wszPathBuffer` contains the full path to the file and is null-terminated.</span></span>|  
|<span data-ttu-id="215bd-125">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="215bd-125">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="215bd-126">Le dimensioni correnti di `wszPathBuffer` non sono sufficienti a contenere il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="215bd-126">The current size of `wszPathBuffer` is not sufficient to hold the full path.</span></span> <span data-ttu-id="215bd-127">In questo caso, `pcchPathBuffer` contiene il numero necessario di `WCHAR`s, incluso il carattere di terminazione null e `GetMetaData` viene chiamato una seconda volta con le dimensioni del buffer richiesto.</span><span class="sxs-lookup"><span data-stu-id="215bd-127">In this case, `pcchPathBuffer` contains the needed count of `WCHAR`s, including the terminating null character, and `GetMetaData` is called a second time with the requested buffer size.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="215bd-128">Note</span><span class="sxs-lookup"><span data-stu-id="215bd-128">Remarks</span></span>  
 <span data-ttu-id="215bd-129">Se `wszImagePath` contiene un percorso completo di un modulo da un dump, specifica il percorso dal computer in cui è stato recuperato il dump.</span><span class="sxs-lookup"><span data-stu-id="215bd-129">If `wszImagePath` contains a full path for a module from a dump, it specifies the path from the computer where the dump was collected.</span></span> <span data-ttu-id="215bd-130">Il file può non esistere in questa posizione oppure un file errato con lo stesso nome può essere archiviato nel percorso.</span><span class="sxs-lookup"><span data-stu-id="215bd-130">The file may not exist at this location, or an incorrect file with the same name may be stored on the path.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="215bd-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="215bd-131">Requirements</span></span>  
 <span data-ttu-id="215bd-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="215bd-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="215bd-133">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="215bd-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="215bd-134">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="215bd-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="215bd-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="215bd-135">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="215bd-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="215bd-136">See also</span></span>
- [<span data-ttu-id="215bd-137">Interfaccia ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="215bd-137">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="215bd-138">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="215bd-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="215bd-139">Debug</span><span class="sxs-lookup"><span data-stu-id="215bd-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
