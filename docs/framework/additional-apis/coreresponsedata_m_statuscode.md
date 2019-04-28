---
title: CoreResponseData.m_StatusCode Field
ms.date: 01/29/2018
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_StatusCode
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.openlocfilehash: 53338c75d31cef3ab89879632710dba3e52091ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675403"
---
# <a name="coreresponsedatamstatuscode-field"></a><span data-ttu-id="89fee-102">CoreResponseData.m\_campo StatusCode</span><span class="sxs-lookup"><span data-stu-id="89fee-102">CoreResponseData.m\_StatusCode Field</span></span>

<span data-ttu-id="89fee-103">`CoreResponseData.m_StatusCode` è un <xref:System.Net.HttpStatusCode> contenente lo stato della risposta.</span><span class="sxs-lookup"><span data-stu-id="89fee-103">`CoreResponseData.m_StatusCode` is an <xref:System.Net.HttpStatusCode> containing the status of the response.</span></span>

## <a name="syntax"></a><span data-ttu-id="89fee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89fee-104">Syntax</span></span>
  
```csharp
public HttpStatusCode m_StatusCode
```

> [!WARNING]
> <span data-ttu-id="89fee-105">Questa API non deve essere utilizzata direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="89fee-105">This API is not meant to be used directly in your code.</span></span> <span data-ttu-id="89fee-106">È necessario utilizzare invece un <xref:System.Diagnostics.DiagnosticSource> per associare il codice di rete.</span><span class="sxs-lookup"><span data-stu-id="89fee-106">Instead, you should use a <xref:System.Diagnostics.DiagnosticSource> to hook networking code.</span></span> <span data-ttu-id="89fee-107">Visualizzare [manuale dell'utente di DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span><span class="sxs-lookup"><span data-stu-id="89fee-107">See [DiagnosticSource User's Guide](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md).</span></span>
> 
> <span data-ttu-id="89fee-108">Microsoft non supporta l'uso di questa classe in un'applicazione di produzione in alcuna circostanza.</span><span class="sxs-lookup"><span data-stu-id="89fee-108">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="89fee-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89fee-109">Requirements</span></span>

<span data-ttu-id="89fee-110">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="89fee-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="89fee-111">**Assembly:** Sistema (in System. dll)</span><span class="sxs-lookup"><span data-stu-id="89fee-111">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="89fee-112">**Versioni di .NET framework:** Disponibile dalla 2.0.</span><span class="sxs-lookup"><span data-stu-id="89fee-112">**.NET Framework versions:** Available since 2.0.</span></span>
