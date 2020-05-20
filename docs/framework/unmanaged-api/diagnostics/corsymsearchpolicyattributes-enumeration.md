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
ms.openlocfilehash: 0cd451854d4dbb3b243339efdc33d7dcd7860eb7
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420604"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="29c2e-102">Enumerazione CorSymSearchPolicyAttributes</span><span class="sxs-lookup"><span data-stu-id="29c2e-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="29c2e-103">Specifica i criteri da utilizzare durante la ricerca di un lettore di simboli.</span><span class="sxs-lookup"><span data-stu-id="29c2e-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="29c2e-104">Queste costanti vengono usate dai metodi [ISymUnmanagedBinder2:: GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) e [ISymUnmanagedBinder3:: GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="29c2e-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="29c2e-105">L'apertura di un file di database di programma (PDB) da un'origine non attendibile costituisce un rischio per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="29c2e-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29c2e-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29c2e-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="29c2e-107">Membri</span><span class="sxs-lookup"><span data-stu-id="29c2e-107">Members</span></span>  
  
|<span data-ttu-id="29c2e-108">Membro</span><span class="sxs-lookup"><span data-stu-id="29c2e-108">Member</span></span>|<span data-ttu-id="29c2e-109">Description</span><span class="sxs-lookup"><span data-stu-id="29c2e-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="29c2e-110">Esegue una query nel registro di sistema per individuare i percorsi dei simboli.</span><span class="sxs-lookup"><span data-stu-id="29c2e-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="29c2e-111">Accede a un server di simboli.</span><span class="sxs-lookup"><span data-stu-id="29c2e-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="29c2e-112">Cerca nel percorso specificato nella directory di debug.</span><span class="sxs-lookup"><span data-stu-id="29c2e-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="29c2e-113">Cerca il PDB nel punto in cui si trova il file exe.</span><span class="sxs-lookup"><span data-stu-id="29c2e-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29c2e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="29c2e-114">Requirements</span></span>  
 <span data-ttu-id="29c2e-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="29c2e-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c2e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29c2e-116">See also</span></span>

- [<span data-ttu-id="29c2e-117">Enumerazioni dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="29c2e-117">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
