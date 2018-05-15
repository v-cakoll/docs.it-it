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
ms.openlocfilehash: 16f878abc11589fe62f78d941b367d82d7b49e1c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a><span data-ttu-id="ade2b-102">Metodo WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)</span><span class="sxs-lookup"><span data-stu-id="ade2b-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Method</span></span>
<span data-ttu-id="ade2b-103">[Supportato in .NET Framework 4.5.1 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="ade2b-103">[Supported in the .NET Framework 4.5.1 and later versions]</span></span>  
  
 <span data-ttu-id="ade2b-104">Converte il flusso specificato in un flusso di accesso casuale.</span><span class="sxs-lookup"><span data-stu-id="ade2b-104">Converts the specified stream to a random access stream.</span></span>  
  
 <span data-ttu-id="ade2b-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ade2b-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType></span></span>  
 <span data-ttu-id="ade2b-106">**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span><span class="sxs-lookup"><span data-stu-id="ade2b-106">**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ade2b-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ade2b-107">Syntax</span></span>  
  
```csharp  
[CLSCompliantAttribute(false)]  
public static  IRandomAccessStream AsRandomAccessStream(Stream stream)  
```  
  
```vb  
'Declaration  
<ExtensionAttribute> _  
<CLSCompliantAttribute(False)> _  
Public Shared Function AsRandomAccessStream ( _  
        stream As Stream) As IRandomAccessStream  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ade2b-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="ade2b-108">Parameters</span></span>  
 `stream`  
  
 <span data-ttu-id="ade2b-109">Tipo: <xref:System.IO.Stream?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ade2b-109">Type: <xref:System.IO.Stream?displayProperty=nameWithType></span></span>  
<span data-ttu-id="ade2b-110">Flusso da convertire.</span><span class="sxs-lookup"><span data-stu-id="ade2b-110">The stream to convert.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ade2b-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ade2b-111">Return Value</span></span>  
 <span data-ttu-id="ade2b-112">Tipo: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span><span class="sxs-lookup"><span data-stu-id="ade2b-112">Type: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span></span>  
<span data-ttu-id="ade2b-113">Oggetto [!INCLUDE[wrt](../../../includes/wrt-md.md)] flusso ad accesso casuale, che rappresenta il flusso convertito.</span><span class="sxs-lookup"><span data-stu-id="ade2b-113">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] random access stream, which represents the converted stream.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="ade2b-114">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="ade2b-114">Exceptions</span></span>  
  
|<span data-ttu-id="ade2b-115">Eccezione</span><span class="sxs-lookup"><span data-stu-id="ade2b-115">Exception</span></span>|<span data-ttu-id="ade2b-116">Condizione</span><span class="sxs-lookup"><span data-stu-id="ade2b-116">Condition</span></span>|  
|---------------|---------------|  
|<xref:System.NotSupportedException>|<span data-ttu-id="ade2b-117">Il flusso da convertire non supporta la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ade2b-117">The stream to convert does not support seeking.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ade2b-118">Note</span><span class="sxs-lookup"><span data-stu-id="ade2b-118">Remarks</span></span>  
 <span data-ttu-id="ade2b-119">Questo metodo di estensione è disponibile solo quando si sviluppano applicazioni Windows Store.</span><span class="sxs-lookup"><span data-stu-id="ade2b-119">This extension method is available only when you develop Windows Store apps.</span></span> <span data-ttu-id="ade2b-120">Questo metodo fornisce un modo conveniente per lavorare con i flussi nelle applicazioni Windows Store.</span><span class="sxs-lookup"><span data-stu-id="ade2b-120">This method provides a convenient way of working with streams in Windows Store apps.</span></span> <span data-ttu-id="ade2b-121">Il flusso .NET Framework da convertire deve supportare la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ade2b-121">The .NET Framework stream you want to convert must support seeking.</span></span> <span data-ttu-id="ade2b-122">Per altre informazioni, vedere il metodo <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ade2b-122">For more information, see the <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ade2b-123">Questa API è supportata in .NET Framework 4.5.1 e nelle versioni successive, ma non nella versione 4.5.</span><span class="sxs-lookup"><span data-stu-id="ade2b-123">This API is supported in the .NET Framework 4.5.1 and later versions, but not in version 4.5.</span></span>  
  
## <a name="version-information"></a><span data-ttu-id="ade2b-124">Informazioni sulla versione</span><span class="sxs-lookup"><span data-stu-id="ade2b-124">Version Information</span></span>  
 <span data-ttu-id="ade2b-125">**.NET per applicazioni Windows Store**</span><span class="sxs-lookup"><span data-stu-id="ade2b-125">**.NET for Windows Store apps**</span></span>  
  
 <span data-ttu-id="ade2b-126">Supportato in: Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ade2b-126">Supported in: Windows 8.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ade2b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ade2b-127">See Also</span></span>  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions`  
 [<span data-ttu-id="ade2b-128">Procedura: Eseguire la conversione tra flussi di .NET Framework e flussi di Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="ade2b-128">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
