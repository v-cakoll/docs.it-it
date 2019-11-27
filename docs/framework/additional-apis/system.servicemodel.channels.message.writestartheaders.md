---
title: Metodo Message. WriteStartHeaders (System. ServiceModel. Channels)
author: mairaw
ms.author: mairaw
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: a2c82ee4029c7af0396219f5ded8c999fd01d65b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451178"
---
# <a name="messagewritestartheaders-method"></a><span data-ttu-id="f0c9a-102">Message. WriteStartHeaders, metodo</span><span class="sxs-lookup"><span data-stu-id="f0c9a-102">Message.WriteStartHeaders Method</span></span>

<span data-ttu-id="f0c9a-103">Scrive l'intestazione iniziale in un file XML chiamando il metodo <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-103">Writes the start header into an XML file by calling the <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> method.</span></span>

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a><span data-ttu-id="f0c9a-104">Parametri</span><span class="sxs-lookup"><span data-stu-id="f0c9a-104">Parameters</span></span>

- <span data-ttu-id="f0c9a-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span><span class="sxs-lookup"><span data-stu-id="f0c9a-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span></span>\
  <span data-ttu-id="f0c9a-106">Writer utilizzato per scrivere l'intestazione iniziale in un file XML.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-106">The writer that is used to write the start header into an XML file.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0c9a-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f0c9a-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="f0c9a-108">Il `Message.WriteStartHeaders` metodo è interno e non deve essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-108">The `Message.WriteStartHeaders` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f0c9a-109">Microsoft non supporta l'utilizzo di questo metodo in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-109">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0c9a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0c9a-110">Requirements</span></span>

<span data-ttu-id="f0c9a-111">**Spazio dei nomi:** <xref:System.ServiceModel.Channels></span><span class="sxs-lookup"><span data-stu-id="f0c9a-111">**Namespace:** <xref:System.ServiceModel.Channels></span></span>

<span data-ttu-id="f0c9a-112">**Assembly:** System. ServiceModel. dll</span><span class="sxs-lookup"><span data-stu-id="f0c9a-112">**Assembly:** System.ServiceModel.dll</span></span>

<span data-ttu-id="f0c9a-113">**Versioni .NET Framework:** Disponibile a partire da 3,0.</span><span class="sxs-lookup"><span data-stu-id="f0c9a-113">**.NET Framework versions:** Available since 3.0.</span></span>
