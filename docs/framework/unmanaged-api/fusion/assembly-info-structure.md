---
title: Struttura ASSEMBLY_INFO
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLY_INFO
api_location: fusion.dll
api_type: COM
f1_keywords: ASSEMBLY_INFO
helpviewer_keywords: ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d532bbd2d338f942c09c4213620468a3361db5f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyinfo-structure"></a><span data-ttu-id="d7326-102">Struttura ASSEMBLY_INFO</span><span class="sxs-lookup"><span data-stu-id="d7326-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="d7326-103">Contiene informazioni relative a un assembly registrato nella global assembly cache.</span><span class="sxs-lookup"><span data-stu-id="d7326-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7326-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7326-104">Syntax</span></span>  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="d7326-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d7326-105">Members</span></span>  
  
|<span data-ttu-id="d7326-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d7326-106">Member</span></span>|<span data-ttu-id="d7326-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d7326-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="d7326-108">Le dimensioni in byte, della struttura.</span><span class="sxs-lookup"><span data-stu-id="d7326-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="d7326-109">Questo campo è riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="d7326-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="d7326-110">Flag che indicano i dettagli di installazione sull'assembly.</span><span class="sxs-lookup"><span data-stu-id="d7326-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="d7326-111">Sono supportati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d7326-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="d7326-112">-Il valore ASSEMBLYINFO_FLAG_INSTALLED, che indica che l'assembly è installato.</span><span class="sxs-lookup"><span data-stu-id="d7326-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="d7326-113">Imposta sempre la versione corrente di .NET Framework `dwAssemblyFlags` su questo valore.</span><span class="sxs-lookup"><span data-stu-id="d7326-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="d7326-114">-Il valore ASSEMBLYINFO_FLAG_INSTALLED, che indica che l'assembly è un payload residente.</span><span class="sxs-lookup"><span data-stu-id="d7326-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="d7326-115">La versione corrente di .NET Framework non viene mai `dwAssemblyFlags` su questo valore.</span><span class="sxs-lookup"><span data-stu-id="d7326-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="d7326-116">Dimensione totale, espressa in kilobyte, dei file che contiene l'assembly.</span><span class="sxs-lookup"><span data-stu-id="d7326-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="d7326-117">Puntatore a un buffer di stringa che contiene il percorso corrente nel file manifesto.</span><span class="sxs-lookup"><span data-stu-id="d7326-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="d7326-118">Il percorso deve terminare con un carattere null.</span><span class="sxs-lookup"><span data-stu-id="d7326-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="d7326-119">Il numero di caratteri wide, incluso il terminatore null, che `pszCurrentAssemblyPathBuf` contiene.</span><span class="sxs-lookup"><span data-stu-id="d7326-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7326-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7326-120">Requirements</span></span>  
 <span data-ttu-id="d7326-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7326-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7326-122">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d7326-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d7326-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7326-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7326-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7326-124">See Also</span></span>  
 [<span data-ttu-id="d7326-125">Strutture Fusion</span><span class="sxs-lookup"><span data-stu-id="d7326-125">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="d7326-126">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="d7326-126">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
