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
ms.openlocfilehash: 3859752fd92a76f3fef1ceced0e792109b65106a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108283"
---
# <a name="fusion_install_reference-structure"></a><span data-ttu-id="816c7-102">Struttura FUSION_INSTALL_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="816c7-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="816c7-103">Rappresenta un riferimento che un'applicazione esegue a un assembly installato dall'applicazione nell'Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="816c7-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="816c7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="816c7-104">Syntax</span></span>  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="816c7-105">Members</span><span class="sxs-lookup"><span data-stu-id="816c7-105">Members</span></span>  
  
|<span data-ttu-id="816c7-106">Member</span><span class="sxs-lookup"><span data-stu-id="816c7-106">Member</span></span>|<span data-ttu-id="816c7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="816c7-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="816c7-108">Dimensioni in byte della struttura.</span><span class="sxs-lookup"><span data-stu-id="816c7-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="816c7-109">Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="816c7-109">Reserved for future extensibility.</span></span> <span data-ttu-id="816c7-110">Questo valore deve essere 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="816c7-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="816c7-111">Entità che aggiunge il riferimento.</span><span class="sxs-lookup"><span data-stu-id="816c7-111">The entity that adds the reference.</span></span> <span data-ttu-id="816c7-112">Questo campo può avere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="816c7-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="816c7-113">-FUSION_REFCOUNT_MSI_GUID: all'assembly viene fatto riferimento da un'applicazione che è stata installata usando il Microsoft Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="816c7-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="816c7-114">Il campo `szIdentifier` è impostato su `MSI`e il campo `szNonCanonicalData` è impostato su `Windows Installer`.</span><span class="sxs-lookup"><span data-stu-id="816c7-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="816c7-115">Questo schema viene utilizzato per gli assembly side-by-side di Windows.</span><span class="sxs-lookup"><span data-stu-id="816c7-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="816c7-116">-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: all'assembly viene fatto riferimento da un'applicazione visualizzata nell'interfaccia **Installazione applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="816c7-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="816c7-117">Il campo `szIdentifier` fornisce il token che registra l'applicazione con l'interfaccia di **Installazione applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="816c7-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="816c7-118">-FUSION_REFCOUNT_FILEPATH_GUID: all'assembly viene fatto riferimento da un'applicazione rappresentata da un file nel file system.</span><span class="sxs-lookup"><span data-stu-id="816c7-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="816c7-119">Il campo `szIdentifier` fornisce il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="816c7-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="816c7-120">-FUSION_REFCOUNT_OPAQUE_STRING_GUID: all'assembly viene fatto riferimento da un'applicazione rappresentata solo da una stringa opaca.</span><span class="sxs-lookup"><span data-stu-id="816c7-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="816c7-121">Il campo `szIdentifier` fornisce questa stringa opaca.</span><span class="sxs-lookup"><span data-stu-id="816c7-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="816c7-122">Il Global Assembly Cache non verifica l'esistenza di riferimenti opachi quando si rimuove questo valore.</span><span class="sxs-lookup"><span data-stu-id="816c7-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="816c7-123">-FUSION_REFCOUNT_OSINSTALL_GUID: questo valore è riservato.</span><span class="sxs-lookup"><span data-stu-id="816c7-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="816c7-124">Stringa univoca che identifica l'applicazione che ha installato l'assembly nel Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="816c7-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="816c7-125">Il valore dipende dal valore del campo `guidScheme`.</span><span class="sxs-lookup"><span data-stu-id="816c7-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="816c7-126">Stringa riconosciuta solo dall'entità che aggiunge il riferimento.</span><span class="sxs-lookup"><span data-stu-id="816c7-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="816c7-127">Il Global Assembly Cache archivia questa stringa, ma non la utilizza.</span><span class="sxs-lookup"><span data-stu-id="816c7-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="816c7-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="816c7-128">Requirements</span></span>  
 <span data-ttu-id="816c7-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="816c7-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="816c7-130">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="816c7-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="816c7-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="816c7-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="816c7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="816c7-132">See also</span></span>

- [<span data-ttu-id="816c7-133">Strutture Fusion</span><span class="sxs-lookup"><span data-stu-id="816c7-133">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="816c7-134">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="816c7-134">Global Assembly Cache</span></span>](../../app-domains/gac.md)
