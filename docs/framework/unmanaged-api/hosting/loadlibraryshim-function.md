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
ms.openlocfilehash: 11bb220068e978dc130701e3b28ab3f421be7337
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937658"
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="a8be3-102">Funzione LoadLibraryShim</span><span class="sxs-lookup"><span data-stu-id="a8be3-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="a8be3-103">Carica una versione specificata di una DLL inclusa nel pacchetto ridistribuibile .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8be3-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="a8be3-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a8be3-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="a8be3-105">Usare invece il metodo [ICLRRuntimeInfo:: LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a8be3-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8be3-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8be3-106">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8be3-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="a8be3-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="a8be3-108">in Stringa con terminazione zero che rappresenta il nome della DLL da caricare dalla libreria .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8be3-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="a8be3-109">in Stringa con terminazione zero che rappresenta la versione della DLL da caricare.</span><span class="sxs-lookup"><span data-stu-id="a8be3-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="a8be3-110">Se `szVersion` è null, la versione selezionata per il caricamento è la versione più recente della DLL specificata inferiore alla versione 4.</span><span class="sxs-lookup"><span data-stu-id="a8be3-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="a8be3-111">Ovvero tutte le versioni uguale o superiore alla versione 4 vengono ignorate se `szVersion` è null e se non è installata alcuna versione precedente alla versione 4, il caricamento della DLL non riesce.</span><span class="sxs-lookup"><span data-stu-id="a8be3-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="a8be3-112">In questo modo si garantisce che l'installazione di .NET Framework 4 non influisca sulle applicazioni o sui componenti preesistenti.</span><span class="sxs-lookup"><span data-stu-id="a8be3-112">This is to ensure that installation of the .NET Framework 4 does not affect pre-existing applications or components.</span></span> <span data-ttu-id="a8be3-113">Vedere la voce relativa [a SxS e migrazione avvio rapido](https://devblogs.microsoft.com/dotnet/in-proc-sxs-and-migration-quick-start/) nel Blog del team CLR.</span><span class="sxs-lookup"><span data-stu-id="a8be3-113">See the entry [In-Proc SxS and Migration Quick Start](https://devblogs.microsoft.com/dotnet/in-proc-sxs-and-migration-quick-start/) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="a8be3-114">Riservato per usi futuri.</span><span class="sxs-lookup"><span data-stu-id="a8be3-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="a8be3-115">out Puntatore all'handle del modulo.</span><span class="sxs-lookup"><span data-stu-id="a8be3-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8be3-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a8be3-116">Return Value</span></span>  
 <span data-ttu-id="a8be3-117">Questo metodo restituisce i codici di errore standard Component Object Model (COM), come definito in WinError. h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="a8be3-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="a8be3-118">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="a8be3-118">Return code</span></span>|<span data-ttu-id="a8be3-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8be3-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a8be3-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="a8be3-120">S_OK</span></span>|<span data-ttu-id="a8be3-121">Il metodo è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a8be3-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="a8be3-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="a8be3-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="a8be3-123">Il caricamento di `szDllName` richiede il caricamento del Common Language Runtime (CLR) e non è possibile caricare la versione necessaria di CLR.</span><span class="sxs-lookup"><span data-stu-id="a8be3-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8be3-124">Note</span><span class="sxs-lookup"><span data-stu-id="a8be3-124">Remarks</span></span>  
 <span data-ttu-id="a8be3-125">Questa funzione viene utilizzata per caricare le DLL incluse nel pacchetto ridistribuibile .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8be3-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="a8be3-126">Non carica le DLL generate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a8be3-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8be3-127">A partire dalla versione .NET Framework 2,0, il caricamento di Fusion. dll causa il caricamento di CLR.</span><span class="sxs-lookup"><span data-stu-id="a8be3-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="a8be3-128">Ciò è dovuto al fatto che le funzioni in Fusion. dll sono ora wrapper le cui implementazioni vengono fornite dal runtime.</span><span class="sxs-lookup"><span data-stu-id="a8be3-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8be3-129">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a8be3-129">Requirements</span></span>  
 <span data-ttu-id="a8be3-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8be3-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8be3-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a8be3-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a8be3-132">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8be3-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8be3-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8be3-133">See also</span></span>

- [<span data-ttu-id="a8be3-134">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="a8be3-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
