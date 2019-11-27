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
ms.openlocfilehash: 4fd31e6b752e13a5c43198760e9a4d62a8f77d10
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448569"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="8ba02-102">Enumerazione CorSymSearchPolicyAttributes</span><span class="sxs-lookup"><span data-stu-id="8ba02-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="8ba02-103">Specifica i criteri da utilizzare durante la ricerca di un lettore di simboli.</span><span class="sxs-lookup"><span data-stu-id="8ba02-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="8ba02-104">Queste costanti vengono usate dai metodi [ISymUnmanagedBinder2:: GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) e [ISymUnmanagedBinder3:: GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8ba02-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8ba02-105">L'apertura di un file di database di programma (PDB) da un'origine non attendibile costituisce un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8ba02-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba02-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ba02-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,       
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //      
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="8ba02-107">Membri</span><span class="sxs-lookup"><span data-stu-id="8ba02-107">Members</span></span>  
  
|<span data-ttu-id="8ba02-108">Membro</span><span class="sxs-lookup"><span data-stu-id="8ba02-108">Member</span></span>|<span data-ttu-id="8ba02-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ba02-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="8ba02-110">Esegue una query nel registro di sistema per individuare i percorsi dei simboli.</span><span class="sxs-lookup"><span data-stu-id="8ba02-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="8ba02-111">Accede a un server di simboli.</span><span class="sxs-lookup"><span data-stu-id="8ba02-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="8ba02-112">Cerca nel percorso specificato nella directory di debug.</span><span class="sxs-lookup"><span data-stu-id="8ba02-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="8ba02-113">Cerca il PDB nel punto in cui si trova il file exe.</span><span class="sxs-lookup"><span data-stu-id="8ba02-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ba02-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ba02-114">Requirements</span></span>  
 <span data-ttu-id="8ba02-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8ba02-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ba02-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ba02-116">See also</span></span>

- [<span data-ttu-id="8ba02-117">Enumerazioni dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="8ba02-117">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
