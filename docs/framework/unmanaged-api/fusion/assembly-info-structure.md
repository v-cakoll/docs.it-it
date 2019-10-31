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
ms.openlocfilehash: a43d5e15c02a97ff10a6a5afd439cadebb6b33d2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109222"
---
# <a name="assembly_info-structure"></a><span data-ttu-id="5d640-102">Struttura ASSEMBLY_INFO</span><span class="sxs-lookup"><span data-stu-id="5d640-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="5d640-103">Contiene informazioni su un assembly registrato nel Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="5d640-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d640-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d640-104">Syntax</span></span>  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="5d640-105">Members</span><span class="sxs-lookup"><span data-stu-id="5d640-105">Members</span></span>  
  
|<span data-ttu-id="5d640-106">Member</span><span class="sxs-lookup"><span data-stu-id="5d640-106">Member</span></span>|<span data-ttu-id="5d640-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d640-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="5d640-108">Dimensione, in byte, della struttura.</span><span class="sxs-lookup"><span data-stu-id="5d640-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="5d640-109">Questo campo è riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="5d640-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="5d640-110">Flag che indicano i dettagli di installazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="5d640-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="5d640-111">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d640-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="5d640-112">: Valore ASSEMBLYINFO_FLAG_INSTALLED, che indica che l'assembly è installato.</span><span class="sxs-lookup"><span data-stu-id="5d640-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="5d640-113">La versione corrente del .NET Framework imposta sempre `dwAssemblyFlags` su questo valore.</span><span class="sxs-lookup"><span data-stu-id="5d640-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="5d640-114">: Valore ASSEMBLYINFO_FLAG_PAYLOADRESIDENT, che indica che l'assembly è un payload residente.</span><span class="sxs-lookup"><span data-stu-id="5d640-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="5d640-115">La versione corrente del .NET Framework non imposta mai `dwAssemblyFlags` su questo valore.</span><span class="sxs-lookup"><span data-stu-id="5d640-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="5d640-116">Dimensioni totali, in kilobyte, dei file contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="5d640-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="5d640-117">Puntatore a un buffer di stringa che include il percorso corrente del file manifesto.</span><span class="sxs-lookup"><span data-stu-id="5d640-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="5d640-118">Il percorso deve terminare con un carattere null.</span><span class="sxs-lookup"><span data-stu-id="5d640-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="5d640-119">Numero di caratteri wide, incluso il terminatore null, che `pszCurrentAssemblyPathBuf` contiene.</span><span class="sxs-lookup"><span data-stu-id="5d640-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d640-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d640-120">Requirements</span></span>  
 <span data-ttu-id="5d640-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d640-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d640-122">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5d640-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5d640-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d640-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d640-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d640-124">See also</span></span>

- [<span data-ttu-id="5d640-125">Strutture Fusion</span><span class="sxs-lookup"><span data-stu-id="5d640-125">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="5d640-126">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="5d640-126">Global Assembly Cache</span></span>](../../app-domains/gac.md)
