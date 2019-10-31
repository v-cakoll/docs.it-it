---
title: Metodo IAssemblyCacheItem::CreateStream
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
ms.openlocfilehash: 0660621f465f2ba3610e06bd1df38baa1bc5c907
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134481"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="44ac7-102">Metodo IAssemblyCacheItem::CreateStream</span><span class="sxs-lookup"><span data-stu-id="44ac7-102">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="44ac7-103">Crea un flusso con il nome e il formato specificati.</span><span class="sxs-lookup"><span data-stu-id="44ac7-103">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="44ac7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44ac7-104">Syntax</span></span>

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a><span data-ttu-id="44ac7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="44ac7-105">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="44ac7-106">in Flag definiti in Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="44ac7-106">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="44ac7-107">in Nome del flusso da creare.</span><span class="sxs-lookup"><span data-stu-id="44ac7-107">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="44ac7-108">in Formato del file da trasmettere.</span><span class="sxs-lookup"><span data-stu-id="44ac7-108">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="44ac7-109">in Flag specifici del formato definiti in Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="44ac7-109">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="44ac7-110">out Puntatore all'indirizzo dell'istanza di [IStream](/windows/desktop/api/objidl/nn-objidl-istream) restituita.</span><span class="sxs-lookup"><span data-stu-id="44ac7-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="44ac7-111">[in, facoltativo] Dimensione massima del flusso a cui fa riferimento `ppIStream`.</span><span class="sxs-lookup"><span data-stu-id="44ac7-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="44ac7-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="44ac7-112">Requirements</span></span>

<span data-ttu-id="44ac7-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44ac7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="44ac7-114">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="44ac7-114">**Header:** Fusion.h</span></span>

<span data-ttu-id="44ac7-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44ac7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="44ac7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44ac7-116">See also</span></span>

- [<span data-ttu-id="44ac7-117">Interfaccia IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="44ac7-117">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
