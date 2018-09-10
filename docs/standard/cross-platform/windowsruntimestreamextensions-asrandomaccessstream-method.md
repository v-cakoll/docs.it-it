---
title: Metodo WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
api_name:
- System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location:
- System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8935a8c282bbe812ad76ac6d4228c38ab12626a4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44059651"
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a><span data-ttu-id="2c9cf-102">Metodo WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)</span><span class="sxs-lookup"><span data-stu-id="2c9cf-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Method</span></span>

<span data-ttu-id="2c9cf-103">[Supportato in .NET Framework 4.5.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="2c9cf-103">[Supported in the .NET Framework 4.5.1 and later versions]</span></span>

<span data-ttu-id="2c9cf-104">Converte il flusso specificato in un flusso di accesso casuale.</span><span class="sxs-lookup"><span data-stu-id="2c9cf-104">Converts the specified stream to a random access stream.</span></span>

<span data-ttu-id="2c9cf-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType> 
 **Assembly:** System.Runtime.WindowsRuntime (in windowsruntime)</span><span class="sxs-lookup"><span data-stu-id="2c9cf-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType>
**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span></span>

## <a name="syntax"></a><span data-ttu-id="2c9cf-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c9cf-106">Syntax</span></span>

```csharp
[CLSCompliantAttribute(false)]
public static IRandomAccessStream AsRandomAccessStream(Stream stream)
```

```vb
'Declaration
<ExtensionAttribute> _
<CLSCompliantAttribute(False)> _
Public Shared Function AsRandomAccessStream ( _
        stream As Stream) As IRandomAccessStream
```

## <a name="parameters"></a><span data-ttu-id="2c9cf-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="2c9cf-107">Parameters</span></span>

`stream`

<span data-ttu-id="2c9cf-108">Tipo: <xref:System.IO.Stream?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="2c9cf-108">Type: <xref:System.IO.Stream?displayProperty=nameWithType></span></span>  
<span data-ttu-id="2c9cf-109">Flusso da convertire.</span><span class="sxs-lookup"><span data-stu-id="2c9cf-109">The stream to convert.</span></span>

## <a name="return-value"></a><span data-ttu-id="2c9cf-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2c9cf-110">Return Value</span></span>

<span data-ttu-id="2c9cf-111">Tipo: <xref:Windows.Storage.Streams.RandomAccessStream></span><span class="sxs-lookup"><span data-stu-id="2c9cf-111">Type: <xref:Windows.Storage.Streams.RandomAccessStream></span></span>  
<span data-ttu-id="2c9cf-112">Oggetto [!INCLUDE[wrt](../../../includes/wrt-md.md)] flusso ad accesso casuale, che rappresenta il flusso convertito.</span><span class="sxs-lookup"><span data-stu-id="2c9cf-112">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] random access stream, which represents the converted stream.</span></span>

## <a name="exceptions"></a><span data-ttu-id="2c9cf-113">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="2c9cf-113">Exceptions</span></span>

|<span data-ttu-id="2c9cf-114">Eccezione</span><span class="sxs-lookup"><span data-stu-id="2c9cf-114">Exception</span></span>|<span data-ttu-id="2c9cf-115">Condizione</span><span class="sxs-lookup"><span data-stu-id="2c9cf-115">Condition</span></span>|
|---------------|---------------|
|<xref:System.NotSupportedException>|<span data-ttu-id="2c9cf-116">Il flusso da convertire non supporta la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2c9cf-116">The stream to convert does not support seeking.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2c9cf-117">Note</span><span class="sxs-lookup"><span data-stu-id="2c9cf-117">Remarks</span></span>

<span data-ttu-id="2c9cf-118">Questo metodo di estensione è disponibile solo quando si sviluppano applicazioni Windows Store.</span><span class="sxs-lookup"><span data-stu-id="2c9cf-118">This extension method is available only when you develop Windows Store apps.</span></span> <span data-ttu-id="2c9cf-119">Questo metodo fornisce un modo conveniente per lavorare con i flussi nelle applicazioni Windows Store.</span><span class="sxs-lookup"><span data-stu-id="2c9cf-119">This method provides a convenient way of working with streams in Windows Store apps.</span></span> <span data-ttu-id="2c9cf-120">Il flusso .NET Framework da convertire deve supportare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2c9cf-120">The .NET Framework stream you want to convert must support seeking.</span></span> <span data-ttu-id="2c9cf-121">Per altre informazioni, vedere il metodo <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2c9cf-121">For more information, see the <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c9cf-122">Questa API è supportata in .NET Framework 4.5.1 e nelle versioni successive, ma non nella versione 4.5.</span><span class="sxs-lookup"><span data-stu-id="2c9cf-122">This API is supported in the .NET Framework 4.5.1 and later versions, but not in version 4.5.</span></span>

## <a name="version-information"></a><span data-ttu-id="2c9cf-123">Informazioni sulla versione</span><span class="sxs-lookup"><span data-stu-id="2c9cf-123">Version Information</span></span>

<span data-ttu-id="2c9cf-124">**.NET per App di Windows Store**</span><span class="sxs-lookup"><span data-stu-id="2c9cf-124">**.NET for Windows Store apps**</span></span>

<span data-ttu-id="2c9cf-125">Supportato in: Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="2c9cf-125">Supported in: Windows 8.1</span></span>

## <a name="see-also"></a><span data-ttu-id="2c9cf-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c9cf-126">See also</span></span>

<span data-ttu-id="2c9cf-127">-[Windowsruntimestreamextensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions(v=vs.110).aspx)
-[procedura: eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime](../io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)</span><span class="sxs-lookup"><span data-stu-id="2c9cf-127">-[System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions(v=vs.110).aspx)
-[How to: Convert Between .NET Framework Streams and Windows Runtime Streams](../io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)</span></span>
