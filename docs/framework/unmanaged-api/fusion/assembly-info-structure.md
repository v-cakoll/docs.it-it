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
ms.openlocfilehash: 219a92c0a105cc43e0c2af7d93868cac12f2e4e4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778527"
---
# <a name="assemblyinfo-structure"></a><span data-ttu-id="a6dc0-102">Struttura ASSEMBLY_INFO</span><span class="sxs-lookup"><span data-stu-id="a6dc0-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="a6dc0-103">Contiene informazioni relative a un assembly registrato nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="a6dc0-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6dc0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6dc0-104">Syntax</span></span>  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="a6dc0-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a6dc0-105">Members</span></span>  
  
|<span data-ttu-id="a6dc0-106">Member</span><span class="sxs-lookup"><span data-stu-id="a6dc0-106">Member</span></span>|<span data-ttu-id="a6dc0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6dc0-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="a6dc0-108">Le dimensioni, in byte, della struttura.</span><span class="sxs-lookup"><span data-stu-id="a6dc0-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="a6dc0-109">Questo campo è riservato per un'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="a6dc0-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="a6dc0-110">Flag che indicano i dettagli di installazione sull'assembly.</span><span class="sxs-lookup"><span data-stu-id="a6dc0-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="a6dc0-111">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6dc0-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="a6dc0-112">-Il valore ASSEMBLYINFO_FLAG_INSTALLED, che indica che l'assembly è installato.</span><span class="sxs-lookup"><span data-stu-id="a6dc0-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="a6dc0-113">Imposta sempre la versione corrente di .NET Framework `dwAssemblyFlags` a questo valore.</span><span class="sxs-lookup"><span data-stu-id="a6dc0-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="a6dc0-114">-Il valore ASSEMBLYINFO_FLAG_INSTALLED, che indica che l'assembly è un payload residente.</span><span class="sxs-lookup"><span data-stu-id="a6dc0-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="a6dc0-115">La versione corrente di .NET Framework non viene mai `dwAssemblyFlags` a questo valore.</span><span class="sxs-lookup"><span data-stu-id="a6dc0-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="a6dc0-116">Dimensione totale, espressa in kilobyte, dei file che contiene l'assembly.</span><span class="sxs-lookup"><span data-stu-id="a6dc0-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="a6dc0-117">Puntatore a un buffer di stringa che contiene il percorso corrente per il file manifesto.</span><span class="sxs-lookup"><span data-stu-id="a6dc0-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="a6dc0-118">Il percorso deve terminare con un carattere null.</span><span class="sxs-lookup"><span data-stu-id="a6dc0-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="a6dc0-119">Il numero di caratteri "wide", incluso il carattere di terminazione null, che `pszCurrentAssemblyPathBuf` contiene.</span><span class="sxs-lookup"><span data-stu-id="a6dc0-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6dc0-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6dc0-120">Requirements</span></span>  
 <span data-ttu-id="a6dc0-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6dc0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6dc0-122">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a6dc0-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a6dc0-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6dc0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6dc0-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6dc0-124">See also</span></span>

- [<span data-ttu-id="a6dc0-125">Strutture Fusion</span><span class="sxs-lookup"><span data-stu-id="a6dc0-125">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [<span data-ttu-id="a6dc0-126">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a6dc0-126">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
