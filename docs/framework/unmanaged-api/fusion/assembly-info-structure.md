---
title: Struttura ASSEMBLY_INFO
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 390ab4881396bbc01337d087f05b6066153bfed1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795482"
---
# <a name="assembly_info-structure"></a><span data-ttu-id="1303d-102">Struttura ASSEMBLY_INFO</span><span class="sxs-lookup"><span data-stu-id="1303d-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="1303d-103">Contiene informazioni su un assembly registrato nel Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="1303d-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1303d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1303d-104">Syntax</span></span>  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="1303d-105">Members</span><span class="sxs-lookup"><span data-stu-id="1303d-105">Members</span></span>  
  
|<span data-ttu-id="1303d-106">Member</span><span class="sxs-lookup"><span data-stu-id="1303d-106">Member</span></span>|<span data-ttu-id="1303d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1303d-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="1303d-108">Dimensione, in byte, della struttura.</span><span class="sxs-lookup"><span data-stu-id="1303d-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="1303d-109">Questo campo è riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="1303d-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="1303d-110">Flag che indicano i dettagli di installazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1303d-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="1303d-111">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="1303d-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="1303d-112">: Valore ASSEMBLYINFO_FLAG_INSTALLED, che indica che l'assembly è installato.</span><span class="sxs-lookup"><span data-stu-id="1303d-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="1303d-113">La versione corrente del .NET Framework imposta `dwAssemblyFlags` sempre su questo valore.</span><span class="sxs-lookup"><span data-stu-id="1303d-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="1303d-114">: Valore ASSEMBLYINFO_FLAG_PAYLOADRESIDENT, che indica che l'assembly è un payload residente.</span><span class="sxs-lookup"><span data-stu-id="1303d-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="1303d-115">La versione corrente del .NET Framework non imposta `dwAssemblyFlags` mai su questo valore.</span><span class="sxs-lookup"><span data-stu-id="1303d-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="1303d-116">Dimensioni totali, in kilobyte, dei file contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1303d-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="1303d-117">Puntatore a un buffer di stringa che include il percorso corrente del file manifesto.</span><span class="sxs-lookup"><span data-stu-id="1303d-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="1303d-118">Il percorso deve terminare con un carattere null.</span><span class="sxs-lookup"><span data-stu-id="1303d-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="1303d-119">Numero di caratteri wide, incluso il terminatore null, che `pszCurrentAssemblyPathBuf` contiene.</span><span class="sxs-lookup"><span data-stu-id="1303d-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1303d-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1303d-120">Requirements</span></span>  
 <span data-ttu-id="1303d-121">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1303d-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1303d-122">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="1303d-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1303d-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1303d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1303d-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1303d-124">See also</span></span>

- [<span data-ttu-id="1303d-125">Strutture Fusion</span><span class="sxs-lookup"><span data-stu-id="1303d-125">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="1303d-126">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="1303d-126">Global Assembly Cache</span></span>](../../app-domains/gac.md)
