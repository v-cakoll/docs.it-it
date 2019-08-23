---
title: Enumerazione CorSymSearchPolicyAttributes
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7188c516d3d0a5192251697ec743e9d41f8d9072
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913734"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="1e822-102">Enumerazione CorSymSearchPolicyAttributes</span><span class="sxs-lookup"><span data-stu-id="1e822-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="1e822-103">Specifica i criteri da utilizzare durante la ricerca di un lettore di simboli.</span><span class="sxs-lookup"><span data-stu-id="1e822-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="1e822-104">Queste costanti vengono usate dai metodi [ISymUnmanagedBinder2:: GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) e [ISymUnmanagedBinder3:: GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1e822-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1e822-105">L'apertura di un file di database di programma (PDB) da un'origine non attendibile costituisce un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1e822-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e822-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e822-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="1e822-107">Members</span><span class="sxs-lookup"><span data-stu-id="1e822-107">Members</span></span>  
  
|<span data-ttu-id="1e822-108">Member</span><span class="sxs-lookup"><span data-stu-id="1e822-108">Member</span></span>|<span data-ttu-id="1e822-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e822-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="1e822-110">Esegue una query nel registro di sistema per individuare i percorsi dei simboli.</span><span class="sxs-lookup"><span data-stu-id="1e822-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="1e822-111">Accede a un server di simboli.</span><span class="sxs-lookup"><span data-stu-id="1e822-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="1e822-112">Cerca nel percorso specificato nella directory di debug.</span><span class="sxs-lookup"><span data-stu-id="1e822-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="1e822-113">Cerca il PDB nel punto in cui si trova il file exe.</span><span class="sxs-lookup"><span data-stu-id="1e822-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e822-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e822-114">Requirements</span></span>  
 <span data-ttu-id="1e822-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1e822-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e822-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e822-116">See also</span></span>

- [<span data-ttu-id="1e822-117">Enumerazioni dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="1e822-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
