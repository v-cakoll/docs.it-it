---
title: Metodo ICLRDomainManager::SetAppDomainManagerType
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
ms.openlocfilehash: 89b3f9f248a445cc0568236d6a1df14269de4187
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615696"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="848e7-102">Metodo ICLRDomainManager::SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="848e7-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="848e7-103">Specifica il tipo, derivato dalla <xref:System.AppDomainManager?displayProperty=nameWithType> classe, del gestore del dominio dell'applicazione che verrà usato per inizializzare il dominio applicazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="848e7-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="848e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="848e7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="848e7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="848e7-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="848e7-106">in Nome visualizzato dell'assembly che contiene il tipo di gestore di dominio dell'applicazione. ad esempio: "AdMgrExample, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf150f00b3".</span><span class="sxs-lookup"><span data-stu-id="848e7-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="848e7-107">in Nome del tipo del gestore di dominio dell'applicazione, incluso lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="848e7-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="848e7-108">in Combinazione di valori di enumerazione [EInitializeNewDomainFlags](einitializenewdomainflags-enumeration.md) che forniscono informazioni sul gestore del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="848e7-108">[in] A combination of [EInitializeNewDomainFlags](einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="848e7-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="848e7-109">Return Value</span></span>  
 <span data-ttu-id="848e7-110">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="848e7-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="848e7-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="848e7-111">HRESULT</span></span>|<span data-ttu-id="848e7-112">Description</span><span class="sxs-lookup"><span data-stu-id="848e7-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="848e7-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="848e7-113">S_OK</span></span>|<span data-ttu-id="848e7-114">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="848e7-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="848e7-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="848e7-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="848e7-116">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="848e7-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="848e7-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="848e7-117">Remarks</span></span>  
 <span data-ttu-id="848e7-118">Attualmente, l'unico valore definito per `dwInitializeDomainFlags` è `eInitializeNewDomainFlags_NoSecurityChanges` , che indica al Common Language Runtime (CLR) che il gestore del dominio dell'applicazione non modificherà le impostazioni di sicurezza durante l'esecuzione del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="848e7-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="848e7-119">Questo consente a CLR di ottimizzare il caricamento di assembly con l'attributo condizionale <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA).</span><span class="sxs-lookup"><span data-stu-id="848e7-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="848e7-120">Questo può comportare un miglioramento significativo del tempo di avvio se la chiusura transitiva di questo set di assembly è grande.</span><span class="sxs-lookup"><span data-stu-id="848e7-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="848e7-121">Se l'host specifica `eInitializeNewDomainFlags_NoSecurityChanges` per il gestore di dominio dell'applicazione, <xref:System.InvalidOperationException> viene generata un'eccezione se viene effettuato un tentativo di modificare la sicurezza del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="848e7-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="848e7-122">La chiamata al metodo [ICLRControl:: SetAppDomainManagerType](iclrcontrol-setappdomainmanagertype-method.md)equivale alla chiamata `ICLRDomainManager::SetAppDomainManagerType` con `eInitializeNewDomainFlags_None` .</span><span class="sxs-lookup"><span data-stu-id="848e7-122">Calling the [ICLRControl::SetAppDomainManagerType](iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="848e7-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="848e7-123">Requirements</span></span>  
 <span data-ttu-id="848e7-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="848e7-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="848e7-125">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="848e7-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="848e7-126">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="848e7-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="848e7-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="848e7-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="848e7-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="848e7-128">See also</span></span>

- [<span data-ttu-id="848e7-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="848e7-129">Hosting</span></span>](index.md)
- [<span data-ttu-id="848e7-130">Interfaccia ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="848e7-130">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)
- [<span data-ttu-id="848e7-131">Enumerazione EInitializeNewDomainFlags</span><span class="sxs-lookup"><span data-stu-id="848e7-131">EInitializeNewDomainFlags Enumeration</span></span>](einitializenewdomainflags-enumeration.md)
