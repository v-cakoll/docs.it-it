---
title: CoreResponseData. m_ResponseHeaders campo
description: Informazioni sul campo CoreResponseData. m_ResponseHeaders in .NET. Questo campo è un tipo WebHeaderCollection con le intestazioni associate alla risposta del server.
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 7c7b896193cb81e9fc9e3ec28110359003a36728
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989794"
---
# <a name="coreresponsedatam_responseheaders-field"></a><span data-ttu-id="ab761-104">CoreResponseData. m- \_ campo ResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="ab761-104">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="ab761-105">`CoreResponseData.m_ResponseHeaders`è un oggetto <xref:System.Net.WebHeaderCollection> di intestazioni associate alla risposta del server.</span><span class="sxs-lookup"><span data-stu-id="ab761-105">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="ab761-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ab761-106">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="ab761-107">Questa API non è destinata all'uso diretto nel codice.</span><span class="sxs-lookup"><span data-stu-id="ab761-107">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="ab761-108">È invece consigliabile usare un <xref:System.Diagnostics.DiagnosticSource> per associare il codice di rete.</span><span class="sxs-lookup"><span data-stu-id="ab761-108">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="ab761-109">Vedere [il manuale dell'utente di DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="ab761-109">See [DiagnosticSource User's Guide](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
>
> <span data-ttu-id="ab761-110">Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="ab761-110">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ab761-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ab761-111">Requirements</span></span>

<span data-ttu-id="ab761-112">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="ab761-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="ab761-113">**Assembly:** Sistema (in System.dll)</span><span class="sxs-lookup"><span data-stu-id="ab761-113">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="ab761-114">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="ab761-114">**.NET Framework versions:** Available since 2.0.</span></span>
