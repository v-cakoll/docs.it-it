---
title: Funzione LoadLibraryShim
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bad6c052ec90c8cd3e47c4ec822fc2d5ae944af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612164"
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="814e2-102">Funzione LoadLibraryShim</span><span class="sxs-lookup"><span data-stu-id="814e2-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="814e2-103">Carica una versione specifica di una DLL che è incluso nel pacchetto ridistribuibile di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="814e2-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="814e2-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="814e2-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="814e2-105">Usare la [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) metodo invece.</span><span class="sxs-lookup"><span data-stu-id="814e2-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="814e2-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="814e2-106">Syntax</span></span>  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="814e2-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="814e2-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="814e2-108">[in] Una stringa con terminazione zero che rappresenta il nome della DLL da caricare dalla libreria di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="814e2-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="814e2-109">[in] Una stringa con terminazione zero che rappresenta la versione della DLL da caricare.</span><span class="sxs-lookup"><span data-stu-id="814e2-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="814e2-110">Se `szVersion` è null, la versione selezionata per il caricamento è la versione più recente del file DLL specificata che è inferiore alla versione 4.</span><span class="sxs-lookup"><span data-stu-id="814e2-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="814e2-111">Vale a dire tutte le versioni uguale o maggiore della versione 4 vengono ignorate se `szVersion` è null, e se non è installata alcuna versione inferiore alla versione 4, la DLL non riesce a caricare.</span><span class="sxs-lookup"><span data-stu-id="814e2-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="814e2-112">Questo modo si garantisce che l'installazione del [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] non influiscono sulle applicazioni preesistenti o componenti.</span><span class="sxs-lookup"><span data-stu-id="814e2-112">This is to ensure that installation of the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] does not affect pre-existing applications or components.</span></span> <span data-ttu-id="814e2-113">Vedere l'intervento [SxS In-Process e avvio rapido di migrazione](https://go.microsoft.com/fwlink/?LinkId=200329) nel blog del team CLR.</span><span class="sxs-lookup"><span data-stu-id="814e2-113">See the entry [In-Proc SxS and Migration Quick Start](https://go.microsoft.com/fwlink/?LinkId=200329) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="814e2-114">Riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="814e2-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="814e2-115">[out] Un puntatore all'handle del modulo.</span><span class="sxs-lookup"><span data-stu-id="814e2-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="814e2-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="814e2-116">Return Value</span></span>  
 <span data-ttu-id="814e2-117">Questo metodo restituisce codici di errore standard modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="814e2-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="814e2-118">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="814e2-118">Return code</span></span>|<span data-ttu-id="814e2-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="814e2-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="814e2-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="814e2-120">S_OK</span></span>|<span data-ttu-id="814e2-121">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="814e2-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="814e2-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="814e2-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="814e2-123">Il caricamento `szDllName` richiede il caricamento non è possibile caricare common language runtime (CLR) e la versione necessaria di CLR.</span><span class="sxs-lookup"><span data-stu-id="814e2-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="814e2-124">Note</span><span class="sxs-lookup"><span data-stu-id="814e2-124">Remarks</span></span>  
 <span data-ttu-id="814e2-125">Questa funzione viene utilizzata per caricare le DLL incluse nel pacchetto ridistribuibile di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="814e2-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="814e2-126">Non è possibile caricare le DLL generati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="814e2-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="814e2-127">A partire da .NET Framework versione 2.0, il caricamento Fusion fa sì che Common Language Runtime da caricare.</span><span class="sxs-lookup"><span data-stu-id="814e2-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="814e2-128">Questo avviene perché le funzioni in Fusion. dll sono ora le cui implementazioni sono fornite dal runtime del wrapper.</span><span class="sxs-lookup"><span data-stu-id="814e2-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="814e2-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="814e2-129">Requirements</span></span>  
 <span data-ttu-id="814e2-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="814e2-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="814e2-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="814e2-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="814e2-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="814e2-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="814e2-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="814e2-133">See also</span></span>
- [<span data-ttu-id="814e2-134">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="814e2-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
