---
title: Metodo MemoryStream. InternalGetOriginAndLength (System.IO)
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: d82b5080e9fbd5fc6603f1cddae996c75a06d3a3
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215471"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a><span data-ttu-id="418d5-102">MemoryStream. InternalGetOriginAndLength, metodo</span><span class="sxs-lookup"><span data-stu-id="418d5-102">MemoryStream.InternalGetOriginAndLength method</span></span>

<span data-ttu-id="418d5-103">Ottiene i valori interni dell'origine e della lunghezza del flusso di memoria.</span><span class="sxs-lookup"><span data-stu-id="418d5-103">Gets the internal values of origin and length of the memory stream.</span></span>

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a><span data-ttu-id="418d5-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="418d5-104">Parameters</span></span>

- <span data-ttu-id="418d5-105">`origin` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="418d5-105">`origin` <xref:System.Int32></span></span>\
  <span data-ttu-id="418d5-106">Quando questo metodo restituisce, l'offset della matrice di byte specificata durante la creazione di un nuovo oggetto <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="418d5-106">When this method returns, the offset of the byte array specified when creating a new <xref:System.IO.MemoryStream> object.</span></span> <span data-ttu-id="418d5-107">Contiene 0 se la matrice di byte è stata creata da <xref:System.IO.MemoryStream>.</span><span class="sxs-lookup"><span data-stu-id="418d5-107">Contains 0 if the byte array was created by <xref:System.IO.MemoryStream>.</span></span>

- <span data-ttu-id="418d5-108">`length` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="418d5-108">`length` <xref:System.Int32></span></span>\
  <span data-ttu-id="418d5-109">Quando questo metodo restituisce, il numero di byte all'interno del flusso di memoria.</span><span class="sxs-lookup"><span data-stu-id="418d5-109">When this method returns, the number of bytes within the memory stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="418d5-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="418d5-110">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="418d5-111">Il `MemoryStream.InternalGetOriginAndLength` metodo è interno e non deve essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="418d5-111">The `MemoryStream.InternalGetOriginAndLength` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="418d5-112">Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="418d5-112">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="418d5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="418d5-113">Requirements</span></span>

<span data-ttu-id="418d5-114">**Spazio dei nomi:** <xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="418d5-114">**Namespace:** <xref:System.IO></span></span>

<span data-ttu-id="418d5-115">**Assembly:** mscorlib. dll (in mscorlib. dll)</span><span class="sxs-lookup"><span data-stu-id="418d5-115">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="418d5-116">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="418d5-116">**.NET Framework versions:** Available since 2.0.</span></span>
