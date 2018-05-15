---
title: CoreResponseData.m_ResponseHeaders Field
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
ms.openlocfilehash: ea93b70ae8e1a710b4208050d7ec823a28b218b7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="coreresponsedatamresponseheaders-field"></a><span data-ttu-id="a7bd3-102">CoreResponseData.m\_ResponseHeaders campo</span><span class="sxs-lookup"><span data-stu-id="a7bd3-102">CoreResponseData.m\_ResponseHeaders Field</span></span>

<span data-ttu-id="a7bd3-103">`CoreResponseData.m_ResponseHeaders` è un <xref:System.Net.WebHeaderCollection> di intestazioni associate alla risposta del server.</span><span class="sxs-lookup"><span data-stu-id="a7bd3-103">`CoreResponseData.m_ResponseHeaders` is a <xref:System.Net.WebHeaderCollection> of headers associated with the server response.</span></span>

## <a name="syntax"></a><span data-ttu-id="a7bd3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7bd3-104">Syntax</span></span>
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> <span data-ttu-id="a7bd3-105">Questa API non deve essere utilizzata direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="a7bd3-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="a7bd3-106">Utilizzare invece un <xref:System.Diagnostics.DiagnosticSource> per associare il codice di rete.</span><span class="sxs-lookup"><span data-stu-id="a7bd3-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="a7bd3-107">Vedere [manuale dell'utente DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="a7bd3-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="a7bd3-108">Microsoft non supporta l'utilizzo di questa classe in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="a7bd3-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a7bd3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7bd3-109">Requirements</span></span>

<span data-ttu-id="a7bd3-110">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a7bd3-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a7bd3-111">**Assembly:** System (System. dll)</span><span class="sxs-lookup"><span data-stu-id="a7bd3-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="a7bd3-112">**Versioni di .NET framework:** disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="a7bd3-112">**.NET Framework versions:** Available since 2.0.</span></span>
