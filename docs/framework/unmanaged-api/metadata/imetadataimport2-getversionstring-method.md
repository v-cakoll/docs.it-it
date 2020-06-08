---
title: Metodo IMetaDataImport2::GetVersionString
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
ms.openlocfilehash: 84cf5ac9eab5749d3bdc63670fe5c31bfb62abcd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490407"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="24c76-102">Metodo IMetaDataImport2::GetVersionString</span><span class="sxs-lookup"><span data-stu-id="24c76-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="24c76-103">Ottiene il numero di versione del runtime utilizzato per compilare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="24c76-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24c76-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24c76-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24c76-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="24c76-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="24c76-106">out Una matrice in cui archiviare la stringa che specifica la versione.</span><span class="sxs-lookup"><span data-stu-id="24c76-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="24c76-107">in Dimensione, in caratteri wide, della `pwzBuf` matrice.</span><span class="sxs-lookup"><span data-stu-id="24c76-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="24c76-108">out Il numero di caratteri wide, incluso un carattere di terminazione null, restituito nella `pwzBuf` matrice.</span><span class="sxs-lookup"><span data-stu-id="24c76-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24c76-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="24c76-109">Remarks</span></span>  
 <span data-ttu-id="24c76-110">Il `GetVersionString` metodo ottiene la versione predefinita dell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="24c76-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="24c76-111">Se l'ambito non è mai stato salvato, non sarà presente una versione predefinita e verrà restituita una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="24c76-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24c76-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="24c76-112">Requirements</span></span>  
 <span data-ttu-id="24c76-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24c76-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24c76-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="24c76-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24c76-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="24c76-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="24c76-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24c76-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c76-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24c76-117">See also</span></span>

- [<span data-ttu-id="24c76-118">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="24c76-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="24c76-119">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="24c76-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
