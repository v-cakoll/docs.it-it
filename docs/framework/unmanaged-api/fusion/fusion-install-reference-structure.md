---
title: Struttura FUSION_INSTALL_REFERENCE
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 611b4a543a1de7c6163ec45ff7f17d07726569ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110365"
---
# <a name="fusioninstallreference-structure"></a><span data-ttu-id="184b3-102">Struttura FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="184b3-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="184b3-103">Rappresenta un riferimento da un'applicazione a un assembly che l'applicazione è installata nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="184b3-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="184b3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="184b3-104">Syntax</span></span>  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="184b3-105">Membri</span><span class="sxs-lookup"><span data-stu-id="184b3-105">Members</span></span>  
  
|<span data-ttu-id="184b3-106">Member</span><span class="sxs-lookup"><span data-stu-id="184b3-106">Member</span></span>|<span data-ttu-id="184b3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="184b3-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="184b3-108">Le dimensioni della struttura in byte.</span><span class="sxs-lookup"><span data-stu-id="184b3-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="184b3-109">Riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="184b3-109">Reserved for future extensibility.</span></span> <span data-ttu-id="184b3-110">Questo valore deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="184b3-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="184b3-111">L'entità che aggiunge il riferimento.</span><span class="sxs-lookup"><span data-stu-id="184b3-111">The entity that adds the reference.</span></span> <span data-ttu-id="184b3-112">Questo campo può avere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="184b3-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="184b3-113">-FUSION_REFCOUNT_MSI_GUID: L'assembly viene fatto riferimento da un'applicazione che è stata installata utilizzando il programma di installazione di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="184b3-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="184b3-114">Il `szIdentifier` campo è impostato su `MSI`e il `szNonCanonicalData` campo è impostato su `Windows Installer`.</span><span class="sxs-lookup"><span data-stu-id="184b3-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="184b3-115">Questo schema viene usato per gli assembly side-by-side di Windows.</span><span class="sxs-lookup"><span data-stu-id="184b3-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="184b3-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: L'assembly viene fatto riferimento da un'applicazione che viene visualizzato nei **Aggiungi/Rimuovi programmi** interfaccia.</span><span class="sxs-lookup"><span data-stu-id="184b3-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="184b3-117">Il `szIdentifier` campo fornisce il token che registra l'applicazione con il **Aggiungi/Rimuovi programmi** interfaccia.</span><span class="sxs-lookup"><span data-stu-id="184b3-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="184b3-118">-   FUSION_REFCOUNT_FILEPATH_GUID: L'assembly viene fatto riferimento da un'applicazione che è rappresentata da un file nel file system.</span><span class="sxs-lookup"><span data-stu-id="184b3-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="184b3-119">Il `szIdentifier` campo fornisce il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="184b3-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="184b3-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: L'assembly viene fatto riferimento da un'applicazione che è rappresentata solo da una stringa opaca.</span><span class="sxs-lookup"><span data-stu-id="184b3-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="184b3-121">Il `szIdentifier` campo fornisce questa stringa opaca.</span><span class="sxs-lookup"><span data-stu-id="184b3-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="184b3-122">Global assembly cache non verifica l'esistenza di riferimenti opachi quando si rimuove questo valore.</span><span class="sxs-lookup"><span data-stu-id="184b3-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="184b3-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: Questo valore è riservato.</span><span class="sxs-lookup"><span data-stu-id="184b3-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="184b3-124">Una stringa univoca che identifica l'applicazione che ha installato l'assembly nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="184b3-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="184b3-125">Il valore dipende dal valore della `guidScheme` campo.</span><span class="sxs-lookup"><span data-stu-id="184b3-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="184b3-126">Stringa che viene riconosciuta solo dall'entità che aggiunge il riferimento.</span><span class="sxs-lookup"><span data-stu-id="184b3-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="184b3-127">Global assembly cache archivia la stringa, ma non lo utilizza.</span><span class="sxs-lookup"><span data-stu-id="184b3-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="184b3-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="184b3-128">Requirements</span></span>  
 <span data-ttu-id="184b3-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="184b3-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="184b3-130">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="184b3-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="184b3-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="184b3-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="184b3-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="184b3-132">See also</span></span>

- [<span data-ttu-id="184b3-133">Strutture Fusion</span><span class="sxs-lookup"><span data-stu-id="184b3-133">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [<span data-ttu-id="184b3-134">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="184b3-134">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
